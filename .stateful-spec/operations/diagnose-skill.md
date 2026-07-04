# Operação: diagnose-skill

Diagnostica uma skill com comportamento errado e propõe a correção mínima. Análogo a
depurar um defeito.

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre o diagnóstico no Session Log da iteração.

2. **Classificar o problema:**
   - **Over-matching** — dispara em casos que não deveria;
   - **Under-matching** — deixa de disparar em casos pretendidos;
   - **Afirmação sem fonte** — regra normativa não fundamentada;
   - **Regras contraditórias** — instruções que se anulam.

3. **Isolar a causa-raiz** com justificativa. Se houver incerteza, ranqueie 2–3
   hipóteses, cada uma com uma verificação que a confirme ou descarte.

4. **Propor a correção mínima.** Prefira ajustar a `description` (o gatilho) ou
   acrescentar/afinar "Quando NÃO aplicar" antes de mexer no corpo. Nada de reescrita
   ampla.

5. **Sugerir uma regressão.** Indique um par antes/depois (ou caso de gatilho) que
   passaria a cobrir o problema, para `write-examples`.

## Lembretes

- Correção mínima: o menor diff que resolve o sintoma sem mudar o resto do comportamento.
- Se a correção crescer para reestruturação, encaminhe para `revise-skill`.
