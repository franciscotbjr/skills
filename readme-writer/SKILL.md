---
name: readme-writer
description: >-
  Use when writing, restructuring, or reviewing a README file — the front page
  of a repository, library, tool, dataset, or documentation-first project.
  Covers creating a README from scratch, auditing an existing one for first
  impressions and adoption signals, choosing its section structure, adding
  badges or a quick start, and keeping the file synchronized with the
  repository. Extracts the project's fundamentals (what it is, why it exists,
  who it serves, what state it is in) and designs for a scanning reader.
  Trigger words: README, project front page, repository entry point, badges,
  quick start. Do not apply to deep documentation (tutorials, how-to guides,
  API reference), changelogs, code comments, or general prose style —
  sober-prose handles prose style and may fire alongside this skill on README
  prose.
---

# README Writer

A README is scanned in seconds and often decides adoption before any
installation. This skill packages a procedure for writing
and revising READMEs, grounded in measured evidence about how they fail and how
visitors read them. Evidence types are labeled throughout: **[empirical]** for
measured results, **[practitioner]** for mature but unvalidated prescriptions
(Diátaxis, standard-readme, GitHub guides).

## The three rules that matter most

1. **Answer the four fundamentals before writing any form.** What it is (one
   sentence, no insider jargon), why it exists (what problem, for whom), what
   differentiates it (why this and not the obvious alternative), and what state
   it is in (active, stable, experimental). **[empirical]** In 393 GitHub
   READMEs, "what" appears in 97.0% and "how" in 88.5%, but "why" in only 25.7%
   and status in 21.4% ([Prana et al., EMSE 2019](https://arxiv.org/abs/1802.06997))
   — the default is to describe mechanics and omit purpose. Anchor each answer
   in a repository artifact (code, docs, history, issues). Where the repository
   does not answer, record the question as unanswered and ask the author;
   filling the gap with plausible prose fabricates a public promise.

2. **Put what decides the visitor's stay in the first third.** **[empirical]**
   79% of users scan new pages and 16% read word by word
   ([NN/g, 1997](https://www.nngroup.com/articles/how-users-read-on-the-web/));
   an average visit covers at most 28% of the words
   ([NN/g](https://www.nngroup.com/articles/website-reading/)); the gaze follows
   an F-pattern concentrated on the top and left margin
   ([NN/g, 2006](https://www.nngroup.com/articles/f-shaped-pattern-reading-web-content-discovered/)).
   A reader who sees only the headings and the first third must still learn
   what the project is, who it is for, and how to start.

3. **Keep the README synchronized with the repository.** An outdated README is
   worse than an incomplete one: it misstates with the authority of official
   documentation. **[empirical]** Version–documentation inconsistency is the
   most reported documentation problem (~80% of surveyed practitioners,
   [Does Documentation Matter?, 2024](https://arxiv.org/html/2403.03819v1) —
   small sample, 29 survey responses), and outdated documentation drives
   newcomers to give up ([Steinmacher et al.](https://www.ime.usp.br/~gerosa/papers/Steinmacher2014_Chapter_BarriersFacedByNewcomersToOpen.pdf)).
   When a change invalidates a claim and maintaining it is not sustainable,
   remove the claim.

## Procedure

### 1. Capture the fundamentals (before form)

- Produce the four-fundamentals block (rule 1) with anchors, before any prose.
- **Declare the audience and what it already knows.** Name the primary and
  secondary audiences (potential user, contributor, evaluator); for each, state
  the vocabulary the text may assume. The default bias is the curse of
  knowledge: informed authors cannot ignore what they know when anticipating
  less-informed readers' judgment (**[empirical]**
  [Camerer, Loewenstein & Weber, JPE 1989](https://www.journals.uchicago.edu/doi/abs/10.1086/261651)).
  Treat every term that only makes sense from inside the project as suspect.
- **Order content by the visitor's decision sequence** — *what is this? is it
  for me? how do I start? can I trust it?* — not by the author's mental summary
  (architecture, history, modules). **[empirical]** The most cited reasons for
  consulting documentation when deciding to adopt are understanding features
  (16.56%) and studying usage examples (12.58%)
  ([Does Documentation Matter?](https://arxiv.org/html/2403.03819v1)).

### 2. Design the communication

- **Informative section headings; lists and links where there is real
  enumeration.** **[empirical]** README update frequency, number of lists, and
  number of links statistically distinguish popular from non-popular
  repositories ([Wang, Wang & Chen, JSS 2023](https://www.sciencedirect.com/science/article/abs/pii/S0164121223002017))
  — a correlation; neither study establishes causal direction. Enumeration
  fabricated to look organized adds visual pattern without answering any
  audience question.
- **Plain language even for experts.** One concept per sentence; a technical
  term enters only when the declared audience commands it. **[empirical]**
  Highly qualified readers also prefer concise, scannable text
  ([NN/g](https://www.nngroup.com/articles/plain-language-experts/));
  **[practitioner]** the plain-language standard is that the intended reader
  finds, understands, and uses the information
  ([ISO 24495-1:2023](https://www.iso.org/standard/78907.html)).
- **Choose sections by repository type, not by universal template.** A library
  needs installation/usage/API; a dataset needs provenance/schema/license; a
  methodology or documentation-first repo needs concept/grounding/how to adopt.
  **[empirical]** README patterns are domain-specific — what serves a library
  is ineffective for a dataset — and documentation linters capture form while
  missing substance ([McNutt et al., 2026](https://arxiv.org/html/2603.00331)
  — user study N=11). **[practitioner]** Templates
  ([standard-readme](https://github.com/richardlitt/standard-readme),
  [Art of README](https://github.com/hackergrrl/art-of-readme)) enter as
  reminder checklists: a section with no audience question behind it does not
  enter because the template lists it.
- **Show a minimal working example before or alongside each central
  capability** — code that runs, a command that executes, an observable
  before/after — and test it against the current repository. **[empirical]**
  Studying examples is the second most cited reason for consulting docs at
  adoption time (12.58%).
- **Every trust signal must measure something.** Badges that assess (build,
  coverage) correlate with the signaled quality; badges that merely declare
  intention do not (**[empirical]**
  [Trockman et al., ICSE 2018](https://cmustrudel.github.io/papers/icse18badges.pdf)),
  and raw popularity signals are manipulable
  ([~6M suspected fake stars](https://arxiv.org/html/2412.13459v2)). Give every
  quality claim an anchor that resolves; remove the ones that cannot get one.
  Declare project status honestly, including "experimental" and "not
  maintained" — status is the most absent content category in the Prana et al.
  data (present in 21.4% of READMEs).

### 3. Keep it alive

- When a change touches behavior the README describes, sweep the README for
  claims the change falsified; the correction ships with the change, not with a
  future grand revision. The observable output is a README diff accompanying
  the diff that invalidated it.
- **Curate by subtraction.** Apply the subtraction test per section: which
  audience question goes unanswered without it? Depth content migrates to
  dedicated docs with a link — **[practitioner]** the README is the entry point
  and map; tutorials, reference, and deep explanation live in their own
  documents ([Diátaxis](https://diataxis.fr/)). A revision that only adds is
  the protocol not applied.
- **Localize with declared audience and cost, not by default.** **[empirical]**
  Repositories with non-English content tend to receive fewer stars,
  contributors, and comments ([arXiv 2602.19446](https://arxiv.org/html/2602.19446v1));
  **[practitioner]** the mature convention is a main README in English plus
  suffixed variants (`README.pt-BR.md`, BCP 47). Every variant enters the
  synchronization scope of step 3: a variant that lags the main file repeats
  the stale-claim failure for a second audience.

## Anti-patterns

1. **Mechanics without why.** Installation and usage present, purpose absent —
   the measured default (74.3% of READMEs omit "why").
2. **Author's-summary ordering.** Architecture, history, and module layout
   before what-is-this and how-do-I-start.
3. **Template compliance.** Sections that exist because the template lists
   them, with no audience question behind them.
4. **Decorative signals.** "Blazing fast", "production-ready", vanity badges —
   claims that assess nothing and resolve to nothing.
5. **Insider jargon.** Terms only meaningful from inside the project, presented
   to a first-time visitor.
6. **The stale claim.** A promise the repository no longer keeps, left in place
   because removal feels like regression.
7. **The bloated README.** Full documentation stuffed into the front page; the
   reader has attention for 20–28% of the words, and each addition spends it.

## Before / after

| # | Before | After | Rule |
|---|--------|-------|------|
| 1 | "A modular, extensible, next-generation framework leveraging cutting-edge parsing technology." | "Parses EDI invoices into typed JSON. For teams replacing hand-written EDI parsers; not an EDI *editor*." | Fundamentals: what/why/for whom, no inflated adjectives |
| 2 | Section order: Architecture → Modules → History → Installation | Section order: What & why → Quick start → Example → Status → Deeper docs (links) | Visitor's decision sequence in the first third |
| 3 | "Blazing fast and battle-tested." | "Processes ~50k records/s on the benchmark in `bench/` (CI-run); API stable since v2.0." | Signals that measure; claims with anchors |
| 4 | "Supports Node 14+" (project dropped Node 14 two releases ago) | Claim updated with the change that dropped it — or removed, with the support matrix linked from CI | Synchronization; removal over stale promise |

## Self-check (run as a separate critique pass)

- [ ] Four fundamentals answered and anchored in the repository — or explicitly
      asked of the author?
- [ ] Audience declared, and every assumed term inside its declared vocabulary?
- [ ] Headings plus first third suffice for what / for whom / how to start?
- [ ] Each section answers an identifiable audience question?
- [ ] Every example runs against the current repository? Every signal measures
      something?
- [ ] What the revision removed is recorded (in history or the review), and the
      revision is not addition-only?

## When NOT to apply

- **Deep documentation** — tutorials, how-to guides, API reference. The README
  links to these; writing them is a different task with different structure
  (Diátaxis).
- **Changelogs, code comments, commit messages** — different artifacts with
  their own conventions.
- **Prose style in general** — `sober-prose` covers rhetorical bias in any
  expository text and legitimately fires alongside this skill on README prose;
  this skill governs content, structure, and audience fit, not sentence-level
  style.
- **Compressing an agent's own answers** — that is `verbosity-reduction`; this
  skill's subtraction test applies to README sections against audience
  questions, not to response padding.
- **Marketing copy or persuasive landing pages** — the evidence here concerns
  informing an adoption decision, not persuading; adoption promises are out of
  scope anyway (all form–popularity evidence is correlational).

## Evidence status

The quantitative evidence on READMEs is correlational — no study found
establishes that a structure causes adoption — and the perception studies have
small samples (29 survey responses; N=11 user study), marked above where
cited. No evidence was found on ideal README length; what this skill says
about size derives from scanning evidence, not direct measurement. The
efficacy of this skill itself is an ex ante hypothesis with cited grounding:
no with/without pair has been measured.
