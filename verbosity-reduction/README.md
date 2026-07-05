# verbosity-reduction

A skill that detects and removes Verbosity Compensation (VC) from generated responses — the pattern of padding an answer with compressible tokens (restated questions, hedged non-answers, candidate enumerations, unrequested detail, decorative formatting) instead of committing to the answer. Based on the VC framework defined by Zhang, Das & Zhang (arXiv:2411.07858).

## Usage

The AI agent activates the skill automatically whenever a response could be compressed without information loss, or when the task demands answer density. To invoke directly:

```
/verbosity-reduction
```

## When it applies

- QA, extraction, and classification tasks
- Tool-call arguments and structured output
- Terse user requests (single-word or short questions)
- Any response where the model feels the pull to "cover its bases" by adding volume
- Expository prose the model writes or edits — aphoristic closing sentences that restate the substantive point with rhetorical flourish, antithesis where the negative half is padding, and enumerations with repeated identical prepositions are VC (compressible without information loss)
- Triggered even when the user did not ask for concision — VC is most harmful when it goes unnoticed

## When it does not apply

- Detail the user explicitly requested
- Enumeration of a genuinely multi-item answer (a real set, not guesses for a single answer)
- One genuine caveat on a genuinely uncertain claim
- Reasoning the user asked to see, or that a reasoning task requires

## Core idea

Verbose responses correlate with higher uncertainty and lower accuracy. Padding is a signal of low confidence, not evidence of a good answer. The fix is not to cut words mechanically, but to **commit the answer token first** — leading with the claim prevents most VC from forming before it starts.

## Architectural mitigation (for system builders)

The skill's self-check is for a model shaping its own output. If you are building a pipeline rather than answering directly, the source paper's mitigation is structural and worth porting:

- **Uncertainty-gated cascade.** Measure per-response uncertainty (perplexity on the answer span for open models; a proxy such as logit/Laplacian or a cheap self-consistency vote for closed ones). When uncertainty exceeds a threshold, treat the response as likely-VC and replace it — re-prompt with a hard concision instruction, route to another model, or fall back to a deterministic path. In the paper this cascade dropped VC on one model from ~64% to ~16% on Qasper.
- **Concision instruction at the boundary.** A system-level "answer in the fewest tokens that preserve the answer; a single phrase if possible" measurably reduces VC, but does not eliminate it — pair it with the gate.
- **Separate the metrics.** Track answer correctness and response compressibility as independent axes. Length alone is a poor proxy; you want low compressibility at fixed correctness, not merely short outputs.

These are pre-runtime or boundary controls. They keep the uncertainty handling out of the hot path, which suits batch or DSL-compiled architectures where the expensive judgment happens at configuration time and execution stays deterministic.

## Source

Yusen Zhang, Sarkar Snigdha Sarathi Das, Rui Zhang. "Verbosity ≠ Veracity: Demystify Verbosity Compensation Behavior of Large Language Models." arXiv:2411.07858 (2024); UncertaiNLP 2025.
