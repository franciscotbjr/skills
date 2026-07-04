# 003 — upgrade-stateful-spec

- **Início:** 2026-07-04
- **Conclusão:** 2026-07-04
- **Status:** completed
- **Tipo:** chore
- **Fase:** Especificar → Redigir → Verificar

## Objetivo

Executar `onboard-existing` (upstream stateful-spec) em modo **full upgrade**: trazer
a estrutura completa da metodologia para dentro do repo (revertendo o setup enxuto
anterior), adaptada ao tipo de projeto **skills** e à voz PT-BR do repositório.

Traz `methodology/` local (skills-only trim, EN), templates de skills, a caixa de
entrada `intake/` + `backlog.md`, e amplia o conjunto de operations de 4 (ciclo de
sessão) para **11** (single-source: corpo canônico em `operations/`, wrappers finos
em `.claude/` e `.opencode/`). Mantém a Persona e todas as convenções do `AGENTS.md`.

## Critérios de aceite

- [x] `.stateful-spec/methodology/` presente (skills-trim, **sem** `multi-agent-flow.md`).
- [x] `.stateful-spec/templates/` com `skill-spec.md`, `iteration.md`, `verification-plan.md` (só subseção skills).
- [x] `.stateful-spec/intake/` (4 READMEs) + `.stateful-spec/backlog.md` (vazio, cabeçalhos PT-BR).
- [x] `operations/` com 11 arquivos; `.claude/commands/` e `.opencode/commands/` com 11 cada, em paridade.
- [x] Nenhuma operation de software/studies presente (grep negativo).
- [x] Nenhuma referência pendente a `multi-agent-flow` em `.stateful-spec/`.
- [x] `AGENTS.md` lista exatamente as 11 ops; Persona e convenções preservadas.
- [x] `project-definition.md` e `memory.md` reconciliados (rótulo skills, metodologia local, Key Decisions atualizadas).

## Tarefas de implementação

- [x] Copiar/trimmar `methodology/` (project-types, roles, qa-phase, history-archiving trimados; demais como-está).
- [x] Copiar templates de skills (`skill-spec`, `iteration`, `verification-plan` skills-only).
- [x] Criar `intake/` + `backlog.md`.
- [x] Escrever 7 novas operations PT-BR + augment das 4 existentes (passos de intake/incident).
- [x] Criar 14 wrappers nativos.
- [x] Augment `project-definition.md` + `AGENTS.md`.
- [x] Reconciliar `memory.md` e fechar esta iteração.

## Decisões

| Decisão | Justificativa | Data |
|---------|---------------|------|
| Full upgrade (reverter setup enxuto) | Usuário quer a estrutura completa da metodologia local | 2026-07-04 |
| Idioma misto (state PT-BR, methodology/templates EN) | Preserva a voz do repo; espelha o upstream como referência | 2026-07-04 |
| Single-source (corpos em `operations/`, wrappers finos) | Mantém a convenção atual; uma fonte de verdade | 2026-07-04 |
| Ambos os agentes (Claude Code + OpenCode) | Preserva a paridade dual-agent já existente | 2026-07-04 |
| Skills-only trim; `qa-phase` entra, `multi-agent-flow` sai | `qa-phase` é type-agnostic e referenciado por `intake/QA`; `multi-agent-flow` é fluxo de time | 2026-07-04 |
| Ops de software/studies fora | Restrição do usuário: projeto skills não carrega ops de outros tipos | 2026-07-04 |

## Notas

- Referências pendentes a limpar após remover `multi-agent-flow.md`: `roles.md`,
  `qa-phase.md` (linha de roteamento), `history-archiving.md`, `intake/README.md` e
  `intake/QA/README.md` (roteamento single- vs multi-agent → simplificar).
