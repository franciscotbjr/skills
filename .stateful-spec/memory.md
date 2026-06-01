# Memory — `skills`

> Estado vivo do projeto. Leia este arquivo **primeiro** ao iniciar ou retomar
> uma sessão. Atualize-o ao salvar ou encerrar uma sessão.

## Resumo do projeto

- **Nome:** skills
- **Descrição:** repositório zero-code de Agent Skills (extensões em Markdown)
  voltadas a fidelidade linguística e qualidade de prosa.
- **Última atualização:** 2026-05-31
- **Status:** Active development

## Active Work

_(nenhuma — aguardando a próxima tarefa/iteração)_

## Open Session

_(nenhuma sessão aberta)_

## Recent Completions

| # | Nome | Tipo | Concluída em |
| - | ---- | ---- | ------------ |
| 1 | sync-source-skills | Import | 2026-05-31 |
| 2 | include-methodological-rigor | Include | 2026-05-31 |

## Key Decisions

- Repositório **documentation-only**: não há código, build, testes automáticos
  nem CI. "Qualidade" é medida por convenções de autoria (ver `project-definition.md`).
- Onboarding stateful-spec adaptado ao domínio de autoria de skills (2026-05-31).
- **Operations** restritas ao ciclo de sessão (`start/end/resume/save-session`);
  a autoria de skills permanece guiada pela Persona e pelas skills existentes.
- Corpo canônico das operations em `.stateful-spec/operations/*.md` (PT-BR);
  `.claude/commands/` e `.opencode/commands/` são wrappers finos.
- Metodologia completa **referenciada** no upstream
  (github.com/franciscotbjr/stateful-spec); o ciclo adaptado vive no
  `project-definition.md`. Não há `.stateful-spec/methodology/` local.
- Skills do vault pessoal (`D:\franciscotbjr\Documents\Explorações\.claude\skills`)
  são a fonte canônica de atualizações das skills; o repo público recebe
  importações periódicas (2026-05-31).
- **`prosa-completa`** (PT) é skill agregadora das três skills de qualidade de
  prosa; não as substitui — é atalho de invocação combinada com resolução de
  conflitos entre elas (2026-05-31).
- **`prosa-sobria`** permanece como contraparte PT da `sober-prose`; a agregação
  fica na `prosa-completa`, não nela (2026-05-31).
- **`methodological-rigor`** (EN): skill de auditoria crítica de argumentação,
  metodologia e robustez epistêmica. Aplica persona de Crítico Implacável que
  questiona premissas não declaradas, vieses estruturais, circular reasoning,
  hipocrisia epistêmica e normativa. Complementar às skills de prosa — o escopo
  é a estrutura do argumento, não a forma da expressão (2026-05-31).

## Constraints & Reminders

- README raiz e mensagens de commit são **bilíngues (PT/EN)**; skills são
  **monolíngues**.
- Preservar integralmente a **Persona** e as convenções do `AGENTS.md`.
- A própria prosa do repo (READMEs, docs) segue `sober-prose`/`prosa-sobria`:
  sem floreios retóricos.
- Toda afirmação normativa numa skill se ancora em fonte (fundamentação).
- Nomenclatura de branch: `skill/<nome>` (nova skill), `update/<tópico>` (mudança).

## History Index

| ID | Nome | Tipo | Status | Arquivo |
| -- | ---- | ---- | ------ | ------- |
| 1  | sync-source-skills | Import | completed | [001-sync-source-skills.md](history/001-sync-source-skills.md) |
| 2  | include-methodological-rigor | Include | completed | [002-include-methodological-rigor.md](history/002-include-methodological-rigor.md) |
