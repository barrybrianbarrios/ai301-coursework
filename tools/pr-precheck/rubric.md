# Rubric: is this pull request ready to submit?

<!--
THIS IS THE PART YOU WRITE (fourth week running; this is the rubric's
final form in the sandbox). Your frame in SKILL.md executes whatever
checks you define here, via your procedure.md. It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the diff read against the plan's scope, the test
     evidence read against the plan's test plan, the description read
     against the diff, the repo-facts block's template asks) or a
     location from your references/evidence-guide.md. "The PR" is not
     a source; "the diff's changed files read against the plan's
     stated boundary" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself
     (does the diff fall inside the plan plus its deviation notes? is
     the claimed evidence observable?), never the write-up's shape
     (how long the description is, how many commits there are).
     Structure-shaped checks are what make graders disagree with
     themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (submit) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. State the `unclear`
   treatment explicitly: the frame here is YOUR SKILL.md, so a rubric
   that stays silent is only covered if your frame's grading
   discipline says what happens (the contract's own default is that
   an unverifiable claim fails).

Cover what actually gets bad PRs submitted. The failure families the
lecture named ARE the harness's scoring categories, same names as the
eval README: silent drift (the diff silently does more or less than
the posted plan, or the description claims fidelity the diff
contradicts), not tested (the evidence proves nothing observable, or
the repo's own checks were never run), unreviewable (debris or
unrelated hunks bury the change), and standards wall (the repo's
stated template and disclosure asks are ignored). Your evidence
guide's four headings map onto these one to one (plan fidelity =
silent drift, test evidence = not tested, diff quality =
unreviewable, standards and comms = standards wall), and the category
floor is scored on exactly these names plus clear accept. A rubric
that ignores a category will fail the eval packages built around
that category. And remember the honest-outcome
rule, fourth week running: a PR that honestly discloses a shortfall
can be ready; a rubric that equates "less than everything" with
"hold" fails the set.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Plan fidelity | The committed diff read against the plan's stated scope and `## Deviations`, plus the issue requirements. | Pass when every material diff change is within the planned scope or is honestly recorded as a deviation, and the implementation does not silently omit a required part of the plan. | required |
| Description fidelity | The draft PR description read against the committed diff, plan, deviations, and issue. | Pass when material claims about what changed and what remains incomplete agree with the observable diff and recorded deviations; an honestly disclosed shortfall may pass. | required |

| Fix evidence | `test_evidence.md` read against the plan's test plan and the issue's failure mode, including before/after reproduction evidence where applicable. | Pass when the recorded commands and observable output demonstrate that the reported failure existed and that the changed branch fixes it, or honestly explain why a planned proof is not applicable. | required |
| Repository checks | `test_evidence.md` read against the repository's stated validation commands and the plan's promised checks. | Pass when the relevant repository checks were actually run and their observable outcomes are reported honestly; a disclosed failing or unavailable check may pass when it does not contradict the claimed readiness of the change. | required |

| Diff quality | The committed branch diff and changed-file list, read against the issue and planned implementation boundary. | Pass when the diff is focused enough to review: changed files and hunks serve the issue or a recorded deviation, and unrelated edits, generated debris, debug artifacts, or accidental files do not bury the intended change. | required |

| Repository standards | The draft title and description read against the repository PR template, `docs/CONTRIBUTING.md`, and repo-facts requirements including disclosure asks. | Pass when the submission satisfies the repository's material stated requirements and honestly answers required template and disclosure asks; an explicit N/A or disclosed limitation may pass when the repository allows it. | required |

## Verdict rule

Accept only when every `required` check passes. Reject when any required check fails or is `unclear`. Preferred checks, if any, never change the verdict. An honestly disclosed limitation is not automatically a failure; grade it according to the applicable check's pass condition and whether the evidence still supports readiness to submit.
