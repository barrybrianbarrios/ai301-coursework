# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/66

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
All three graded live. Scope confirmed — all in codepath/pathreview-ai301-fa26-s3; house rule applied, so classmates' claim comments were not read as claims. This run used the active scope (.claude/skills/issue-select/scope.md), with your fit profile, not the stale starter copy.

Project viability — pass (all three, repo-level). Not archived; last default-branch commits 2026-09-16 by Aburke225; docs/CONTRIBUTING.md, the PR template, and the repo carry no AI or contribution-tooling policy — silence passes.

Accepted, in fit order:

1. #66 — structlog not captured by pytest caplog. Best fit: Python test-infrastructure work that lands squarely on your stated goals of writing tests and getting oriented in an unfamiliar repo, with a concrete pass condition (caplog assertions work), one named file to change (tests/conftest.py), a named failing test, and a runnable repro. It also happens to be untouched — zero comments, zero claims, no PR.
2. #73 — README and .env.example disagree about the LLM API key. Bounded and concrete ("Make the two files agree", two named files, 1–2 hours), but a docs/config alignment task rather than the debugging-and-testing work your profile points at, so it ranks second.

Rejected:

- #69 — output parser crashes on top-level JSON array. Sunk by Available: PR #79 "fix: handle top-level JSON arrays in output parser" is open and non-draft with body "Fixes #69". Its other two checks passed.

Two notes. #73 carries 18 comments that are entirely claim comments and reproduction reports from nine classmates, with no PR and no assignee — the timeline's only cross-reference is to issue #53, not a pull request. Under the house rule that leaves Available passing, but be aware you'd be the tenth person on it. And #66 is the one candidate without a good first issue label (just bug, tests, tier-1). Your rubric treats that label as positive evidence only, so its absence fails nothing — but it does mean no maintainer has explicitly vouched for it as newcomer-friendly, and the phrase "fail suite-wide" in the title describes the blast radius of the bug, not the size of the fix.

[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/66",
    "checks": [
      {"name": "Project viability", "grade": "pass",
       "evidence": "Repo not archived; last default-branch commits 2026-09-16 by Aburke225; no AI or contribution-policy statement in docs/CONTRIBUTING.md, PR template, or any policy file (silence passes)."},
      {"name": "Newcomer scope", "grade": "pass",
       "evidence": "Maintainer-filed (Aburke225, COLLABORATOR); one bounded outcome ('Configure structlog in tests/conftest.py ... so caplog-based assertions work') with a named failing test and a runnable repro command; no umbrella, redesign, or prior attempts."},
      {"name": "Available", "grade": "pass",
       "evidence": "No assignees, zero comments, and no cross-referenced pull requests in the issue timeline."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73",
    "checks": [
      {"name": "Project viability", "grade": "pass",
       "evidence": "Repo not archived; last default-branch commits 2026-09-16 by Aburke225; docs/CONTRIBUTING.md contains no AI, disclosure, or policy language."},
      {"name": "Newcomer scope", "grade": "pass",
       "evidence": "Maintainer-filed, labeled 'good first issue'/'docs'/'tier-1'; one outcome ('Make the two files agree') across two specifically named files (README.md, .env.example), est. 1-2 hours."},
      {"name": "Available", "grade": "pass",
       "evidence": "No assignees; timeline's only cross-reference is issue #53 (not a PR); all 18 comments are classmates' claims and repro reports, waived by the Path Review house rule."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
    "checks": [
      {"name": "Project viability", "grade": "pass",
       "evidence": "Repo not archived; last default-branch commits 2026-09-16 by Aburke225; no AI or contribution-policy statement anywhere in the repo."},
      {"name": "Newcomer scope", "grade": "pass",
       "evidence": "Maintainer-filed, labeled 'good first issue'/'rag'/'tier-1'; one outcome ('The fallback path should handle array responses', remove the H-02 xfail) with named files rag/generator/output_parser.py and tests/unit/test_output_parser.py."},
      {"name": "Available", "grade": "fail",
       "evidence": "PR #79 'fix: handle top-level JSON arrays in output parser' is open, non-draft, body 'Fixes #69' (cross-referenced 2026-09-27)."}
    ],
    "verdict": "reject"
  }
]
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

"agreement: 19/20 scored items  (bar: 18/20: PASS)"

**Issue analysis**

"issue-01  accept  reject   NO     failed: Newcomer scope"

My rubric's decision was reject and the gold label was accept. The evaluator records the reason as "failed: Newcomer scope." Under my rubric, Newcomer scope is required, so failing that check caused the overall reject verdict even though the gold label was accept.

**Check rationale**

"Pass if the issue identifies one concrete outcome that a newcomer can reasonably investigate and work toward. Several specifically named files, components, examples, or fixes may still constitute one bounded task when they serve the same outcome. Wording such as "for example," "including," "etc.," "consider," "additional suggestions," or explicitly lower-priority ideas does not by itself expand the required scope. When the issue identifies a concrete bug or desired outcome and separately suggests possible causes, fixes, or optimizations, judge the required outcome rather than treating every suggestion as mandatory. A maintainer-applied `good first issue` or equivalent newcomer label is strong positive evidence that the scope is suitable, but it does not override the failure conditions below. Fail if the required work is genuinely open-ended or codebase-wide, is a tracking/umbrella issue containing independent tasks rather than one coherent outcome, requires broad architectural redesign, has a long pattern of repeated contributor claims or implementation attempts abandoned or closed without the requested change landing, or proposes new product surface without evidence of project buy-in such as maintainer authorship/endorsement, an accepted project label, or roadmap evidence."

I kept this check because my iterations showed that simply counting files or suggested fixes was too rigid. A multi-file issue can still be one bounded newcomer task, while repeated abandoned attempts, an umbrella issue, or an unendorsed new product surface can signal substantially more scope than the issue initially appears to have.

**Trade-offs**

The trade-off is visible in the final run:

"issue-01  accept  reject   NO     failed: Newcomer scope"

The final Newcomer scope check correctly handled the other scope cases well enough for the run to report:

"scope 4/4"

but it still rejected issue-01 when the gold label was accept. I accept that trade-off because the check is deliberately cautious about work that can appear broader than a bounded newcomer task.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Issue #66 fits my interests because it involves Python, debugging, testing, and understanding test infrastructure in an unfamiliar codebase. The task is also bounded enough to fit the time available: it identifies tests/conftest.py, a failing test, and a reproducible failure.

2. The verdict correctly identified that the repository is active, the issue has a concrete outcome, and nobody is currently working on it. I also weighed my own interest in debugging and testing work. The rubric can determine whether an issue is suitable, but my fit profile is what made #66 more appealing to me than the accepted documentation/configuration issue #73.

3. I expect claiming #66 to be straightforward because the live check found no assignee, no comments, and no cross-referenced pull request. The main difficulty will likely be understanding how structlog and pytest caplog interact and making the configuration change without affecting unrelated tests.
---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
