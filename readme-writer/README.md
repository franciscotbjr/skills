# readme-writer

A skill that guides writing, restructuring, and reviewing README files — the
front page of a repository. It extracts the project's fundamentals (what it is,
why it exists, who it serves, what state it is in), designs the file for a
scanning reader, and keeps it synchronized with the repository. Every normative
rule in the skill is anchored in a cited source, with empirical evidence
distinguished from practitioner prescription.

## Usage

The AI agent activates the skill automatically when the task involves creating
or revising a README. To invoke directly:

```
/readme-writer
```

## When it applies

- Writing a README from scratch for a repository, library, tool, dataset, or
  documentation-first project
- Auditing an existing README for first impressions, structure, and audience fit
- Choosing or reordering README sections, adding badges or a quick start
- Checking a README against the current state of the repository after changes
- Deciding whether and how to localize a README

## When it does not apply

- Deep documentation: tutorials, how-to guides, API reference (the README links
  to these; writing them is a different task)
- Changelogs, code comments, or commit messages
- Sentence-level prose style — that is [sober-prose](../sober-prose/), which
  legitimately fires alongside this skill on README prose
- Compressing an agent's own responses — that is
  [verbosity-reduction](../verbosity-reduction/)
- Marketing copy or persuasive landing pages

## Grounding

The skill condenses the research consolidated in iteration 006 of this
repository's stateful-spec history: empirical studies on README content and
adoption (Prana et al. 2019; Wang, Wang & Chen 2023; Trockman et al. 2018;
Steinmacher et al.), reading behavior (Nielsen Norman Group), plain language
(ISO 24495-1:2023), and practitioner frameworks (Diátaxis, standard-readme,
Art of README) — sources linked inline in [SKILL.md](SKILL.md). The evidence is
correlational and the skill's own efficacy is an ex ante hypothesis; the
"Evidence status" section of SKILL.md states these limits.
