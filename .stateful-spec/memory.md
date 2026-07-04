# Memory — `skills`

> Estado vivo do projeto. Leia este arquivo **primeiro** ao iniciar ou retomar
> uma sessão. Atualize-o ao salvar ou encerrar uma sessão.

## Resumo do projeto

- **Nome:** skills
- **Descrição:** repositório zero-code de Agent Skills (extensões em Markdown)
  voltadas a fidelidade linguística e qualidade de prosa.
- **Última atualização:** 2026-07-04
- **Status:** Active development

## Active Work

_(nenhuma iteração ativa — candidatas naturais: aplicar os protocolos G1–G3/R1–R4
do `persona.md` numa revisão do catálogo existente, ou colher os sinais ex post
da seção 9 do `persona-reference.md`)_

## Open Session

_(nenhuma sessão aberta)_

## Recent Completions

| # | Nome | Tipo | Concluída em |
| - | ---- | ---- | ------------ |
| 1 | sync-source-skills | Import | 2026-05-31 |
| 2 | include-methodological-rigor | Include | 2026-05-31 |
| 3 | upgrade-stateful-spec | chore | 2026-07-04 |
| 4 | personas-especialistas | chore | 2026-07-04 |
| 5 | aplicar-personas | chore | 2026-07-04 |

## Key Decisions

- Repositório **documentation-only**: não há código, build, testes automáticos
  nem CI. "Qualidade" é medida por convenções de autoria (ver `project-definition.md`).
- Onboarding stateful-spec adaptado ao domínio de autoria de skills (2026-05-31).
- **Full upgrade da metodologia** (2026-07-04, iteração 003): revertidas as decisões
  "enxutas" anteriores. Adotados `.stateful-spec/methodology/` local (aparado para o
  tipo `skills`, EN), `templates/`, `intake/` + `backlog.md`, e o conjunto **completo
  de 11 operations** do tipo skills. Objetivo: estrutura completa da metodologia
  versionada com o repo.
- **Operations = 11 (single-source):** ciclo (`start/resume/save/end-session`) +
  `review-changes`, `update-documentation`, `write-commit-message` + `create-skill-spec`,
  `write-examples`, `diagnose-skill`, `revise-skill`. Corpos canônicos PT-BR em
  `.stateful-spec/operations/*.md`; `.claude/commands/` e `.opencode/commands/` são
  wrappers finos (paridade dual-agent).
- **Ops de software/studies ficam fora** (2026-07-04): projeto `skills` não carrega
  `create-technical-spec`, `write-tests`, `debug-issue`, `refactor-code` nem as ops de
  studies. O `multi-agent-flow` (fluxo de time) não é copiado; `qa-phase` entra por ser
  type-agnostic e referenciado por `intake/QA`.
- **Idioma misto:** state files e operations em PT-BR (voz do repo); `methodology/`,
  `templates/` e READMEs de `intake/` em EN (espelham o upstream como referência).
- **`.claude/settings.json` ignorado** (2026-07-04): cache local de permissões da
  sessão, não é config de projeto; adicionado ao `.gitignore` junto de
  `settings.local.json` para não ser commitado por engano.
- Skills do vault pessoal (`D:\franciscotbjr\Documents\Explorações\.claude\skills`)
  são a fonte canônica de atualizações das skills; o repo público recebe
  importações periódicas (2026-05-31).
- **`prosa-completa`** (PT) é skill agregadora das três skills de qualidade de
  prosa; não as substitui — é atalho de invocação combinada com resolução de
  conflitos entre elas (2026-05-31).
- **`prosa-sobria`** permanece como contraparte PT da `sober-prose`; a agregação
  fica na `prosa-completa`, não nela (2026-05-31).
- **Personas consolidadas no repo** (2026-07-04, iteração 005): modelo
  stateful-spec — `.stateful-spec/persona.md` (system prompt operacional das
  Personas A base + B extensão) + `persona-reference.md` (cópia verbatim da
  pesquisa do vault; repo público não pode ancorar em caminho local) + binding
  ambiente fino no `AGENTS.md`. A Persona antiga (credencial + listas de
  competências) foi substituída: o formato declarativo não adiciona competência
  (Zheng et al.; Playing Pretend) e o conteúdo redundante reprovou no teste de
  subtração — o confronto completo está na iteração 005.
- **`methodological-rigor`** (EN): skill de auditoria crítica de argumentação,
  metodologia e robustez epistêmica. Aplica persona de Crítico Implacável que
  questiona premissas não declaradas, vieses estruturais, circular reasoning,
  hipocrisia epistêmica e normativa. Complementar às skills de prosa — o escopo
  é a estrutura do argumento, não a forma da expressão (2026-05-31).

## Constraints & Reminders

- README raiz e mensagens de commit são **bilíngues (PT/EN)**; skills são
  **monolíngues**.
- Preservar a **Persona** (binding no `AGENTS.md` + `.stateful-spec/persona.md`,
  racional em `persona-reference.md`) e as convenções do `AGENTS.md`.
- A própria prosa do repo (READMEs, docs) segue `sober-prose`/`prosa-sobria`:
  sem floreios retóricos.
- Toda afirmação normativa numa skill se ancora em fonte (fundamentação).
- Nomenclatura de branch: `skill/<nome>` (nova skill), `update/<tópico>` (mudança).

## History Index

| ID | Nome | Tipo | Status | Arquivo |
| -- | ---- | ---- | ------ | ------- |
| 1  | sync-source-skills | Import | completed | [001-sync-source-skills.md](history/001-sync-source-skills.md) |
| 2  | include-methodological-rigor | Include | completed | [002-include-methodological-rigor.md](history/002-include-methodological-rigor.md) |
| 3  | upgrade-stateful-spec | chore | completed | [003-upgrade-stateful-spec.md](history/003-upgrade-stateful-spec.md) |
| 4  | personas-especialistas | chore | completed | [004-personas-especialistas.md](history/004-personas-especialistas.md) |
| 5  | aplicar-personas | chore | completed | [005-aplicar-personas.md](history/005-aplicar-personas.md) |
