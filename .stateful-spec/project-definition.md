# Project Definition — `skills`

> Referência de identidade, convenções e fluxo de trabalho do projeto.
> Adaptado do template stateful-spec para um repositório de autoria de skills
> (zero-code). A metodologia (aparada para o tipo skills) vive localmente em
> [`.stateful-spec/methodology/`](methodology/project-types.md); o upstream
> (https://github.com/franciscotbjr/stateful-spec) é a fonte de referência.

## 1. Identidade

- **Nome:** skills
- **Tipo de projeto:** `skills` (registry da metodologia — repositório zero-code de
  Agent Skills, extensões em Markdown).
- **Domínio:** fidelidade linguística e qualidade de prosa (pt-BR e inglês).
- **Licença:** MIT.

## 2. Formato & Ferramentas

- **Formato:** Markdown com frontmatter YAML (campos `name`, `description`).
- **Sem** build, gerenciador de pacotes, task runner, lint, typecheck ou CI.
- **Agentes consumidores:** Claude Code (`.claude/`) e OpenCode (`opencode.json`,
  que carrega `AGENTS.md` como instruções e registra skills em `.`).

## 3. Estrutura do repositório

```
skills/
  AGENTS.md          — entrada universal p/ agentes (orientação + Persona)
  CLAUDE.md          — @AGENTS.md
  README.md          — índice bilíngue (PT/EN) das skills
  opencode.json      — config OpenCode (instructions + skills.paths)
  <skill>/
    SKILL.md         — frontmatter (name, description) + instruções
    README.md        — docs voltados a humanos
  .stateful-spec/    — estado e metodologia:
    memory.md          — estado vivo (ler primeiro)
    project-definition.md — este arquivo
    operations/        — corpos canônicos das 11 operações (PT-BR)
    methodology/       — metodologia local, aparada p/ o tipo skills (EN)
    templates/         — templates de spec/verificação/iteração
    intake/            — caixa de entrada (Backlog/ Discovery/ QA/)
    backlog.md         — oportunidades triadas (O-NNN)
    history/           — iterações NNN-<nome>.md
```

Skills atuais: `prosa-sobria` (PT), `pt-br-fullness` (PT), `sober-prose` (EN),
`verbosity-reduction` (EN).

## 4. Convenções de autoria

- **Estrutura de 2 arquivos por skill:** `SKILL.md` + `README.md`, nada além.
- **`description` como gatilho:** o campo determina a auto-ativação; deve ser
  específico e acionável.
- **Bilinguismo:** README raiz e mensagens de commit em PT/EN; skills são
  monolíngues (`prosa-sobria` ↔ `sober-prose` são contrapartes cruzadas).
- **Branch naming:** `skill/<nome>` (nova skill), `update/<tópico>` (mudança).
- **Padrão de conteúdo de uma skill:** lista de anti-padrões, pares antes/depois
  (bilíngues EN→pt-BR quando aplicável), checklist de auto-checagem e seção
  "Quando NÃO aplicar".

## 5. Verificação (no lugar de "Testing")

Não há testes automáticos. A verificação de uma skill é manual:

- **Validação de gatilho:** a `description` cobre os casos de uso pretendidos e
  exclui os indevidos ("Quando NÃO aplicar")?
- **Checklist de auto-checagem:** a skill traz e satisfaz seu próprio checklist.
- **Exemplos antes/depois:** demonstram o efeito da regra em casos reais.
- **Fundamentação:** cada afirmação normativa se ancora em fonte/pesquisa.

## 6. Quality Gates (convenções)

Antes de considerar uma skill "pronta", confirmar:

- [ ] Diretório com exatamente `SKILL.md` + `README.md`.
- [ ] `description` específica e acionável (condição de gatilho clara).
- [ ] Skill monolíngue; contraparte bilíngue referenciada no README raiz, se houver.
- [ ] Anti-padrões, antes/depois e "Quando NÃO aplicar" presentes.
- [ ] A própria prosa segue `sober-prose`/`prosa-sobria` (sem floreios).
- [ ] Afirmações normativas fundamentadas em fonte.
- [ ] README raiz atualizado (tabela de skills) quando se adiciona/renomeia skill.

## 7. Documentação

- README raiz é **bilíngue (PT/EN)** e indexa as skills.
- Ao adicionar uma tradução, cruzar a referência com a contraparte no README raiz.

## 8. Distribuição

- Skills são **consumidas direto do repositório** (git): `opencode.json` registra
  skills em `.`; Claude Code as descobre via `.claude`/`AGENTS.md`.
- "Publicar" = **merge na `main` via PR**. Não há pipeline ou registro externo.

## 9. Constraints & Non-Negotiables

- Não introduzir código, build ou dependências: o repo é documentation-only.
- Não quebrar a estrutura de 2 arquivos por skill.
- Skills permanecem monolíngues; READMEs e commits, bilíngues.
- Preservar a **Persona** e as convenções do `AGENTS.md`.
- A prosa do próprio repo evita vieses retóricos (aplicar as skills a si mesmas).

## Ciclo de trabalho (fases)

Adaptação do ciclo stateful-spec (Analyze → Plan → Specify → Implement → Verify)
para autoria de skills:

1. **Analisar** — entender o viés ou fenômeno linguístico alvo e como as skills
   atuais (referência) já o tratam; delimitar o que falta.
2. **Planejar** — definir o gatilho (`description`), os anti-padrões a cobrir, o
   idioma da skill e sua contraparte bilíngue.
3. **Especificar** — rascunhar a estrutura: frontmatter + esqueleto de seções do
   `SKILL.md` e do `README.md`.
4. **Redigir** — escrever a prosa da skill, os pares antes/depois e o checklist de
   auto-checagem, fundamentando as afirmações em fonte.
5. **Verificar** — passar pelos Quality Gates (seção 6): estrutura, gatilho,
   bilinguismo, sober-prose aplicada à própria skill e fundamentação.

**Mapeamento fase → operação:**

- Analisar + Especificar → `create-skill-spec`
- Redigir + Verificar → `write-examples`
- Diagnóstico (skill dispara errado / não dispara) → `diagnose-skill`
- Revisão de forma (sem mudar intenção/gatilho) → `revise-skill`
- Revisão de mudanças / docs / commit → `review-changes`, `update-documentation`, `write-commit-message`

O ciclo de sessão (`start` / `resume` / `save` / `end-session`) envolve todas as fases
e cuida do estado, da caixa de entrada (`intake/`) e do `backlog.md`.
