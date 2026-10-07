# Voice guide: how I talk upstream

## Who I am in threads

I am a student contributor investigating a specific issue through reproduction and evidence. I write as an investigator, not as someone who already knows the cause or fix. Readers can expect me to state what I tested, what I observed, and what I still do not know.

## Rules I write by

### Rule: Separate plans from results

Before I have run the reproduction, I describe what I plan to investigate rather than writing as though I already confirmed the bug.

- Wrong: "I reproduced this bug and will investigate it."
- Right: "I'll try to reproduce this behavior and report the environment, steps, and results here."

### Rule: Claim only what the evidence shows

I do not turn an observation into a diagnosis unless my evidence establishes the cause.

- Wrong: "This proves the parser is broken because of the new release."
- Right: "I observed the reported failure on this version; I have not established its cause."

### Rule: Make my report independently useful

I describe my own test and evidence instead of relying on another person's reproduction.

- Wrong: "Same as the reproduction above. I can confirm."
- Right: "I tested this in my environment using the following steps and observed the following result."

### Rule: Do not promise what I cannot control

I can promise to investigate and report what I find, but I do not promise a fix, acceptance, merge, or completion date.

- Wrong: "I'll have a fix ready tomorrow."
- Right: "I'll investigate the reported behavior and post my findings here."

### Rule: State uncertainty directly

When the evidence is incomplete or I cannot reproduce the issue, I say that directly rather than forcing a confident conclusion.

- Wrong: "The issue must already be fixed."
- Right: "I could not reproduce the reported behavior under the environment described below."

## Things I never post

- A claim that I reproduced something before I actually tested it.
- A promise that I will fix an issue or deliver a patch by a particular date.
- A claim about root cause that my evidence does not establish.
- A piggyback reproduction such as "same as above."
- A required-disclosure omission when the repository requires disclosure.
- A confident conclusion when my evidence is incomplete.
