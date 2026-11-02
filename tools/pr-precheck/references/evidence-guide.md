# Evidence guide: where evidence lives in a PR package

<!--
THIS IS THE PART YOU WRITE (third week running: the map stays in your
hands). Your tool uses this guide as its map: for every kind of
evidence a rubric check names, this file says WHERE to find it in a PR
package and WHAT GOOD LOOKS LIKE when you do.

The four families below are the harness's failure categories under
the names the eval README uses: plan fidelity = silent-drift, test
evidence = not-tested, diff quality = unreviewable, standards and
comms = standards-wall. A package that fails none of them is a
clear-accept. Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the plan-context block's scope pair and test
  plan, the candidate PR's diff, commits, description, or
  test-evidence section, the repo-facts block's template asks and
  stated policy). In live mode (where in your working copy and on
  GitHub: your plan.md and its deviation notes, your branch's diff,
  your draft title and description, your captured test output, the
  repo's PR template and CONTRIBUTING.md).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("every changed file falls inside the
  plan's stated boundary or a deviation note") over adjectives ("the
  diff is clean").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts three ways: your
procedure says WHEN to gather each family, this guide says WHERE, and
your SKILL.md says the tool reads both. Write the map you wish your
executor had.
-->

## Plan fidelity (harness category: silent-drift)

**Where it lives:** In eval mode, compare the plan-context block's scope, boundary, and deviations with the candidate PR diff and description. In live mode, compare `plan.md`, especially `## Deviations`, with `git diff main...HEAD`, the issue thread, and `pr_draft.md`.

**What good looks like:** Every material changed file and hunk falls within the plan's stated boundary or an honestly recorded deviation, and required planned work is not silently omitted. Material claims in the description agree with what the diff actually delivers.

## Test evidence (harness category: not-tested)

**Where it lives:** In eval mode, compare the package's test-evidence section with the plan-context test plan and reproduction steps. In live mode, compare `test_evidence.md` with the test plan in `plan.md`, the issue reproduction, and the repository's required validation commands.

**What good looks like:** Evidence names the command or behavior tested and shows observable output supporting the claimed before/after result. Required repository checks have visible, honestly reported outcomes; a bare claim such as "tests pass" without observable evidence is insufficient.

## Diff quality (harness category: unreviewable)

**Where it lives:** In eval mode, inspect the candidate PR unified diff and commit list. In live mode, inspect `git diff main...HEAD`, its changed-file list, and the branch commits.

**What good looks like:** The intended fix is directly visible and reviewable without unrelated changes obscuring it. Debug leftovers, dead or commented-out code, formatting churn, generated debris, accidental files, and unrelated drive-by edits are absent.

## Standards and comms (harness category: standards-wall)

**Where it lives:** In eval mode, compare the repo-facts block's PR-template asks, contribution instructions, stated policies, and disclosure requirements with the candidate PR title and description. In live mode, compare `.github/PULL_REQUEST_TEMPLATE.md`, `docs/CONTRIBUTING.md`, relevant maintainer direction in the issue thread, and `voice-guide.md` with `pr_draft.md`.

**What good looks like:** Material repository requirements are actually addressed rather than left as boilerplate or ignored. Required disclosures, including AI-use disclosure when requested, are present and honest; explicit N/A responses or disclosed limitations are acceptable when repository rules allow them.
