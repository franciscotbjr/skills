# Operação: update-documentation

Atualiza a documentação do repo depois de uma mudança implementada (skill nova,
revisão ou mudança de convenção).

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre o que for feito no Session Log da iteração.

2. **Percorrer os alvos** (o repo não tem CHANGELOG nem API docs). Para cada um,
   decida se precisa de atualização e produza o conteúdo:
   - **README raiz** — tabela bilíngue (PT/EN) de skills: adicionar/renomear linha;
     manter as contrapartes cruzadas (`prosa-sobria` ↔ `sober-prose`).
   - **README da skill afetada** — descrição, uso, "quando aplica/não aplica",
     referências.
   - **`AGENTS.md`** — apenas se uma convenção mudou (estrutura, bilinguismo, branch,
     Persona, tabela de operações).
   - **`.stateful-spec/project-definition.md`** — se a mudança altera convenções,
     estrutura ou Quality Gates.

3. **Confirmar coerência.** Cross-references PT↔EN resolvem; a tabela do README raiz
   reflete o conjunto real de skills.

## Lembretes

- A prosa da doc segue `sober-prose`/`prosa-sobria`.
- Só documente o que mudou; não reescreva docs que continuam corretos.
