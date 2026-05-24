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
- Expository prose the model writes or edits — aphoristic closing sentences that restate the substantive point with rhetorical flourish are VC (compressible without information loss) even though they "feel closed"
- Triggered even when the user did not ask for concision — VC is most harmful when it goes unnoticed

## When it does not apply

- Detail the user explicitly requested
- Enumeration of a genuinely multi-item answer (a real set, not guesses for a single answer)
- One genuine caveat on a genuinely uncertain claim
- Reasoning the user asked to see, or that a reasoning task requires

## Core idea

Verbose responses correlate with higher uncertainty and lower accuracy. Padding is a signal of low confidence, not evidence of a good answer. The fix is not to cut words mechanically, but to **commit the answer token first** — leading with the claim prevents most VC from forming before it starts.

## Source

Yusen Zhang, Sarkar Snigdha Sarathi Das, Rui Zhang. "Verbosity ≠ Veracity: Demystify Verbosity Compensation Behavior of Large Language Models." arXiv:2411.07858 (2024); UncertaiNLP 2025.
