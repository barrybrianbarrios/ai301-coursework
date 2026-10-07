# Procedure: how this skill grades a plan package

## Read order

1. Read the issue context and thread highlights first. Record the reported problem, expected behavior, maintainer requests, constraints, and any decisions already made in the thread.
2. Read the repro-evidence block next. Record the reproduction steps, inputs, commands, observed output or behavior, and the specific failure that was demonstrated.
3. Read the repo-facts block. Record contribution rules, repository conventions, relevant file or test conventions, and any AI-use or disclosure requirements.
4. Read the candidate plan. Record its diagnosis, in-scope and out-of-scope work, files or areas to change, proposed implementation approach, test plan, risks, assumptions, and unknowns.
5. Read the draft plan comment last. Record what it tells reviewers about the diagnosis, proposed change, verification approach, and any response to thread or repository constraints.
6. Do not grade checks while doing the initial read. Gather the facts first so that claims in the candidate plan do not replace or bias the independent reproduction and issue evidence.

## Evidence gathering

1. For diagnosis evidence, compare the plan's stated cause with the behavior actually demonstrated in the repro-evidence block. Record supporting, contradicting, and missing evidence.
2. For root-cause evidence, compare the diagnosed cause with the proposed implementation. Record whether the change acts on that cause or only suppresses the visible symptom.
3. For scope evidence, record the stated in-scope work, out-of-scope work, named files or areas, and any unrelated cleanup, refactoring, or feature work included in the approach.
4. For executability evidence, record the files or areas to modify, the implementation actions, their useful ordering or dependencies, and any essential implementation decision left unresolved.
5. For test evidence, map each relevant reproduction step or observable failure to the proposed post-fix test. Record the command, input, path, or behavior to exercise and the expected observable result.
6. For honesty evidence, record risks, assumptions, unknowns, and claims of certainty. Compare those claims with what the issue and reproduction evidence actually establish.
7. For communication evidence, compare the draft plan comment with the issue/thread highlights and repo facts. Record relevant maintainer requests, contribution rules, conventions, or disclosure requirements and whether the comment respects them.
8. Use the evidence guide for the exact package or live-mode location of each evidence family. Do not infer missing facts merely because they would make the plan plausible.

## Check execution

1. Grade the required checks first in this order: Diagnosis grounded in reproduction, Root cause targeted, Scope bounded, Plan executable, Test proves the fix, Risks and unknowns honest, and Comment and repo alignment.
2. For each check, use only the evidence named in that rubric row and gathered according to the evidence guide.
3. Grade a check pass only when its pass condition is supported by the available evidence.
4. Grade a check fail when the available evidence demonstrates that its pass condition is not met or is contradicted.
5. Grade a check unclear when evidence required to decide the check is genuinely missing or ambiguous. Do not turn missing evidence into a favorable assumption.
6. After the required checks, grade Communication clarity as preferred. Its result may support feedback but cannot change the final verdict.
7. When a check has already been decided from the recorded evidence, do not reread the entire package. Return only to the specific evidence location if verification is necessary.
8. Keep checks independent. Passing one check does not supply evidence for another check with a different pass condition.

## Verdict assembly

1. Apply the verdict rule from rubric.md after all checks have grades.
2. Return accept only if every required check is pass.
3. Return reject if any required check is fail or unclear.
4. Never change the verdict because of the preferred Communication clarity check.
5. For every failed or unclear required check, identify the specific evidence or missing evidence that caused the grade and state what must change before the plan is ready.
6. Quote or point to the smallest relevant piece of package evidence for the deciding required check rather than summarizing unrelated material.
7. Produce the final per-check results and the final binary verdict consistently from these grades.
