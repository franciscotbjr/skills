# Operação: revise-skill

Reestrutura ou enxuga uma skill sem mudar sua intenção nem o comportamento do gatilho.
Análogo a refatorar.

## Passos

1. **Verificar Open Session.** Leia `.stateful-spec/memory.md`; se houver Open
   Session, registre a revisão no Session Log da iteração.

2. **Identificar os problemas** de forma (não de intenção): padding retórico,
   ambiguidade, fundamentação fraca, seções desorganizadas, exemplos que demonstram
   mais de uma regra.

3. **Plano de revisão ordenado.** Liste os passos na ordem em que serão feitos; cada
   passo deve ser pequeno e revisável isoladamente.

4. **Após cada passo, confirmar invariantes:**
   - a `description` (gatilho) permanece inalterada;
   - as regras e o "Quando NÃO aplicar" seguem preservados;
   - prosa sóbria e afirmações fundamentadas;
   - estrutura de 2 arquivos intacta (`SKILL.md` + `README.md`).

5. **Sinalizar mudança de comportamento.** Se algum passo alterar de fato o que a skill
   faz ou quando dispara, destaque isso à parte — deixa de ser revisão e vira decisão
   do autor (candidato a `create-skill-spec`/`diagnose-skill`).

## Lembretes

- Revisar ≠ redefinir: preserve intenção e gatilho; mude só a forma.
- Atualize a tabela do README raiz se nome/idioma/contraparte mudarem.
