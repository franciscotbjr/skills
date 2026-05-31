# Operação: start-session

Inicia uma sessão de trabalho com contexto carregado a partir do estado persistido.

## Passos

1. **Carregar contexto.** Leia, nesta ordem:
   - `.stateful-spec/memory.md` — estado atual, Active Work, Open Session, Key
     Decisions, Constraints.
   - `.stateful-spec/project-definition.md` — identidade, convenções, Quality
     Gates e o ciclo de fases.
   - `.stateful-spec/history/` — iterações passadas e em andamento (se houver).
   - Se `.stateful-spec/` não existir, ofereça rodar o onboarding antes de seguir.

2. **Resumir o estado.** Em 5–10 linhas, apresente: status do projeto, Active Work
   e Open Session (se houver), iterações recentes e as Constraints pertinentes.

3. **Perguntar o foco.** Pergunte ao usuário o que ele quer fazer nesta sessão:
   continuar um trabalho ativo, iniciar uma nova tarefa (skill nova, revisão de
   uma existente, mudança em docs/convenções) ou apenas consultar o estado.

4. **Abrir o trabalho.** Conforme a resposta:
   - **Nova tarefa:** determine o próximo número em `.stateful-spec/history/` e crie
     `NNN-<nome-kebab>.md` com: Tipo (skill nova / revisão / chore), Status
     (in-progress), descrição, critérios de aceitação (checkboxes) e tarefas
     (checkboxes). Atualize `memory.md` (Active Work + Open Session + History Index).
   - **Continuar trabalho ativo:** retome a iteração na fase apropriada do ciclo.
   - Recomende a fase inicial do ciclo (Analisar para algo novo; pode pular para
     Redigir se a tarefa já estiver bem entendida).

## Lembretes

- Toda autoria de skill segue a Persona e as convenções do `AGENTS.md`.
- Não há build/test/lint: a "verificação" é a checklist dos Quality Gates.
