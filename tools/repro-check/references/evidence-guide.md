# Evidence guide: where proof lives in a reproduction package

## Environment

**Where it lives:** In eval mode, read the issue context for the environment or version the issue targets, the repo-facts block for relevant project/version requirements, and the repro report's environment record for what was actually tested. In live mode, read the issue thread and repository documentation for the target conditions and compare them with the environment stated in the student's draft repro comment.

**What good looks like:** The report identifies the relevant software/project version and other environment facts needed to understand what was tested. Those conditions match the issue's target, or any material difference is explicitly called out so a reader can judge whether the result applies.

## Steps

**Where it lives:** In eval mode, read the reproduction procedure in the repro report together with any starting conditions or commands supplied by the issue context. In live mode, read the student's draft repro comment and the issue's stated reproduction instructions or repository setup documentation when relevant.

**What good looks like:** A stranger can establish the tested starting state, perform the material actions or commands, and reach the trigger without guessing a step that could change the result. The test does not need a particular number of steps or headings; it needs enough operational information to repeat the attempted reproduction.

## Behavior shown

**Where it lives:** In eval mode, read the repro report's concrete artifacts, including command output, error excerpts, logs, screenshots described in the package, or other recorded observations, and compare them directly with the behavior described in the issue context. In live mode, inspect the corresponding evidence included or quoted in the student's draft and compare it with the issue thread.

**What good looks like:** For a successful reproduction, the artifacts show the material behavior the issue reports rather than a neighboring failure or superficially similar symptom. For an explicitly stated cannot-reproduce result, evidence of a concrete attempt and its observed result is sufficient when the report honestly identifies material differences or limitations that may have prevented the trigger; it does not need to establish that the bug cannot occur. Evidence should establish what was actually observed rather than merely repeat a conclusion.

## Honesty

**Where it lives:** Compare the repro report's conclusion and any claims in the comments with the recorded environment, reproduction steps, and artifacts. Also compare claims about scope or cause with what the issue context and evidence actually establish.

**What good looks like:** The wording stays within the evidence. A successful reproduction says what was observed without claiming an unproven cause or broader scope. A cannot-reproduce report is equally valid when it clearly records what was attempted and accurately states that the reported behavior was not observed. Uncertainty or material environment differences are acknowledged instead of hidden.

## Comms

**Where it lives:** In eval mode, compare the claim comment and repro report with the issue context and the repo-facts block, especially the repository's bug-report template, contribution policy, and any AI-use or disclosure policy. In live mode, compare the drafts with the issue thread, repository contribution documentation, and the Path Review house rules in `scope.md`.

**What good looks like:** The claim identifies the specific issue and the investigation the student will perform without pretending future work has already happened. The repro comment contains the student's own evidence and conclusion rather than piggybacking on another report. Apply repository disclosure rules literally: when repo facts require disclosure of AI usage in issues/comments or AI usage in any form, an AI-assisted candidate with no disclosure fails the conventions requirement; when repo facts explicitly state that issue comments do not require disclosure, do not invent one. The comments make only commitments the student can control: investigate and report findings, not promise a fix or completion date.
