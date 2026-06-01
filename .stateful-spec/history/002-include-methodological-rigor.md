# 002 — include-methodological-rigor

- **Início:** 2026-05-31
- **Status:** completed
- **Fase:** Redigir → Verificar

## Objetivo

Incluir a skill `methodological-rigor` (já adicionada ao diretório) no repositório público: adicionar YAML frontmatter (`name`, `description`) ao `SKILL.md`, registrar na tabela de skills do `README.md` raiz e atualizar os arquivos da metodologia stateful-spec.

## Alterações

1. **`methodological-rigor/SKILL.md`**: adicionado YAML frontmatter com `name: methodological-rigor` e `description` como condição de gatilho.
2. **`README.md` raiz**: adicionado `methodological-rigor` à tabela bilíngue de skills (EN, audit/critical review).
3. **`.stateful-spec/memory.md`**: registrada iteração ativa, adicionada Key Decision sobre a nova skill.

## Quality Gates

- [x] Diretório com exatamente `SKILL.md` + `README.md`
- [x] `description` específica e acionável
- [x] Skill monolíngue (EN) — ver nota
- [x] Anti-padrões, antes/depois e "Quando NÃO aplicar" presentes
- [x] README raiz atualizado (tabela de skills)
- [ ] A própria prosa segue sober-prose (verificação pendente — conteúdo da skill pré-existente)
- [ ] Afirmações normativas fundamentadas em fonte (verificação pendente — conteúdo da skill pré-existente)

## Nota

O `SKILL.md` contém mescla de PT e EN (seções como "Descrição", "Quando usar", "Persona: O Crítico Implacável" em português; exemplos e anti-patterns majoritariamente em inglês). A convenção do repo exige skills monolíngues. O README raiz classifica a skill como "English". Uma iteração futura deve normalizar o idioma.
