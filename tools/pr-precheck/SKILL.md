---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

<!--
THIS IS THE PART YOU WRITE, and it is the last one: the frame itself.
Weeks 1 through 3 handed you a working SKILL.md and you filled the
files behind it; this week the frame ships as headings, and you write
what it says. The frontmatter above and the section headings below are
fixed (CONTRACT.md's layout rule); the instructions under each heading
are yours. Write instructions to the tool, in the imperative, the way
weeks 1-3's frames spoke to you: what to read, in what order, what to
refuse, what to emit. Your executor in the rotation is the test: a
frame gap they hit (cannot tell what the tool reads, or how a verdict
gets assembled) is a missing sentence here.

One section is not yours: the JSON schema in "Verdict and output" is
reproduced from CONTRACT.md verbatim and may not be altered. Your
words decide everything around it.
-->

## The question

Grade exactly one PR package to answer one question: is this ready to submit?

A PR package consists of its title, description, committed branch diff, and test evidence. Read those artifacts against the plan it claims to implement, including recorded deviations, and against the issue that plan belongs to.

Do not grade unrelated questions or more than one PR package in one run. Execute the rubric, evidence guide, and procedure instead of deciding from intuition.

## Inputs and modes

Run in exactly two modes.

Live mode grades the student's own draft PR. Read `plan.md`, including `## Deviations`; the committed branch diff from `git diff main...HEAD`; the PR title and description in `pr_draft.md`; `test_evidence.md`; the supplied issue and its thread; `.github/PULL_REQUEST_TEMPLATE.md`; and `docs/CONTRIBUTING.md`.

Gather the issue thread, PR template, and contribution policy from the real scoped repository. For a house-chain student, use the house plan and house repro pack in place of the student's plan and reproduction evidence.

Eval mode grades one frozen practice-submission bundle. The bundle is the whole world. Use only its text. Fetch nothing and read no outside files. Run every rubric check and the complete verdict rule.

## The scope seam (live mode only)

In live mode, read `scope.md` before anything else. Use the repository and house rules it defines.

Refuse to grade a PR outside the repository named by `scope.md`. If its `Repo:` line still contains an unfilled placeholder, stop without grading and tell the student to fill it with their section's Path Review repository. Never guess the scope.

In eval mode, ignore `scope.md` entirely.

## The voice seam (live mode only)

In live mode, read `voice-guide.md` and check the outgoing PR title and description against its rules. Report any broken rule in the readable summary and identify the rule that was broken.

A voice-guide problem does not change the verdict by itself unless a check in `rubric.md` explicitly uses that evidence.

In eval mode, ignore `voice-guide.md` entirely.

## Component reads

Read `rubric.md`. It defines the checks, the evidence each check uses, the pass condition, the weight of each check, and the verdict rule.

Read `references/evidence-guide.md` as the map for locating each evidence family in the PR package.

Execute `procedure.md` exactly as written. It defines the read order, evidence gathering, check execution, and verdict assembly. If the procedure is silent where a step is required, report the gap instead of improvising.

If `rubric.md` has no written checks or `procedure.md` has no written steps, refuse to grade and identify the empty component. Never invent checks or procedure steps at runtime.

## Verdict and output

The verdict is binary: `accept` means ready to submit and `reject` means hold. There is no conditional, scored, or third verdict.

A concise readable per-check summary may appear before the JSON block. In live mode, it may also include voice-guide notes.

End every completed grading run with the following fenced JSON block, valid and last, with nothing after it:

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

- Evidence first. Never grade a check without naming the concrete fact, quote, diff line, command output, or absence that decided it. "Looks fine" is not evidence.
- Grade the PR, not the polish. Compare the actual artifacts against the plan, issue, evidence, and stated repository standards.
- The rubric decides. If evidence satisfies its stated pass condition, grade it accordingly even if intuition disagrees.
- The procedure decides how. Follow `procedure.md` as written and report gaps rather than silently adding steps.
- Treat `unclear` according to the verdict rule in `rubric.md`. If the rule is silent, treat `unclear` as failure because an unverifiable PR is not ready to submit.
