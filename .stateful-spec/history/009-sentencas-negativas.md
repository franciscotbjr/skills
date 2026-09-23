# Iteration: 009 — sentencas-negativas

> One file per feature, bugfix, or refactor. Track progress and decisions here.

## Metadata

- **Type:** `skill-revision` (evolução do par prosa-sobria/sober-prose; definido na fase Analisar)
- **Status:** in-progress
- **Created:** 2026-09-22
- **Completed:** —
- **Author:** franciscotbjr

## Description

IAs generativas tendem a argumentar por negação — constroem sentenças negativas para
realizar afirmações. A iteração analisa as alternativas de tratamento: nova skill ou
evolução de `prosa-sobria`/`sober-prose` (cujas descriptions já cobrem parcialmente o
padrão "X não é apenas Y, é Z"). Fonte: `O-006` do backlog, originada de
`intake/Backlog/sentencas-negativas.md` (ideia registrada pelo usuário em 2026-09-22,
com pares antes/depois).

## Acceptance Criteria

- [x] Decisão documentada: skill nova vs. evolução das existentes, com alternativas consideradas
- [x] Gatilho (`description`) específico e acionável; sobreposição com skills atuais delimitada
- [x] Especificação passa nos Quality Gates (§6 do project-definition)
- [ ] Estado persistido (`memory.md`, backlog, iteração) — fica para o fechamento da 009

## Implementation Tasks

- [x] Fase Analisar: questionamento exaustivo do item (uma pergunta por vez), com árvore de decisões documentada
- [x] Fase Planejar: gatilho, anti-padrões, idioma e contraparte
- [x] Fase Especificar: frontmatter + esqueleto de SKILL.md/README.md (ou diff das skills existentes)
- [x] Fase Redigir: prosa, pares antes/depois, checklist de auto-checagem, fundamentação
- [x] Fase Verificar: Quality Gates §6 + checklist §9 em passo separado; registrar no Session Log

## Quality Checks

> Standard checks from the Project Definition. Verify before marking done.

- [x] Estrutura de 2 arquivos por skill (SKILL.md + README.md) — preservada; diff mínimo nas existentes
- [x] Afirmações normativas fundamentadas — fundação interna aprovada (preservação de informação + exemplos reais do item)
- [x] A prosa da própria skill segue sober-prose/prosa-sobria — adições sem floreios retóricos
- [x] README raiz — sem mudança necessária (nenhuma skill adicionada/renomeada)

## Session Log

> Timestamped entries recording each operation performed during this session.
> Agents append entries automatically when an Open Session is active.

| Timestamp | Operation | Summary |
|-----------|-----------|---------|
| 2026-09-22 17:52 | resume-session | Retomada carregou estado: sem iteração ativa; intake com ideia nova do usuário em `intake/Backlog/prd.md` (não-triada). Usuário escolheu Caminho A. |
| 2026-09-22 17:52 | triage | `prd.md` restaurado como origem do O-003; ideia movida para `intake/Backlog/sentencas-negativas.md` (`status: ready`); promovida a `O-006` no backlog.md. |
| 2026-09-22 18:31 | analyze | Questionamento exaustivo concluído: 5 decisões com alternativas documentadas (escopo, arquitetura, discriminador, tratamento, fundamentação) — ver Decisions Made. |
| 2026-09-22 18:31 | draft | Evoluções redigidas no par: sub-variante "negação com conteúdo" no anti-padrão #2 (prosa-sobria + sober-prose), teste da deleção com perda, par antes/depois real do item, "delimitação positiva" em O que fazer em vez, categoria de segunda passada, fronteira do contraste substantivo em Quando NÃO aplicar; espelhos nos READMEs das duas skills e na prosa-completa (resumo + checklist item 2). |
| 2026-09-22 18:31 | verify | Checklist §9 em passo separado: todos os itens passam — sem afirmações empíricas novas a ancorar; contra-caso (contraste substantivo legítimo) no corpo; C1 (fundação interna aprovada pelo usuário), C2 (par real do item), C3 (enquadramento positivo + fronteira) conformes; G1–G3 inalterados (família já nomeada nas descriptions, sem skill nova); V2 coberto pelo teste da deleção com perda + fronteira. Quality Gates §6 conformes; README raiz sem mudança (nenhuma skill adicionada/renomeada). |
| 2026-09-22 21:30 | resume-session | Retomada para revisão externa do rascunho (revisão de outra IA em `velvet-stargazing-cocke.md`). Branch renomeado `feat/sentenca-nao-negativas` → `update/sentencas-negativas` (convenção AGENTS.md, aprovado). |
| 2026-09-22 21:30 | review | Revisão adversarial verificada: A1 (enunciado do #2 dizia "remover" contradizendo a 4ª sub-variante — corrigido), A2 (par antes/depois ensinava inflação — 3ª frase restaurada no "Antes"), A2b (mesmo defeito no exemplo inline do bullet — corrigido a pedido do usuário), A3 ("Três categorias" com 6 itens — número removido), A4 (fronteira do lócus não-recuperável — frase de manter-a-negação adicionada), A5 (exemplo em 3 ocorrências — mantido por decisão), A6 (estado dessincronizado — corrigido nesta retomada). Sobreposição com o #7 considerada sem mudança (mira a falsa simetria, não o conteúdo; remissão empilharia regra — §8.3). |
| 2026-09-22 21:30 | verify | Checklist §9 em passo separado sobre o estado pós-revisão: passa em todos os itens — sem afirmações empíricas novas; contra-caso no corpo (frase de fronteira A4 + contraste substantivo em Quando NÃO aplicar); protocolo com gatilho/saída na 4ª sub-variante; C2 satisfeito com o par restaurado que preserva informação (tudo no "Depois" vem do "Antes"); C3 com enquadramento positivo e duas fronteiras; G1–G3 inalterados; V2 respeitado (diff mínimo, espelhado PT/EN item a item). Intake sem `ready` pendente (só templates). |

## Decisions Made

> Decisions made during this iteration. Include rationale.

| Decision | Rationale | Date |
|----------|-----------|------|
| Escopo do alvo: negação **com conteúdo** — a negação que delimita/corrige e exige reescrita positiva que preserva o conteúdo; o caso de metade negativa como enchimento já está coberto por #2/#7 | Os exemplos do item mostram negação que corrige leitura possível, e a reescrita do usuário converte a delimitação em afirmação relacional — tratamento ausente nas skills atuais, cuja regra é deletar a metade negativa | 2026-09-22 |
| Arquitetura: **evoluir o par** `prosa-sobria` + `sober-prose` (sub-variante no anti-padrão #2) — sem skill nova | Alternativas: (B) skill nova par PT/EN — cria colisão de gatilho G3 com as prosa skills, exige README raiz e integração na `prosa-completa`; (C) só PT primeiro — quebra a paridade do par bilíngue. A sub-variante é da mesma família sintática já coberta pelo #2; o delta é o tratamento | 2026-09-22 |
| Discriminador: **teste da deleção com perda** — remover a metade negativa; se se perde delimitação/correção que o leitor plausivelmente precisa, é conteúdo; senão, é enchimento | Alternativas: (B) contrapositiva positiva — equivalente em extensão, mas menos operacional; (C) teste duplo — redundante. O teste da deleção segue a mecânica de teste já usada pela skill (#1, #12) | 2026-09-22 |
| Tratamento: **conversão positiva integral** — reescrever a delimitação negativa como afirmação positiva integrada à definição (o lócus real do que é afirmado), nunca mantendo o andaime de contraste | Alternativas: (B) contraste condicional — reintroduz o andaime que a skill remove; (C) tipologia dupla — complica sem ganho demonstrado. Os dois exemplos do item já praticam a conversão integral | 2026-09-22 |
| Fundamentação: **interna** — preservação de informação + exemplos reais do item, no estilo atual do arquivo (sem citações inline) | Alternativas: (B) pesquisa no vault Jandi — custo de ciclo desproporcional para evolução pequena de skill existente; (C) literatura externa (ex.: negação metalinguística de Horn) — ancoragem forte, mas não exigida pelo padrão do arquivo. Aprovada pelo usuário no questionamento do Analisar (Session Log de 18:31) | 2026-09-22 |
| Revisão A4: **manter a negação quando o lócus positivo não é recuperável** — frase de fronteira na 4ª sub-variante do #2, após a conversão | A conversão pressupõe saber onde a propriedade mora; aplicada a texto que o agente não domina, a regra pode induzir fabricação (§1.5, C3) — o Exemplo 2 do intake importa afirmação ausente do original. Alternativas: sinalizar ao usuário em vez de manter; não acrescentar nada | 2026-09-22 |
| Revisão A5: **manter o exemplo em 3 ocorrências** (bullet #2, "Delimitação positiva", par antes/depois) | Cada seção fica autocontida para leitura isolada; redundância aceita conscientemente após o teste de subtração (R2). Alternativas: uma ocorrência só; trocar pelo Exemplo 2 (conflita com A4) | 2026-09-22 |

## Blockers & Notes

- A ideia original reutilizava `prd.md` (origem do O-003 já promovido); movida para arquivo próprio para preservar rastreabilidade.
- As descriptions de `prosa-sobria` e `sober-prose` já mencionam o anti-padrão "X não é apenas Y, é Z" — delimitar a fronteira com o viés mais amplo de negação-como-afirmação foi a primeira decisão da fase Analisar (resolvida: escopo = negação com conteúdo).

## References

- **Specification:** Decisions Made (tabela acima) — o ciclo Analisar→Verificar ficou registrado como decisões, sem spec em arquivo separado (evolução de skill existente)
- **PR/MR:** —
- **Commits:** —
- **Branch:** `update/sentencas-negativas`
- **Related Issues:** O-006 (`backlog.md`); intake `intake/Backlog/sentencas-negativas.md`
