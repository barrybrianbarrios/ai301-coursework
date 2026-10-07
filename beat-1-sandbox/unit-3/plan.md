# Plan for issue #66

## Diagnosis

The failing assertion is caused by a mismatch between the application's structlog logging path and pytest's `caplog` capture during tests.

`BatchEmbeddingProcessor` creates its logger with `structlog.get_logger()` and, when `process([])` receives an empty list, calls:

> `logger.warning("Empty chunks list provided to BatchEmbeddingProcessor")`

The Unit 2 reproduction confirmed that this warning is actually emitted, but pytest does not receive it through `caplog`. Running:

> `python -m pytest "tests/unit/test_batch_processor.py::TestBatchEmbeddingProcessor::test_empty_chunks_list_returns_empty" -vv -s --runxfail`

showed the warning:

> `Empty chunks list provided to BatchEmbeddingProcessor`

while the assertion failed because:

> `caplog.text` was `''`

and the search of `caplog.records` returned false.

The repository's issue information identifies the same cause: application logging uses structlog, but the test environment does not configure it to propagate through Python's standard-library logging system. `tests/conftest.py` currently contains shared fixtures but no structlog test configuration.

## Scope

### In scope

- Configure structlog for the pytest environment so structlog events used by application code can reach standard-library logging and therefore pytest's `caplog`.
- Make the smallest shared test-configuration change needed in `tests/conftest.py`.
- Remove the issue #66 `xfail` marker from `test_empty_chunks_list_returns_empty` once the underlying assertion passes normally.
- Re-run the original Unit 2 reproduction against the real change and verify the warning is captured.

### Out of scope

- Changing `BatchEmbeddingProcessor.process()` behavior or replacing its structlog logger.
- Replacing structlog across the application.
- Refactoring unrelated logging code.
- Changing unrelated tests or application functionality.
- Broad changes to production logging configuration in `core/logging.py` unless testing shows that a test-only configuration cannot correctly exercise the existing logging path.

## Files to change

- `tests/conftest.py` — add shared pytest-time structlog configuration that routes events through standard-library logging so `caplog` can capture them.
- `tests/unit/test_batch_processor.py` — remove the issue #66 `xfail` marker after the logging assertion succeeds normally.

No production file is expected to require modification.

## Approach

1. Add test logging setup in `tests/conftest.py` that configures structlog to use its standard-library logging integration during pytest runs.
2. Keep the configuration scoped to the test environment rather than changing every application logger or production logging behavior.
3. Verify that calling `BatchEmbeddingProcessor.process([])` still returns `[]` and emits the existing warning without changing `batch_processor.py`.
4. Verify that the emitted warning now appears in `caplog.text` or `caplog.records`.
5. Once the assertion passes through normal pytest logging capture, remove the strict issue #66 `xfail` marker from the test.
6. Run the focused test and relevant surrounding batch-processor tests to check for regressions caused by the shared logging configuration.

## Test plan

First, rerun the original Unit 2 reproduction command with `--runxfail` while developing:

> `python -m pytest "tests/unit/test_batch_processor.py::TestBatchEmbeddingProcessor::test_empty_chunks_list_returns_empty" -vv -s --runxfail`

Before the fix, the warning is visibly emitted but `caplog.text` is empty and no matching record appears in `caplog.records`, producing an assertion failure.

After the fix, the same behavior should return `[]`, emit the warning, and make the warning observable through `caplog`, so the assertion passes.

After removing the `xfail` marker, run the focused test normally:

> `python -m pytest "tests/unit/test_batch_processor.py::TestBatchEmbeddingProcessor::test_empty_chunks_list_returns_empty" -vv`

Expected result: the test passes normally rather than being reported as an expected failure.

Then run the complete batch processor unit-test file:

> `python -m pytest tests/unit/test_batch_processor.py -vv`

Expected result: the batch processor tests pass without a regression caused by the shared test logging configuration.

## Risks and unknowns

- The exact minimal structlog processor/configuration needed for reliable `caplog` integration should be confirmed during implementation rather than assuming one configuration API in advance.
- Because `tests/conftest.py` is shared across the test suite, changing structlog configuration there could affect logging behavior in tests beyond `test_batch_processor.py`. The focused test and surrounding tests should therefore be rerun after the change.
- If existing production logging configuration is initialized by some test paths, the test setup may need to reset or restore structlog state to avoid test-order dependence. This should be handled only if observed during implementation rather than expanding scope preemptively.

## Deviations

No material deviations from the posted plan.

Implementation confirmed that a test-scoped structlog configuration in `tests/conftest.py` using `structlog.stdlib.LoggerFactory()` allows pytest's `caplog` fixture to capture the existing warning without changing production application code. The issue #66 `xfail` marker was then removed as planned.

Verification exceeded the initially planned focused checks: the original reproduction passed after the logging change, the focused test passed normally after removing the `xfail`, all 11 tests in `tests/unit/test_batch_processor.py` passed, and the complete test suite finished with 376 passed and 52 expected failures.
