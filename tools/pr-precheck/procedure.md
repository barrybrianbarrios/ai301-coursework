# Procedure: how this tool grades a PR package

<!--
THIS IS THE PART YOU WRITE (second week running for the procedure).
Week 3 you wrote these steps for a plan package; this week the graded
object is a PR package, and the read that matters most is a
side-by-side: the diff against the plan, the evidence against the test
plan, the description against both. Your week-3 procedure is the
pattern; do not paste it unchanged, because its read order was built
for a different object.

Your rotation is the design brief again, and this week friction routes
three ways: a stall on WHAT to decide is a rubric gap, a stall on
WHERE to look is a procedure gap (this file), and a stall on what the
tool even reads or outputs is a frame gap (your SKILL.md). A complete
procedure lets someone who has never seen a PR package before grade
one exactly the way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
plan's scope pair before opening the diff, and list the files the plan
names" is a step; "understand the change" is a wish.
-->

## Read order

1. Read the issue first and record the required behavior and reported failure.
2. Read `plan.md` next. Record its implementation boundary, named files, test plan, and every entry under `## Deviations`.
3. Read the committed branch diff against `main`. Record changed files and material hunks before reading claims about them in the PR description.
4. Read `test_evidence.md` and record each command, observable result, before/after reproduction result, and repository check outcome.
5. Read the draft PR title and description last so its claims can be compared against evidence already gathered.
6. In live mode, also read the repository PR template and `docs/CONTRIBUTING.md` before grading standards.

This order prevents the PR description from becoming the source of truth for what the change actually does.

## Evidence gathering

1. For plan fidelity, pair every material changed file and hunk with the plan's stated scope or a recorded deviation. Record unexplained additions and planned work missing from the diff.
2. For description fidelity, pair each material claim in the draft description with the diff, plan, issue, or deviations that prove or contradict it.
3. For fix evidence, pair the plan's promised reproduction or behavioral test with the command and observable output in `test_evidence.md`.
4. For repository checks, record each required validation command and its reported outcome. Do not convert an honest failure, skip, or unavailable check into a pass without applying the rubric's readiness rule.
5. For diff quality, record unrelated hunks, debug artifacts, generated debris, accidental files, or other changes that obscure review.
6. For repository standards, record the material asks from the PR template and contribution policy, then pair each with the draft title or description response.

## Check execution

1. Execute the rubric checks in table order using the evidence already gathered.
2. For each check, compare only the named evidence with that check's pass condition and record `pass`, `fail`, or `unclear`.
3. Grade `pass` only when observable evidence satisfies the pass condition. Grade `fail` when evidence contradicts it.
4. Grade `unclear` when evidence needed to decide the check is genuinely absent, ambiguous, or unverifiable; do not invent missing facts.
5. Reuse gathered evidence across checks when it directly applies instead of re-reading the whole package, but keep each check's decision independent.

## Verdict assembly

1. Apply the verdict rule in `rubric.md` after every check has a grade.
2. Accept only when every required check passes. Treat `unclear` as failure for required checks. Preferred checks never change the verdict.
3. If the verdict is `reject`, identify the first failing or unclear required check in rubric order as the deciding check. If several checks fail, still report every check in the JSON.
4. For each JSON check entry, give one concrete line of evidence that decided its grade. For the deciding check, quote or identify the specific contradiction, missing evidence, or observable failure.
5. End with the exact JSON schema required by `SKILL.md`, using only `accept` or `reject`, and write nothing after the fenced JSON block.
