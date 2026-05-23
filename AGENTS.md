# AGENTS.md

Zero-code repository of [Agent Skills](https://agentskills.io) — prompt extensions in Markdown. No build, test, lint, or typecheck.

## Skill structure

Each skill is a directory containing exactly two files:

```
skill-name/
  SKILL.md    — YAML frontmatter (name, description) + instructions read by the agent
  README.md   — human-facing docs: brief description, usage, when applies/doesn't, cross-references
```

The `description` field in SKILL.md's frontmatter is the trigger condition — it determines when the agent auto-activates the skill. Keep it specific and actionable.

## Bilingual convention

Root `README.md` and commit messages are bilingual (PT/EN). Individual skills are monolingual — `prosa-sobria` (PT) is the Portuguese equivalent of `sober-prose` (EN). When adding a Portuguese translation, cross-reference its English counterpart in README.md (and vice versa).

## Branch naming

- `skill/<name>` for new skills
- `update/<topic>` for changes

## Ignored

`.prompts/`, `.vscode/`, `.claude/settings.local.json` are gitignored — used for local drafts and editor config.
