# Operação: review-changes

Revisa as mudanças da sessão (uma skill nova ou revisada, ou edições em docs) antes
de commit/PR, no papel de revisor.

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`. Se houver Open
   Session, o trabalho pertence à iteração apontada — os achados serão registrados lá.

2. **Reunir o diff.** Identifique o que mudou (arquivos de skill, README raiz,
   `AGENTS.md`, estado). Compare com a intenção declarada (spec da iteração, se houver).

3. **Revisar contra os critérios** (adaptados de código para skills):
   - **Fidelidade:** a mudança faz o que a spec/iteração pediu, sem escopo a mais.
   - **Convenções:** estrutura de 2 arquivos (`SKILL.md` + `README.md`); `description`
     como gatilho específico e acionável; skill monolíngue; README raiz bilíngue.
   - **Quality Gates:** confira a checklist do `project-definition.md` §6.
   - **Prosa sóbria:** a própria prosa evita floreios (aplica `sober-prose`/`prosa-sobria`).
   - **Fundamentação:** cada afirmação normativa se ancora em fonte.
   - **Escopo/diff:** mudanças mínimas e direcionadas; nada de reescrita desnecessária.

4. **Reportar os achados.** Para cada problema: **Severidade** (bloqueia / deveria /
   opcional), **Local** (arquivo:seção), **Descrição**, **Recomendação**. Se estiver
   tudo certo, diga isso — não invente problemas.

5. **Registrar.** Se houver Open Session, acrescente uma entrada no Session Log da
   iteração. Falha de processo (ex.: gate pulado) entra como `[INCIDENT/P]`, citando
   `methodology/qa-phase.md`.

## Lembretes

- Revisão não é reescrita: aponte, recomende, deixe a decisão com o autor.
- Não há lint/test automático; o "gate" é a checklist dos Quality Gates.
