# Project Types

> **Cópia local skills-only.** Este repositório é do tipo **skills**; esta é uma
> versão da referência upstream aparada para conter apenas o tipo `skills`. A
> metodologia completa (todos os tipos) vive no upstream
> `github.com/franciscotbjr/stateful-spec`. O Project Type é registrado em
> `project-definition.md` (Project Identity) e determina quais convenções,
> templates e operações se aplicam.

## Registry

| Type | One-liner | Default? |
|------|-----------|----------|
| skills | Repositories of Agent Skills (Markdown prompt extensions; zero-code). | — |

## Detection signals

| Type | Signals |
|------|---------|
| skills | Directories containing `SKILL.md`; `opencode.json` with `skills.paths`; skill `description:` frontmatter; references to agentskills.io. |

## Terminology mapping (what each phase word means)

| Concept | skills |
|---------|--------|
| Artifact | a skill (SKILL.md + README.md) |
| "Implement" (Phase 4) | author the skill prose, before/after pairs, self-check checklist |
| "Tests" | trigger validation + self-check + before/after examples |
| "Quality gates" | structure + trigger + sober-prose + grounding (see skills detail) |
| "Deliver" (Phase 5) | consumed from repo; publish = merge via PR |

## Per-type detail

### skills

A repository of Agent Skills: Markdown prompt extensions, each a directory with
`SKILL.md` (YAML `name`/`description` + instructions) and `README.md`. Zero-code.

- **Detection signals.** Directories containing `SKILL.md`; `opencode.json` with
  `skills.paths`; `description:` frontmatter; references to agentskills.io.
- **Terminology.** *Artifact* = a skill. *Implement* = author the skill prose,
  before/after pairs, self-check checklist. *Tests* = trigger validation +
  self-check + before/after examples. *Deliver* = consumed directly from the repo;
  publish = merge to main via PR.

**project-definition skeleton (skills subsections):**

```markdown
- Project Type: skills
## Stack / Materials — skills
- Format: Markdown + YAML frontmatter (name, description)
- Target agents: [e.g., Claude Code, OpenCode]
- No build, package manager, lint, or CI
## Conventions — skills
- Two files per skill: SKILL.md + README.md
- `description` is the trigger condition — specific and actionable
- Skills are monolingual; root README is bilingual with cross-references
- Content pattern: anti-patterns, before/after pairs, self-check checklist, "When NOT to apply"
## Verification — skills
- Trigger validation (description covers intended cases, excludes the rest)
- Self-check checklist present and satisfied
- Before/after examples demonstrate the rule
- Every normative claim is grounded in a source
## Quality Gates — skills
- [ ] Directory has exactly SKILL.md + README.md
- [ ] `description` specific and actionable
- [ ] Skill monolingual; bilingual counterpart cross-referenced in root README (if any)
- [ ] Anti-patterns, before/after, "When NOT to apply" present
- [ ] Prose follows sober-prose (no rhetorical padding)
- [ ] Claims grounded in sources
- [ ] Root README skill table updated
## Delivery / Distribution — skills
- Consumed directly from the repo (e.g., opencode.json skills.paths)
- Publish = merge to main via PR; no external pipeline
```

- **Spec template:** `skill-spec.md` — Metadata (skill name, language, status);
  Target bias/phenomenon; Trigger (`description` draft); Anti-patterns to cover;
  Before/After examples; "When NOT to apply"; Source grounding; Bilingual
  counterpart (if any); Out of scope.
- **Operations:** lifecycle (`start-session`, `end-session`, `resume-session`,
  `save-session`) + `create-skill-spec`, `write-examples`, `diagnose-skill`,
  `revise-skill`, `review-changes`, `update-documentation`, `write-commit-message`.
- **Verification template:** `verification-plan.md` (before/after coverage +
  self-check).
- **Iteration `Type` values:** new-skill | skill-revision | chore.
- **Generic activity → operation:** *create spec* → `create-skill-spec`;
  *implement/examples* → `write-examples`; *debug* → `diagnose-skill`;
  *refactor/revise* → `revise-skill`; *write tests* → `write-examples` +
  `diagnose-skill` (trigger validation).
- **Preset:** `presets/skills-repo.md` (upstream).

## How the layers use this registry

- **`project-definition.md`** keeps a single section per concept with the active
  type's subsections (Stack / Materials, Conventions, Verification, Quality Gates,
  Delivery).
- **Phase guides** (`phases/04-implement.md`, `phases/05-verify.md`) point here for
  the per-type meaning of "Implement", "Tests", "Quality gates", and "Deliver".
- **Operation prompts** for this repo are the skills set; they live as canonical
  bodies in `.stateful-spec/operations/` with thin native wrappers.
