# intake / Backlog — inbound ideas

Raw feature/improvement ideas not yet shaped into a numbered opportunity. One file per idea,
`kebab-case.md`, with the READY frontmatter (see [`../README.md`](../README.md)). At triage, a
`ready` item is promoted into `.stateful-spec/backlog.md` as a stable `O-NNN` entry.

## Example item

```markdown
---
status: draft
title: New skill for pt-BR pronoun placement (ênclise/próclise)
origin: idea
---

A skill that corrects clitic pronoun placement in pt-BR generation (próclise vs ênclise), a gap
`pt-br-fullness` touches but does not fully cover. Mirrors the anti-pattern → before/after → "When
NOT to apply" pattern of the existing skills. Shape the scope (which cases, EN counterpart or not)
before promoting to O-NNN.
```

> `draft` until shaped; flip to `ready` when it is concrete enough to triage. Do **not** assign an
> `O-NNN` here — numbering belongs to `.stateful-spec/backlog.md`.
