# intake / Discovery — open questions & spikes

Research notes, open questions, and spike results that precede a decision. One file per question,
`kebab-case.md`, with the READY frontmatter (see [`../README.md`](../README.md)). A resolved
discovery either feeds a decision (recorded in the relevant iteration / ADR) or is promoted to
`.stateful-spec/backlog.md` as an `O-NNN` if it surfaces durable work.

## Example item

```markdown
---
status: ready
title: Do prosa-sobria and verbosity-reduction overlap enough to merge?
origin: discovery (spike)
---

Question: do the two prose skills catch the same anti-patterns, or are they complementary? Findings
so far: sober-prose targets rhetorical bias, verbosity-reduction targets padding — they overlap on
adjective inflation but differ elsewhere. Next step: map their anti-pattern lists side by side.
Collects the evidence before re-triaging.
```

> Use `draft` while still gathering; `ready` once the question is well-posed and the next step is
> clear. Long-lived opportunities go to `.stateful-spec/backlog.md`; one-off answers go to the
> iteration record.
