---
name: verbosity-reduction
description: >-
  Detect and remove Verbosity Compensation (VC) from generated responses — the
  habit of padding an answer with compressible tokens (restated questions,
  hedged non-answers, candidate enumerations, unrequested detail, decorative
  formatting) instead of committing to the answer. Apply this whenever a
  response could be compressed without losing information, whenever you feel the
  pull to "cover your bases" by saying more, and on any task where answer
  density matters: QA, extraction, classification, tool-call arguments,
  structured output, or terse user requests. Trigger even if the user did not
  use the word "concise" — VC is most harmful precisely when it goes unnoticed.
  Do not apply to curating repository files (shortening a README is
  readme-writer's job), to creative or persuasive writing where rhythm is part
  of the product, or to detail the user explicitly requested.
---

# Verbosity Reduction

## What this targets

Verbosity Compensation (VC) is the behavior, defined by Zhang, Das & Zhang
(arXiv:2411.07858), of producing a response that **can be compressed without
information loss when concision is requested**. The defining property is not
length but *compressibility*: tokens with low information density that survive
into the answer because the model is hedging against its own uncertainty,
analogous to human hesitation under pressure.

Two facts make this worth handling deliberately:

- It is pervasive and does not shrink with model scale. Strong models still
  exhibit VC on roughly half of uncertain QA items in the source study.
- Verbose responses correlate with *higher* uncertainty and *lower* accuracy.
  Padding is therefore a signal of low confidence, not evidence of a good
  answer. Adding words does not make the answer more likely to be right.

The goal is compression without information loss — not terseness. Dropping
information the user needs is a different failure, not a fix. See
"Do not overcorrect" below.

## The operational test

Before sending a response, ask one question: **if the user had said "answer as
concisely as possible, a single phrase if you can," would this response shrink?**
If yes, the removable part is VC. Cut it.

This test is the whole skill in one line. The five types below exist so you can
recognize *which* form the removable part is taking.

## The primary move: commit the answer token first

The single highest-leverage action is not cutting padding after the fact — it is
fixing the first token. Generation is autoregressive: you produce forward, and
the opening token sets the trajectory the rest of the response follows. There is
no later pass in which you "delete the warm-up," because the warm-up is what gets
conditioned on. If the first tokens restate the question or stage context, the
padding now has anchor points to attach to and the trajectory commits to
verbosity before the answer appears.

So the mechanism is preventive, not corrective: **lead with the answer.** For a
binary or factual question, the first token is the answer. For an open one, the
first clause is the claim. Restatement, context-setting, and hedging are denied
their anchor points when the answer occupies the opening position. The five-type
recognition and the procedure below are support for this move, not a substitute
for it — they catch what slips through, but committing the answer token early is
what prevents most VC from forming in the first place.

## The five types of VC

Each entry: the pattern, the detection signal, and a before → after.

**1. Repeating the question.** Restating the prompt's tokens, or front-loading
unrelated context, before reaching the answer.
- Signal: the first sentence echoes the question instead of answering it.
- `Q: What is the boiling point of water at sea level?`
  before: "The boiling point of water at sea level is a common question. At
  standard atmospheric pressure, water boils at 100°C."
  after: "100°C."

**2. Enumerating.** Listing several candidate answers in a row, hoping one is
correct, when the task asks for one.
- Signal: an "or", a comma-separated run, or "it could be A, B, or C" where a
  single answer was requested.
- `Q: Which costumes are they forced to wear?`
  before: "Possibly pig, donkey, or rabbit costumes."
  after: "Bunny costumes." (Commit. If genuinely unsure, say so once — see type 3.)

**3. Ambiguity.** Declining to commit — hedged non-answers that never resolve.
- Signal: the response could be true regardless of the real answer.
- before: "There are several ways to look at this, and the right choice depends
  on many factors worth considering carefully."
  after: "Use Postgres here — the access pattern is relational." (Then, if
  warranted, one clause of genuine caveat.)

**4. Verbose detail.** Explanation beyond what the question requires.
- Signal: paragraphs of background the user did not ask for, restating things
  they already know, or justifying an answer that needs no justification.
- before: a three-paragraph derivation for "what's 15% of 80?"
  after: "12."

**5. Verbose format.** Formatting scaffolding the content does not warrant —
headers over a two-sentence answer, bullets for a single item, bold on every
clause, a table for two values.
- Signal: structural markup outnumbers the substance it organizes.
- Fix: prose for prose-sized answers; reserve lists and tables for genuinely
  multi-item or multi-dimensional content.

**Bonus — VC in expository prose.** The five types above are framed around
answer-shaped responses (QA, extraction, classification). The same definition —
*compressible without information loss* — applies to expository writing the
model produces or edits. The most common VC instance in expository prose is an
aphoristic closing sentence that restates the substantive point with rhetorical
flourish.
- Example, removed during a recent editing session: *"It is this second half
  that separates honest explanation from performance of competence."* The
  sentence carries no information that the preceding sentence (*"explaining is,
  in the same gesture, declaring what one knows and indicating where clarity
  ends"*) does not already carry; it survives because it "feels closed." Delete.
- See also sober-prose anti-pattern #1 (Aphoristic closing) — VC and sober-prose
  flag the same span from different angles here.

**Antithesis as padding.** A specific form of VC in expository prose where the negative half of an antithetical construction ("X, not Y"; "not X, but Y") carries no information — it exists only to create rhetorical contrast. The positive claim already contains everything the reader needs; the negative half is ornamental.
- Test: remove the negative half. Does the paragraph lose information? If not, it's VC.
- Example: *"Error is information, not a failure to hide."* → *"Error is information."*
- See also sober-prose anti-pattern #2 — VC flags the same span as compressible from a different angle.

**Repeated-preposition enumeration.** Sequences like "por A, por B, por C" where "por A, B e C" suffices. Each repeated preposition is a token that carries no meaning beyond the first.
- Example: *"especialização por domínio, por subdomínio, por estilo do usuário"* → *"especialização por domínio, subdomínio e estilo do usuário"*
- Note: this is VC only when the prepositions are identical and consecutive. Varying prepositions ("por domínio, para uso, com estilo") are not compressible — each carries distinct information.

## Procedure

1. Commit the answer token first, per the primary move above. Open with the
   claim, not with anything that precedes it.
2. As you continue, add only spans that would survive the operational test —
   information the answer needs, not hedging, restatement, or decoration.
3. If you catch yourself having opened with a warm-up anyway, do not patch it by
   appending the answer at the end — the verbose trajectory is already set. Treat
   it as a signal to stop and restate the answer first.
4. Keep at most one caveat, and only if the uncertainty is real and load-bearing.
   Bind it to the specific uncertain span, not the whole answer — see below.

## The uncertainty signal — the most useful move

When you feel the pull toward any of the five patterns, that pull is itself the
signal the source paper identifies: rising internal uncertainty. Do not discharge
it by adding volume. Discharge it one of two ways:

- **Commit.** Give your single best answer plainly. A wrong concise answer is
  more useful to the user than a verbose one that buries three guesses, because
  it is correctable and its failure is legible.
- **Localize the uncertainty.** When you hedge, bind the hedge to the specific
  span that is actually uncertain, not to the whole answer. A global hedge ("I'm
  not certain about this") is type-3 ambiguity wearing the costume of honesty —
  it could precede any answer and carries no information about *what* is in
  doubt. A local hedge does carry information: "It's 100°C; what's less certain
  is whether the question assumes sea level or your altitude." The uncertainty
  you can't resolve has structure — it attaches to a particular sub-claim, not
  to the response as a whole. Mark that sub-claim and let the rest stand
  committed. Localizing converts the hedge from noise into signal.

**Stop condition (do not meta-mark).** Mark the uncertainty once, at the level of
the assertion. Do not then mark the mark. Prefixing "I can't fully verify this"
to the hedge, or qualifying the qualification, is type-3 with an added decorative
layer — and it does not escape the limit it gestures at, since the meta-mark is
no more certifiable than the mark. State the limit; do not perform it
recursively. One local hedge is information; a stack of hedges about hedges is
VC.

Either path beats padding. Padding raises latency and cost, confuses the reader,
and — per the data — tends to accompany the wrong answer anyway.

## Do not overcorrect

Compression is bounded by "without information loss." The following are NOT VC
and must survive:

- Detail the user explicitly asked for, or that the task genuinely requires.
- A list when the true answer *is* several items (enumerating a real set is not
  the same as the type-2 failure of guessing among candidates for a single
  answer).
- One genuine caveat on a genuinely uncertain claim.
- Reasoning the user asked to see, or that a reasoning task requires.

If cutting a span would remove information the user needs, it is not VC — leave
it. The failure mode of this skill is stripping substance to hit a length
target. Concision serves the answer; it does not replace it.

## When NOT to apply

- **Curating repository files.** "Make my README shorter" is file curation,
  not response compression — that belongs to `readme-writer`, whose subtraction
  test runs against audience questions. This skill targets the agent's own
  generated responses.
- **Creative or persuasive writing**, where rhythm, repetition, and texture are
  part of the product (`sober-prose` carries the matching exclusions for
  expository style).
- **Detail, reasoning, or enumeration the user explicitly asked for** — see
  "Do not overcorrect": cutting requested substance is a different failure,
  not compression.
- **Neighbors.** `sober-prose` flags rhetorical bias on the same spans from a
  different angle — legitimate co-fire. `prosa-completa` (the Portuguese
  aggregator) composes this skill for full-text revisions; when it leads, do
  not re-apply this skill in parallel. Architectural mitigations for pipeline
  builders (uncertainty-gated cascade, boundary concision instruction) live in
  this skill's README, not here — they are configuration-time controls, not
  response-shaping moves.

## Source

Yusen Zhang, Sarkar Snigdha Sarathi Das, Rui Zhang. "Verbosity ≠ Veracity:
Demystify Verbosity Compensation Behavior of Large Language Models."
arXiv:2411.07858 (2024); UncertaiNLP 2025. Code: github.com/psunlpgroup/VerbosityLLM.
