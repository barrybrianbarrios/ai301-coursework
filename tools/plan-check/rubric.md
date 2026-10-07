# Rubric: is this plan ready to post and build from?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Diagnosis grounded in reproduction | The plan's stated diagnosis read against the repro-evidence block, including the reproduced behavior, commands, and output. | Pass if the proposed cause is consistent with and explains the reproduced behavior. Fail if it contradicts, ignores, or makes an unsupported leap beyond the reproduction evidence. | required |
| Root cause targeted | The plan's diagnosis and proposed approach read together with the repro evidence. | Pass if the proposed change addresses the cause supported by the evidence rather than only masking the observed symptom. If the evidence cannot distinguish the root cause, the plan must identify that uncertainty instead of claiming certainty. | required |
| Scope bounded | The plan's in-scope and out-of-scope statements, named files or areas, and proposed approach. | Pass if the work is one bounded change tied to the reproduced issue and avoids unrelated cleanup, refactors, or feature work. | required |
| Plan executable | The plan's files or areas to touch, proposed approach, and order of work. | Pass if another contributor could begin implementing the change from the plan without needing the author to supply a missing implementation decision essential to starting the work. | required |
| Test proves the fix | The plan's test plan read against the repro-evidence steps, inputs, and observable failure. | Pass if the test plan reruns or validly adapts the reproduction against the real changed code and states an observable expected result that distinguishes the fixed behavior from the reproduced failure. | required |
| Risks and unknowns honest | The plan's risks, unknowns, assumptions, and any stated uncertainty read against the available issue and reproduction evidence. | Pass if material unknowns or assumptions are stated as such and the plan does not present unsupported conclusions as established facts. | required |
| Comment and repo alignment | The draft plan comment read against the issue/thread highlights and the repo-facts block, including contribution conventions and stated maintainer requests. | Pass if the comment represents the student's own plan, responds to relevant maintainer or thread constraints, and does not conflict with stated repository contribution rules. | required |
| Communication clarity | The draft plan comment and plan details needed to communicate the intended change and verification. | Pass if the comment communicates the diagnosis, bounded change, and verification approach clearly enough for a reviewer to understand what will be built and why. | preferred |

## Verdict rule

Accept only when every required check passes. A fail on any required check produces reject. An unclear grade on a required check counts as a fail because the plan is not ready to build when evidence needed for a required decision is missing or ambiguous. Preferred checks may identify improvements but never change the final verdict.
