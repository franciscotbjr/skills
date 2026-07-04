# intake / QA — defects & observations from testing

Defects and observations from human / post-delivery testing, captured before they are routed. One
file per item, `kebab-case.md`, with the READY frontmatter (see [`../README.md`](../README.md)).

At triage, each QA item is **routed by type** (the canonical QA phase in `methodology/qa-phase.md`):

- **small / localized** (a tighter `description`, a single before/after pair, a wording fix) →
  direct (applied directly), recorded with root cause + category **E/P/H** + lesson → skill + a
  commit per item;
- **substantial / cross-cutting** (a rule spanning several skills, a contradiction between skills) →
  spec-first (a skill spec or revision plan is written, reviewed, then applied).

A QA item that reveals durable evolution of a skill is promoted to `.stateful-spec/backlog.md` as an
`O-NNN`.

## Example item

```markdown
---
status: ready
title: sober-prose fires on code comments and strips intended emphasis
origin: real use (post-delivery QA)
category: E      # E = engineering defect, P = process gap, H = human/UX call
---

Repro: apply the skill to a file with inline code comments → it rewrites technical notes as prose.
Suspected class: the `description` over-matches (missing "When NOT to apply" for code contexts).
Route: small/localized → direct fix (tighten the trigger) + lesson back to the skill.
```

> `draft` while only observed; `ready` once it has a repro and a suspected class. The `category`
> (E/P/H) field is filled at triage, not at capture.
