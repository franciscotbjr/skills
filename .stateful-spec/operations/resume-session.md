# Operação: resume-session

Retoma o trabalho carregando o contexto automaticamente, sem reentrada manual de
informação.

## Passos

1. **Carregar contexto do projeto.** Leia:
   - `.stateful-spec/memory.md` (estado atual, Active Work, Open Session, Constraints).
   - `.stateful-spec/project-definition.md` (convenções, Quality Gates, ciclo de fases).
   - `.stateful-spec/history/` (todas as iterações; identifique a que está in-progress).
   - Se `.stateful-spec/` não existir, ofereça rodar o onboarding.

2. **Resumir o estado atual.** Em 5–10 linhas: Active Work e seu status, Open
   Session (se houver), progresso da iteração aberta, Constraints e conclusões
   recentes.

3. **Perguntar o próximo passo.** Ofereça opções contextuais: continuar a iteração
   ativa, iniciar algo novo ou encerrar iterações já concluídas.

4. **Prosseguir.** Conforme a resposta:
   - Retomar a iteração ativa na fase apropriada do ciclo (Analisar → Planejar →
     Especificar → Redigir → Verificar).
   - Criar nova iteração `.stateful-spec/history/NNN-<nome>.md` e registrar em
     `memory.md`.
   - Encerrar iterações concluídas (mover de Active Work para Recent Completions).

## Lembretes

- Mantenha `memory.md` atualizado ao longo da sessão.
- A autoria segue a Persona; a verificação são os Quality Gates do project-definition.
