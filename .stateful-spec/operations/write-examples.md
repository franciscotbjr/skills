# Operação: write-examples

Redige os pares antes/depois e a checklist de auto-checagem de uma skill. Em um
projeto de skills, isto é ao mesmo tempo "implementar" e "verificar" (análogo a
escrever testes).

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre no Session Log da iteração.

2. **Um par por anti-padrão.** Para cada anti-padrão da spec, escreva um par
   antes/depois. Cada par demonstra **exatamente uma** regra e usa um caso realista
   (bilíngue EN→pt-BR quando fizer sentido para a skill).

3. **Checklist de auto-checagem.** Acrescente à skill sua própria checklist de
   verificação (o que confirmar antes de considerá-la aplicada).

4. **Validar o gatilho.** Liste casos que **devem** disparar a skill e casos que **não
   devem** — confirme que a `description` cobre os primeiros e exclui os segundos.

5. **Prosa sóbria e fundamentação.** A própria prosa dos exemplos evita floreios; toda
   afirmação normativa se mantém ancorada em fonte.

6. **Respeitar a estrutura.** Tudo vive em `SKILL.md` (instruções/exemplos) e
   `README.md` (docs para humanos) — nada além dos dois arquivos.

## Lembretes

- Um par que demonstra duas regras ao mesmo tempo deve ser dividido em dois.
- Próximos passos: `diagnose-skill` se algo não dispara como esperado; atualizar a
  tabela do README raiz via `update-documentation`.
