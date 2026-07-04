# Operação: create-skill-spec

Produz a especificação de uma skill nova antes de escrevê-la. Combina as fases
Analisar e Especificar do ciclo. Usa o template
`.stateful-spec/templates/specification/skill-spec.md`.

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre a spec no Session Log da iteração.

2. **Identificar o alvo.** Delimite com precisão o viés ou fenômeno linguístico que a
   skill corrige — o que o agente faz de errado (ou deixa de fazer) que esta skill
   conserta. Veja como as skills de referência já tratam fenômenos vizinhos.

3. **Rascunhar o gatilho (`description`).** Deve cobrir os casos pretendidos e excluir
   o resto — específico e acionável, pois determina a auto-ativação.

4. **Listar os anti-padrões** concretos que a skill precisa capturar.

5. **Propor pares antes/depois** — pelo menos dois, cada par demonstrando **uma** regra.

6. **Definir "Quando NÃO aplicar"** para impedir o gatilho de casar demais.

7. **Fundamentar.** Ancore cada afirmação normativa em fonte; sinalize as que não
   conseguir fundamentar.

8. **Apontar a contraparte bilíngue.** Indique se deve existir uma skill-espelho
   (PT↔EN) e qual.

9. **Preencher o template** `skill-spec.md` com o acima. A spec deve bastar para
   escrever a skill sem novas perguntas.

## Lembretes

- Autoria segue a Persona e as convenções do `AGENTS.md`.
- Próximo passo: `write-examples` para redigir os pares e o checklist de auto-checagem.
