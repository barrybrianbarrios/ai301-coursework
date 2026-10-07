# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

**Where it lives:** In eval mode, read the candidate plan's diagnosis or stated cause together with the repro-evidence block, including reproduced behavior, commands, inputs, and output. Also use relevant issue context when it establishes expected behavior. In live mode, read the diagnosis in `plan.md` against the student's posted Unit 2 repro evidence and the GitHub issue.

**What good looks like:** The stated cause explains behavior that the reproduction actually demonstrates and does not contradict the observed evidence. If the evidence supports multiple possible causes, the plan identifies that uncertainty instead of claiming an unsupported root cause.

## Scope

**Where it lives:** In eval mode, read the candidate plan's scope statement, out-of-scope statement, named files or areas, and proposed approach. Compare them with the issue context and reproduced problem. In live mode, use the same parts of `plan.md` and the GitHub issue.

**What good looks like:** The plan describes one bounded change tied to the reproduced issue. It identifies what will and will not change and avoids unrelated cleanup, refactors, or feature work unless the issue evidence makes that work necessary.

## Executability

**Where it lives:** In eval mode, read the candidate plan's files or areas to touch, implementation approach, and sequence or dependencies. Use repo facts when they identify relevant repository structure or conventions. In live mode, read those parts of `plan.md` together with the repository.

**What good looks like:** Another contributor can identify where to start and what implementation actions to take without asking the author for an essential missing decision. The plan gives enough concrete direction to begin work without requiring every line of code to be predetermined.

## Test plan

**Where it lives:** In eval mode, read the candidate plan's test plan against the repro-evidence block's steps, inputs, commands, artifacts, and observed failure. In live mode, compare the test plan in `plan.md` with the student's Unit 2 reproduction.

**What good looks like:** The proposed test exercises the real changed behavior by rerunning the reproduction or a justified adaptation of it. It names an observable expected result that would distinguish the fixed behavior from the reproduced failure rather than merely saying tests should pass.

## Honesty

**Where it lives:** In eval mode, read the candidate plan's risks, unknowns, assumptions, and any claims about causes or implementation outcomes. After a build, also read the Deviations section. Compare these with the issue and reproduction evidence. In live mode, use the corresponding sections of `plan.md`.

**What good looks like:** Material uncertainty is labeled as uncertainty, assumptions are visible, and claims do not go beyond what the available evidence establishes. After implementation, any meaningful departure from the posted plan is recorded under Deviations; if nothing changed, that is stated explicitly.

## Comms

**Where it lives:** In eval mode, read the draft plan comment against the issue context or thread highlights and the repo-facts block, including maintainer requests, templates, contribution conventions, and AI-use disclosure rules. In live mode, read `comment.md` against the GitHub issue thread and repository contribution documentation.

**What good looks like:** The comment presents the student's own diagnosis and proposed change, addresses relevant maintainer or thread constraints, and follows stated repository conventions. It gives reviewers enough information to understand the intended change and verification without relying on another student's plan or generic boilerplate.
