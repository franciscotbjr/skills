# Operação: save-session

Preserva o progresso da sessão atual no estado persistido, para retomada futura.

## Passos

1. **Revisar o trabalho da sessão.** Peça ao usuário um resumo do que foi feito ou
   infira da conversa: tarefas concluídas, arquivos alterados, decisões tomadas e
   obstáculos encontrados.

2. **Ler o estado atual.** Examine `.stateful-spec/memory.md` e as iterações em
   `.stateful-spec/history/` para identificar o trabalho ativo. Se houver Open
   Session, a iteração apontada é o alvo da atualização.

3. **Tratar iteração ausente.** Se houve trabalho substantivo sem iteração
   correspondente, crie uma iteração retroativa refletindo o que foi feito ou, como
   fallback, atualize `memory.md` diretamente.

4. **Atualizar a iteração.** No arquivo `NNN-<nome>.md` ativo:
   - marque as tarefas concluídas;
   - acrescente tarefas recém-descobertas;
   - registre decisões;
   - se a iteração tiver um **Session Log** (ver o template
     `.stateful-spec/templates/implementation/iteration.md`), acrescente uma entrada
     `AAAA-MM-DD HH:MM | <operação> | <resumo>`; falha de processo entra como `[INCIDENT]`;
   - ajuste o Status (done / blocked / in-progress).

5. **Atualizar a memória.** Em `memory.md`: atualize Active Work (status ou promova
   para Recent Completions), registre decisões relevantes em Key Decisions e novas
   Constraints. Atualize o campo "Última atualização" com a data atual.

6. **Confirmar.** Resuma as alterações e confirme que `memory.md` e a iteração
   ficaram consistentes.

## Lembretes

- Não há etapa de commit obrigatória aqui; se o usuário desejar versionar, siga a
  convenção de commit bilíngue do repo (regra global: PT, ≤300 caracteres, 1 linha).
