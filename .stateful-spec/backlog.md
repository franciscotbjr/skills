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

<!--
Estados:
- new       — promovida para o backlog, ainda não avaliada.
- triaged   — avaliada; aguardando destino (slot de roadmap / iteração) ou descarte.
- promoted  — virou trabalho de roadmap/iteração (Destino diz qual).
- discarded — fechada sem executar; Destino registra o porquê.
-->
