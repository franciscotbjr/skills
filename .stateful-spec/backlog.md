# Backlog

> **Oportunidades** triadas — trabalho além da iteração atual. O formato canônico está
> definido em [`methodology/backlog.md`](methodology/backlog.md). Este arquivo
> (`.stateful-spec/backlog.md`) é a instância do projeto: uma linha por oportunidade,
> numeração `O-NNN` gerida aqui (sequencial, estável, nunca reutilizada).
>
> Um defeito de uma skill (disparo indevido, ausência de disparo, orientação ruim) entra
> primeiro em `intake/QA/` e só vira `O-NNN` se revelar evolução durável. Ideias novas de
> skill entram em `intake/Backlog/`; questões abertas, em `intake/Discovery/`.

<!-- O-NNN alocado na triagem. Estados: new → triaged → promoted | discarded. -->

| ID | Descrição | Origem | Status | Destino |
|------|-----------|--------|--------|---------|
| O-001 | Pesquisar e estruturar duas personas especialistas para as evoluções do repo — (1) especialista em Skills para agentes de IA de propósito geral; (2) especialista em vieses linguísticos de outputs de LLMs. Pesquisa pura primeiro no vault (Jandi), nos moldes da persona SDD do stateful-spec; sem alterar as skills existentes nesta etapa. | idea (`intake/Backlog/prd.md`) | promoted | iteração [004-personas-especialistas](history/004-personas-especialistas.md) |
| O-002 | Aplicar as personas pesquisadas no repo: derivar `persona.md` operacional do doc do vault (Persona A base + Persona B extensão) e fazer o binding no `AGENTS.md`, confrontando a Persona atual com a pesquisa. Sem alterar as skills existentes. | idea (`intake/Backlog/aplicar-personas.md`) | promoted | iteração [005-aplicar-personas](history/005-aplicar-personas.md) |
| O-003 | Criar a skill `readme-writer` (especialista em escrita de README files): pesquisa pura primeiro no vault Jandi (rigor conceitual + bases empíricas), nos moldes da pesquisa das personas (O-001), com questionamento exaustivo (uma pergunta por vez) antes da execução. Sem alterar as skills existentes nesta etapa. | idea (`intake/Backlog/prd.md`) | promoted | iteração [006-readme-writer](history/006-readme-writer.md) |
| O-004 | Consolidar a skill `readme-writer` no catálogo: derivar `SKILL.md` + `README.md` (EN) do doc de pesquisa da 006 (vault Jandi), com gatilho passando G1–G3 e atualização do README raiz. Sem alterar as skills existentes nem criar a contraparte PT-BR nesta etapa. | idea (`intake/Backlog/consolidar-readme-writer.md`) | promoted | iteração [007-consolidar-readme-writer](history/007-consolidar-readme-writer.md) |

<!--
Estados:
- new       — promovida para o backlog, ainda não avaliada.
- triaged   — avaliada; aguardando destino (slot de roadmap / iteração) ou descarte.
- promoted  — virou trabalho de roadmap/iteração (Destino diz qual).
- discarded — fechada sem executar; Destino registra o porquê.
-->
