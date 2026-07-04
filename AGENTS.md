# AGENTS.md

Zero-code repository of [Agent Skills](https://agentskills.io) — prompt extensions in Markdown. No build, test, lint, or typecheck.

## Stateful Spec

Este repositório adota a metodologia [stateful-spec](https://github.com/franciscotbjr/stateful-spec)
(adaptada ao domínio de autoria de skills) para manter estado e contexto entre
sessões e agentes.

- **Leia primeiro:** [`.stateful-spec/memory.md`](.stateful-spec/memory.md) — estado
  atual, trabalho ativo, decisões e restrições.
- **Convenções e ciclo:** [`.stateful-spec/project-definition.md`](.stateful-spec/project-definition.md)
  — identidade, Quality Gates (convenções) e o ciclo de fases adaptado
  (Analisar → Planejar → Especificar → Redigir → Verificar).
- **Metodologia:** local em [`.stateful-spec/methodology/`](.stateful-spec/methodology/project-types.md),
  aparada para o tipo de projeto `skills` (EN); o upstream é a fonte de referência.
- **Caixa de entrada:** [`.stateful-spec/intake/`](.stateful-spec/intake/README.md)
  (Backlog / Discovery / QA) alimenta o [`.stateful-spec/backlog.md`](.stateful-spec/backlog.md)
  (`O-NNN`, triado em `start`/`resume`/`end-session`). Ver `methodology/backlog.md`.

### Operações

Os corpos canônicos vivem em `.stateful-spec/operations/`; os comandos nativos abaixo
são wrappers finos (Claude Code e OpenCode, mesma sintaxe `/<nome>`). São as **11
operações do tipo skills** — nenhuma operação de software ou studies.

**Ciclo de sessão**

| Comando | O que faz |
| ------- | --------- |
| `/start-session`  | Inicia a sessão, carrega o estado e tria a caixa de entrada |
| `/resume-session` | Retoma o trabalho com o contexto persistido |
| `/save-session`   | Salva o progresso em `memory.md` e na iteração ativa |
| `/end-session`    | Encerra a sessão, persistindo o estado |

**Compartilhadas**

| Comando | O que faz |
| ------- | --------- |
| `/review-changes`       | Revisa as mudanças (skill/docs) antes de commit/PR |
| `/update-documentation` | Atualiza README raiz, README da skill e docs de estado |
| `/write-commit-message` | Escreve o commit na convenção bilíngue PT/EN, 1 linha, ≤300 |

**Autoria de skills**

| Comando | O que faz |
| ------- | --------- |
| `/create-skill-spec` | Especifica uma skill nova (fases Analisar + Especificar) |
| `/write-examples`    | Redige pares antes/depois e checklist de auto-checagem |
| `/diagnose-skill`    | Diagnostica uma skill que dispara errado ou não dispara |
| `/revise-skill`      | Reestrutura/enxuga uma skill sem mudar intenção nem gatilho |

Iterações de trabalho são rastreadas em `.stateful-spec/history/NNN-<nome>.md`.

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

## Persona

Agentes trabalhando neste repositório operam sob as duas personas definidas em
[`.stateful-spec/persona.md`](.stateful-spec/persona.md): a **Persona A**, autora e
curadora de Agent Skills (projetar o gatilho, redigir o corpo, avaliar e curar), e a
**Persona B**, que herda A e acrescenta o domínio dos vieses linguísticos de outputs
de LLMs. O binding é **ambiente** (toda sessão): A cobre qualquer autoria ou revisão
de skill; B se aplica quando o objeto da skill é a própria linguagem do modelo — o
caso das skills de prosa do catálogo (`prosa-sobria`/`sober-prose`, `pt-br-fullness`,
`verbosity-reduction`, `prosa-completa`); `methodological-rigor` (estrutura de
argumento, não forma da expressão) fica sob A. O peso dos protocolos escala com o
tamanho da tarefa — uma correção trivial não paga o custo integral. Racional e fontes
vivem em [`.stateful-spec/persona-reference.md`](.stateful-spec/persona-reference.md)
— consulte sob demanda, nunca em leitura integral por rotina. **Sensor:** entregáveis
de autoria (skill nova, revisão, diagnóstico) passam pelo checklist de saída do
`persona.md` (§9) em passo separado de crítica, com o resultado registrado no Session
Log da iteração aberta.
