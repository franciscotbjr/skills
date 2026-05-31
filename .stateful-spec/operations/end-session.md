# Operação: end-session

Encerra a sessão atual de forma limpa, garantindo que o estado fique persistido.

## Passos

1. **Salvar primeiro.** Execute o fluxo de `save-session`: revise o trabalho,
   atualize a iteração ativa e `memory.md`.

2. **Fechar a Open Session.** Em `memory.md`, limpe o campo "Open Session"
   (nenhuma sessão aberta).

3. **Resolver a iteração ativa.** Se a iteração foi concluída:
   - marque seu Status como `done`;
   - mova-a de Active Work para Recent Completions (com a data);
   - atualize o Status no History Index.
   Caso contrário, deixe-a em Active Work com o status corrente (in-progress / blocked).

4. **Resumo de saída.** Em poucas linhas, registre onde o trabalho parou e qual o
   próximo passo sugerido, para facilitar a retomada via `resume-session`.

## Lembretes

- Atualize o campo "Última atualização" de `memory.md` com a data atual.
- Se o usuário quiser versionar o estado, siga a convenção de commit bilíngue do repo.
