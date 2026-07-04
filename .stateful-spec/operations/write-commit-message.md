# Operação: write-commit-message

Escreve a mensagem de commit conforme a convenção do repositório.

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre a mensagem gerada no Session Log da iteração.

2. **Reunir as mudanças.** Considere o que está staged **e** o que ainda não está
   (mudanças não adicionadas), para descrever o commit por inteiro.

3. **Redigir a mensagem** na convenção bilíngue do repo:
   - **Uma única linha, ≤ 300 caracteres.**
   - Formato `<PT> | <EN>` — a mesma mensagem em português e inglês, separadas por ` | `.
   - Descreva **o quê** e **por quê**, não o como; foco no efeito da mudança.
   - Imperativo/objetivo (ex.: "Adiciona skill X | Add skill X").

4. **Apresentar.** Mostre a mensagem pronta para uso; não faça o commit sem o usuário
   pedir.

## Lembretes

- Regra global do usuário: commit em 1 linha, ≤ 300 caracteres.
- Convenção do repo (`AGENTS.md`): mensagens de commit são bilíngues PT/EN.
- Nomenclatura de branch relacionada: `skill/<nome>` (nova skill), `update/<tópico>`.
