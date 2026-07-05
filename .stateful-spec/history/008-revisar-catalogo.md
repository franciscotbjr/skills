# 008 — revisar-catalogo

- **Início:** 2026-07-04
- **Conclusão:** 2026-07-04
- **Status:** completed
- **Tipo:** skill-revision (revisão do catálogo sob G1–G3/R1–R4; sem alterar skills nesta fase)
- **Fase:** ciclo completo (Analisar → Redigir → Verificar; edições validadas
  pelo usuário no fechamento)
- **Origem:** O-005 ([backlog.md](../backlog.md)) ← [intake/Backlog/revisar-catalogo.md](../intake/Backlog/revisar-catalogo.md)

## Objetivo

Aplicar os protocolos de autoria do [`persona.md`](../persona.md) — **G1–G3**
(projetar o gatilho) e **R1–R4** (redigir o corpo) — numa revisão das 6 skills
anteriores às personas: `prosa-sobria`, `sober-prose`, `pt-br-fullness`,
`verbosity-reduction`, `prosa-completa`, `methodological-rigor`. A
`readme-writer` já passou G1–G3 na [007](007-consolidar-readme-writer.md) e
entra apenas como vizinha nos pares G3.

Enquadramento adversarial (persona §1.3): a pergunta por skill não é "está
boa?", e sim "que tarefa a dispararia indevidamente? que leitor entenderia
errado esta regra?". O entregável é **evidência, não correção**: registro por
skill com veredito `conforme | achado | INCONCLUSIVO` por protocolo, teste de
colisão G3 por par do catálogo e lista triada de achados com opções tipadas —
a decisão sobre corrigir é do usuário (§8.6).

**Fora de escopo:** alterar qualquer `SKILL.md`/`README.md`; avaliação de
eficácia E1 (par com/sem — revisão estática ex ante); reabrir Key Decisions
(`prosa-completa` agregadora; contrapartes PT↔EN).

## Critérios de aceite

- [x] Registro por skill completo (6/6): G1, G2, R1, R2, R3, R4 com veredito e
      a saída observável que cada protocolo exige (G1: 3 tarefas que disparam +
      2 que não; G2: fronteira e vizinhos; R1: medida de tamanho; R2: resultado
      do teste de subtração; R3: as 3 regras críticas e sua posição; R4:
      proibições e substitutos).
- [x] Teste de colisão G3 registrado com os pares examinados (mínimo:
      `sober-prose`↔`verbosity-reduction`, `prosa-sobria`↔`prosa-completa`,
      `pt-br-fullness`↔`prosa-completa`, `prosa-sobria`↔`pt-br-fullness`,
      `methodological-rigor`↔`sober-prose`, `prosa-sobria`↔`sober-prose`
      cross-língua), 3–5 tarefas ambíguas por par e conjunto exposto por tarefa
      avaliado contra o ótimo 2–3.
- [x] INCONCLUSIVO tratado como resultado de primeira classe (§1.2): o que não
      pôde ser confirmado estaticamente tem lugar estruturado no registro.
- [x] Achados consolidados em lista triada com opções tipadas por achado:
      (a) corrigir nesta iteração (fase Redigir), (b) oportunidade no backlog,
      (c) INCONCLUSIVO/sem ação — escolha do usuário.
- [x] Checklist de saída do `persona.md` §9 executado em passo separado de
      crítica, com resultado (incl. INCONCLUSIVOs) no Session Log.
- [x] Nenhum `SKILL.md`/`README.md` do catálogo alterado nesta fase.

## Tarefas

- [x] Ler os 7 `SKILL.md` + `README.md` do catálogo (SKILL.md integrais;
      READMEs varridos por referências cruzadas).
- [x] Revisar cada uma das 6 skills pré-persona sob G1–G2 e R1–R4, registrando
      vereditos e saídas observáveis.
- [x] Rodar o teste de colisão G3 por par com sobreposição semântica,
      reaproveitando o registro da 007 para `readme-writer`.
- [x] Consolidar a lista triada de achados com opções tipadas.
- [x] Crítica em passo separado: checklist §9 sobre o próprio relatório;
      registrar no Session Log.
- [x] Apresentar o resumo ao usuário para decisão sobre os achados.

**Fase Redigir (autorizada pelo usuário — "Corrigir todas A1–A12"):**

- [x] pt-br-fullness: description reescrita ≤1.024 com as 11 categorias (A3),
      cabeçalho "onze categorias" (A7), prioridade de varredura rotulada (A11).
- [x] prosa-completa: passo 4 com as onze categorias (A7); description com
      modo de disparo e subsunção das componentes (A8).
- [x] prosa-sobria: gating de língua na description (A1); #12, #13, item do
      exemplo concreto, checklist 7–8 e segunda passada sincronizados da
      sober-prose (A6); vizinhas e deferência no "Quando NÃO aplicar" (A8/A9).
- [x] sober-prose: gating de língua + contraparte na description (A1);
      vizinhas e deferência no "When NOT to apply" (A8/A9).
- [x] verbosity-reduction: fronteira negativa na description e seção "When NOT
      to apply" com vizinhas (A2); "Architectural mitigation" movida para o
      README (A10).
- [x] methodological-rigor: corpo e README traduzidos para EN (A5, A12);
      segundo exemplo e "Como acionar" removidos (A4); "When NOT to apply"
      com vizinhas (A9).
- [x] Re-medição pós-correção: descriptions todas ≤ 1.024; MR a ~4,9k tokens
      est.; verificação de sobras de PT na MR (0 ocorrências).

## Session Log

| Timestamp | Operation | Summary |
|-----------|-----------|---------|
| 2026-07-04 20:22 | start-session | Sessão aberta; intake sem itens `ready` (triagem no-op); foco escolhido: revisão do catálogo sob G1–G3/R1–R4 (candidata do memory.md desde a 007). Item revisar-catalogo.md criado e triado a O-005; iteração 008 criada (fase Analisar); branch update/revisar-catalogo. |
| 2026-07-04 20:40 | analisar (revisão) | 6 skills revisadas sob G1–G2/R1–R4 com medidas por script (linhas/chars/desc; tokens estimados chars/4) + G3 em 5 pares (16 tarefas ambíguas) reaproveitando o registro da 007. Resultado: 12 achados triados (2 ALTA, 1 MÉDIA-ALTA, 4 MÉDIA, 5 BAIXA), 4 INCONCLUSIVOs registrados. Destaques: contrapartes sem gating de língua (A1); VC sem "When NOT to apply" (A2); description da pt-br-fullness > 1.024 chars (A3); MR ~5,8k tokens est. (A4). Nenhuma skill alterada. |
| 2026-07-04 20:48 | verificar (crítica em passo separado) | Checklist §9 sobre o relatório: (1) âncoras — 2 estimativas substituídas por medição (typo "acharcos": 9 linhas por grep; checklist MR: 26 caixas), demais resolvem (script + arquivos); (2) evidência contrária no corpo (notas de mitigação nos "conforme"; contrapontos nos pares G3, ex. dedupe prático no par 5); (3) nota de método presente com 4 INCONCLUSIVOs; (4) nada removido/obsoletado nesta fase por design (§8.6) — candidatas a remoção identificadas em A4/A10; (5) vereditos com saída observável; (6) item G1–G3/C1–C3 N/A — o entregável é revisão, não skill. Falha não corrigível: nenhuma. Pendente: decisão do usuário sobre A1–A12. |
| 2026-07-04 21:05 | redigir (correções A1–A12) | Usuário autorizou "Corrigir todas". 6 skills editadas (10 arquivos, 447+/500−): gating de língua nas contrapartes (A1); fronteira + "When NOT to apply" na VC (A2); description da pt-br-fullness 1.203→852 chars com 11 categorias (A3); MR podada 432→337 linhas (A4) e traduzida para EN com README (A5, A12); prosa-sobria sincronizada 13/13 com a sober-prose (A6); contagens corrigidas (A7); subsunção da agregadora + deferências recíprocas (A8); vizinhas nomeadas nos corpos (A9); mitigação arquitetural da VC movida ao README (A10); prioridade rotulada na pt-br-fullness (A11). Duas regressões introduzidas e corrigidas na re-medição: description da prosa-completa a 1.028 chars (encurtada para 981) e nota da pt-br-fullness (enxugada). |
| 2026-07-04 21:12 | verificar (crítica §9 sobre as edições) | Gates §6 por skill editada: estrutura 2 arquivos ✓; descriptions ≤1.024 ✓ (re-medidas por script); monolinguidade ✓ (MR 100% EN — grep de palavras PT: 0); "quando não aplicar" presente nas 6 ✓; fundamentação ✓ (#12/#13 portados com exemplos — C2; prioridade rotulada [preferência editorial] — C1; sem racional fabricado — §1.5). Coerência cruzada: sober-prose default p/ línguas terceiras casa com a tabela da prosa-completa ✓; README raiz já lista MR como English (sem mudança) ✓. Residuais declarados: pt-br-fullness INCONCLUSIVO na fronteira de R1 (5.044 est.); densidade da MR reduzida, não eliminada. E2: saldo do diff −53 linhas. Ajustes de calibração declarados (README da MR: "Validada"→"Evidence status"; fecho aforístico removido). Pendente: validação do usuário; commit/PR sob demanda. |
| 2026-07-04 21:30 | resume-session (fechamento) | Sessão retomada; intake sem itens novos (triagem no-op). Usuário validou as edições A1–A12 ("Validar e fechar a 008"): diff conferido contra o registro (10 arquivos, 457+/501−). Iteração marcada completed; memory.md atualizado (Active Work → Recent Completions #8, History Index); commit/PR preparados na branch update/revisar-catalogo. |

## Revisão por skill (fase Analisar)

**Método.** Revisão estática dos 7 `SKILL.md` (2026-07-04, working tree da
branch `update/revisar-catalogo`). Medidas por script (parse do frontmatter +
contagem); tokens **estimados** como chars/4 — não é tokenização real, e
veredito de R1 na fronteira fica INCONCLUSIVO. Enquadramento adversarial
(§1.3): por skill, busca ativa da tarefa que dispararia indevidamente e do
leitor que entenderia errado. `readme-writer` fora do escopo (nasceu sob os
protocolos na 007).

### Medidas (âncoras)

| Skill | Linhas (corpo) | Chars (corpo) | Tokens est. | `description` (chars) |
|---|---|---|---|---|
| prosa-sobria | 106 | 9.177 | ~2.294 | 596 |
| sober-prose | 113 | 12.406 | ~3.102 | 569 |
| pt-br-fullness | 250 | 19.899 | ~4.975 | **1.203** |
| verbosity-reduction | 202 | 11.379 | ~2.845 | 670 |
| prosa-completa | 101 | 11.628 | ~2.907 | 874 |
| methodological-rigor | 432 | 23.026 | **~5.756** | 505 |
| readme-writer | 190 | 11.571 | ~2.893 | 812 |

Limites de referência: G1 ≤ 1.024 chars na `description`; R1 < 500 linhas e
< 5.000 tokens no corpo (persona.md §2–3).

### prosa-sobria

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | conforme | O quê (restringe vieses retóricos de RLHF, padrões nomeados), quando (prosa expositiva/técnica/filosófica/analítica; "mesmo que o usuário não peça"), palavras-chave ("sem floreios", aforístico, ternário). Disparam: (1) "Explique o consenso Raft"; (2) "Escreva a seção de análise do relatório"; (3) "Deixe este texto sem floreios". Não disparam: (1) "Escreva um poema sobre o mar"; (2) "Escreva o copy do anúncio". Nota: gatilho quase-sempre-ativo por design do domínio — a condicionalidade vem do tipo de texto, não do pedido. |
| G2 | achado (leve) | "Quando NÃO aplicar" presente (4 exclusões por tipo de tarefa). Vizinhas de catálogo não nomeadas no corpo que o agente lê (desempates vivem na verbosity-reduction, na prosa-completa e no README humano). Sem gating de língua → par 5 do G3. |
| R1 | conforme | 106 linhas; ~2,3k tokens est. |
| R2 | conforme | "Por que o viés existe" passa a subtração pelo papel de fundamentação (ancora as normas no mecanismo RLHF); o resto é procedimento. |
| R3 | conforme | Os dois anti-padrões nucleares (#1 aforístico, #2 família "X não é Y") no primeiro terço; checklist de 6 itens. |
| R4 | conforme | Cada anti-padrão traz "Correção:"; "O que fazer em vez" dá os substitutos. |

Nota de sincronização (→ A6): 11 anti-padrões contra 13 da contraparte
`sober-prose` (#12 metáfora definicional e #13 scare quotes ausentes); falta o
item aditivo do exemplo concreto em "O que fazer em vez"; checklist 6 vs 8. A
`prosa-completa` (itens 4–5 do checklist) já cobra #12/#13 — que não existem
na skill PT.

### sober-prose

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | conforme | Espelho EN da prosa-sobria (569 chars). Disparam: (1) "Explain Raft consensus"; (2) "Write the analysis section of this report"; (3) "Rewrite this without flourish". Não disparam: (1) "Write a poem"; (2) "Write ad copy for the launch". Mesma nota de gatilho amplo por design. |
| G2 | achado (leve) | "When NOT to apply" presente. Nomeia a verbosity-reduction pontualmente (fronteira do exemplo concreto vs VC #4), mas sem seção de vizinhas/desempate; sem gating de língua → par 5 do G3. |
| R1 | conforme | 113 linhas; ~3,1k tokens est. |
| R2 | conforme | Mesma nota do "Why the bias exists". |
| R3 | conforme | #1/#2 no primeiro terço; checklist de 8 itens. |
| R4 | conforme | "What to do instead" + correção por anti-padrão; a única regra aditiva (exemplo concreto) declara a própria fronteira contra VC #4. |

### pt-br-fullness

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | **achado** | Conteúdo exemplar (o quê + quando + palavras-chave com as categorias nomeadas), mas a `description` tem **1.203 chars > limite 1.024**, e cobre 10 das 11 categorias do corpo (§11 barra-como-ou ausente). Disparam: (1) "Escreva um artigo em pt-BR sobre filas de mensagens"; (2) "Traduza este documento para o português"; (3) "Redija em português a resposta a partir deste material em inglês". Não disparam: (1) "Write an English blog post"; (2) "Revise este texto em português europeu". → A3 |
| G2 | conforme | Exclusões na description (inglês, citações literais, coloquial deliberado, pt-PT) + "Quando NÃO aplicar" + seção "Relação com sober-prose e verbosity-reduction" com desempate (informacional vs decorativo; artigo não é VC). A melhor G2 do conjunto pré-persona. |
| R1 | INCONCLUSIVO | 250 linhas (< 500 ✓); 19.899 chars ≈ 4.975 tokens estimados — na fronteira dos < 5.000; o veredito estrito depende do tokenizador real. |
| R2 | conforme | As 11 categorias são procedimento (EN-fonte/drift/pleno por caso); "Por que o viés existe" carrega as âncoras (LDM-PT). |
| R3 | achado (leve) | 11 categorias (§1 e §2 com 5 sub-casos cada) + checklist de 11 itens, sem primazia declarada ("as 3 que mais importam" não existem — compare com a readme-writer). A ordem implícita prioriza artigos/conectivos/regência, mas R3 pede a hierarquia explícita. → A11 |
| R4 | conforme | Anti-padrões como par drift→pleno (alvo positivo sempre presente); diretrizes afirmativas com exceções declaradas. |

Nota de sincronização interna (→ A7): o cabeçalho diz "Anti-padrões — **dez**
categorias" mas são 11; a description cobre 10/11. O exato "stale claim" que a
readme-writer condena, dentro do próprio catálogo.

### verbosity-reduction

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | achado (parcial) | O quê + quando + palavras-chave presentes (QA, extraction, classification, tool-call arguments, "concise"; 670 chars). Disparam: (1) "What's the boiling point of water?"; (2) "Extract the dates from this doc"; (3) "Classify these tickets". **As 2 tarefas que não disparam não são deriváveis da description** — nenhuma exclusão declarada; o leitor infere (prosa criativa? curadoria de arquivo?) sem apoio textual. → A2 |
| G2 | **achado** | Sem seção "When NOT to apply" — viola também o Quality Gate §6 do repo. "Do not overcorrect" limita a correção, não o disparo. A sober-prose é nomeada nas fronteiras de span ("mesmo span, ângulos distintos"), mas não há exemplo de tarefa do outro lado; o desempate com a readme-writer ("Make my README shorter" → curadoria de arquivo ≠ resposta gerada) existe só do lado da readme-writer (007). → A2 |
| R1 | conforme | 202 linhas; ~2,8k tokens est. |
| R2 | achado (leve) | "Architectural mitigation (for system builders)" endereça construtores de pipeline, não o agente em disparo — falha a subtração para o caso de uso do gatilho. Candidata a migrar para o README da skill. → A10 |
| R3 | conforme | Operational test + primary move no primeiro terço. |
| R4 | conforme | Remoção sempre com movimento substituto (commit the answer token; localizar o hedge); "Do not overcorrect" declara o que sobrevive. |

### prosa-completa

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | conforme (nota) | 874 chars; o quê (agrega as três), quando (revisão integral de texto longo), desempate na própria description ("para escopo específico, prefira a individual"). Disparam: (1) "Revise integralmente este ensaio em pt-BR"; (2) "Faça uma revisão completa deste documento"; (3) "/prosa-completa neste texto". Não disparam: (1) "Corte só o padding daqui"; (2) "Escreva um poema". Nota: a description mistura dois modos — auto-gatilho ("Use quando...") e invocação explícita ("Acione via /prosa-completa") — sem dizer qual prevalece. → A8 |
| G2 | conforme | "Quando NÃO aplicar" + "Relação com as três skills individuais" com desempate por escopo + tabela de gating de língua. |
| R1 | conforme | 101 linhas; ~2,9k tokens est. |
| R2 | conforme | Ordem de aplicação, gating e resolução de conflitos — procedimento que o agente não derivaria sozinho. |
| R3 | conforme (nota) | Ordem de aplicação no início; checklist combinada de 14 itens é densa, mas é a agregação declarada das três componentes. |
| R4 | conforme | Resoluções no formato "mantenha X; corte Y" com critério. |

Notas (→ A7, A1): o passo 4 manda percorrer "as **sete** categorias" da
pt-br-fullness — são 11 (o item 14 do próprio checklist já cita a §11). A
componente citada para qualquer língua é a `sober-prose` (com "tradução mental"
dos exemplos); a `prosa-sobria` **não** é componente da agregadora.

### methodological-rigor

| Prot. | Veredito | Evidência / saída observável |
|---|---|---|
| G1 | conforme | 505 chars; o quê (auditoria de solidez metodológica/epistêmica), quando (antes de publicar análise que baseia decisão; "especially when you are confident"), palavras-chave (audit, premises, circular reasoning). Disparam: (1) "Audit this analysis before I publish it"; (2) "Critique the methodology of this comparison"; (3) "Minha recomendação está epistemicamente sólida?". Não disparam: (1) "Write a short story"; (2) "Renomeie esta variável". |
| G2 | achado (leve) | Fronteira mínima na description ("creative writing / no factual claims"); corpo tem "Quando usar" mas não "quando não usar"; nenhuma vizinha nomeada — o desempate com a sober-prose (estrutura do argumento vs forma da expressão) vive no `AGENTS.md`, não na skill; o README da skill também não referencia vizinhas (0 ocorrências). → A9 |
| R1 | **achado** | 432 linhas (< 500 ✓), mas 23.026 chars ≈ **5.756 tokens estimados > 5.000**. Maior corpo do catálogo (~2× a mediana). → A4 |
| R2 | **achado** | Falham a subtração para o agente em disparo: (a) o segundo exemplo completo de aplicação duplica a função do primeiro; (b) "Como acionar a skill" é instrução para humanos (material de README); (c) o protocolo aparece em três formas (Abordagem sistemática §1–7b, Checklist de auditoria com 26 caixas, Critérios de completude) com sobreposição alta. → A4 |
| R3 | achado | Posição ok (o §7 auto-aplicação — "a crítica mais valiosa" da própria skill — está no primeiro terço), mas a densidade excede o orçamento: 7+1 passos, 26 caixas de checklist, 8 anti-padrões, 6 critérios de completude e notas de calibração competindo pela adesão. → A4 |
| R4 | conforme (leve) | Persona definida por comportamentos positivos ("O Crítico é..."); proibições com alternativa na maioria; as distinções (erro/omissão/limitação) dão o critério. |

Notas fora de G/R (rotuladas, convenção do repo): (a) **monolinguidade
violada** — description EN + corpo PT-BR, skill catalogada como EN no
memory.md → A5; (b) typo sistemático "acharcos" por "achados" (9 linhas,
medido por grep) → A12.

## Teste de colisão G3 (catálogo)

**Método:** por par com sobreposição semântica, 3–5 tarefas ambíguas simuladas
contra as `description`s lidas isoladamente ("dispara" = a description, sozinha,
cobre a tarefa). Ótimo de referência: conjunto exposto de 2–3 skills por tarefa
(persona.md G3). O par da `readme-writer` reaproveita o registro da 007 (5
tarefas, nenhuma reescrita exigida, co-disparos legítimos com sober-prose e
pt-br-fullness).

**Par 1 — sober-prose ↔ verbosity-reduction**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|---|---|---|---|
| "What's the capital of France?" | verbosity-reduction | sober-prose (mensagem muito curta — exclusão declarada) | Sem colisão. Conjunto 1. |
| "Write a technical blog post on Raft" | ambas | — | Co-disparo legítimo: retórica vs densidade; "mesmo span, ângulos distintos" documentado na VC. Conjunto 2. |
| "Trim this paragraph without losing content" | verbosity-reduction (+ sober-prose se houver floreio) | — | Co-disparo legítimo; desempate documentado (VC "bonus"; prosa-completa §conflitos). |
| "Make my README shorter" | readme-writer | verbosity-reduction — mas só por inferência ("generated responses" ≠ arquivo) | Fronteira declarada apenas do lado da readme-writer; do lado da VC, ausente → reforça A2. |
| "Summarize this document in 3 bullets" | verbosity-reduction | — | Sem colisão. |

**Par 2 — prosa-completa ↔ componentes (verbosity-reduction, pt-br-fullness; sober-prose)**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|---|---|---|---|
| "Revise integralmente este ensaio em pt-BR" | prosa-completa + pt-br-fullness + verbosity-reduction + sober-prose (e prosa-sobria, ver par 5) | — | **Colisão de agregação:** 4–5 expostas (> ótimo 2–3); as individuais não deferem à agregadora, e a agregadora re-aplica as mesmas regras. → A8 |
| "Corte os floreios deste parágrafo" | prosa-sobria/sober-prose | prosa-completa (escopo específico — deferência declarada) | Resolve pela description da agregadora. Conjunto 1–2. |
| "Escreva duas frases em pt-BR" | pt-br-fullness (leve) | prosa-completa (mensagens curtas — exclusão) | Sem colisão. |
| "Revise este texto longo em inglês por completo" | prosa-completa + sober-prose + verbosity-reduction | pt-br-fullness (gating de língua) | Conjunto 3 (no limite do ótimo); o gating interno da agregadora funciona. |

**Par 3 — prosa-sobria ↔ pt-br-fullness**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|---|---|---|---|
| "Escreva um artigo técnico em pt-BR" | ambas | — | Co-disparo legítimo: dimensões disjuntas (retórica vs morfossintaxe); desempate documentado na pt-br-fullness. Conjunto 2–3. |
| "Corrija o idiomático deste texto pt-BR (ex.: 'lave suas mãos')" | pt-br-fullness | prosa-sobria (não há viés retórico em jogo) | Sem colisão. |
| "Remova a retórica deste texto em pt-BR" | prosa-sobria (+ pt-br-fullness, por ser geração pt-BR) | — | Co-disparo legítimo. Conjunto 2. |

**Par 4 — methodological-rigor ↔ sober-prose**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|---|---|---|---|
| "Audit this analysis before I publish it" | methodological-rigor (+ sober-prose sobre a prosa da própria resposta) | — | Objetos distintos (argumento do documento vs forma da minha prosa); co-disparo legítimo. |
| "Review this document" (ambíguo) | methodological-rigor se doc analítico; readme-writer se README | — | Resolve pelo objeto; as descriptions cobrem. |
| "Melhore a escrita desta análise" | sober-prose/prosa-sobria | methodological-rigor (forma, não solidez) | Fronteira derivável mas não declarada na MR (→ A9). |
| "Esta comparação de ferramentas é confiável?" | methodological-rigor | demais | Sem colisão. |

**Par 5 — prosa-sobria ↔ sober-prose (contrapartes cross-língua)**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|---|---|---|---|
| "Escreva uma análise em português" | prosa-sobria **e** sober-prose (nenhuma description exclui a outra língua) | — | **Colisão latente:** dedupe depende do bom senso do agente — exatamente o que G3 manda resolver por reescrita. → A1 |
| "Write an analysis in English" | sober-prose **e** prosa-sobria | — | Espelho do anterior. → A1 |
| "Écris une analyse en français" | indefinido (nenhuma declara língua-alvo; a tabela da prosa-completa trata a sober-prose como válida para qualquer língua, "com cautela") | — | Comportamento em línguas terceiras não especificado em nenhuma description. → A1 |

**Pior caso medido:** "Revise integralmente o README.pt-BR.md deste
repositório" → readme-writer + prosa-completa + pt-br-fullness + prosa-sobria +
sober-prose + verbosity-reduction = **6 skills nominalmente expostas** (ótimo:
2–3). As colisões concentram-se em dois eixos: língua (par 5) e agregação
(par 2); os demais co-disparos são complementares e documentados.

## Achados triados

12 achados (média 2/skill). Opções tipadas por achado: **(a)** corrigir nesta
iteração (fase Redigir, semântica `revise-skill`/`diagnose-skill`); **(b)**
registrar como oportunidade no backlog; **(c)** aceitar/INCONCLUSIVO com
registro. A escolha é do usuário (persona §8.6).

| # | Sev. | Prot. | Achado | Skills |
|---|---|---|---|---|
| A1 | ALTA | G3/G2 | Gating de língua ausente nas contrapartes: nenhuma description declara língua-alvo; em qualquer tarefa de prosa as duas disparam juntas; em línguas terceiras o comportamento é indefinido; a prosa-completa usa a sober-prose para qualquer língua, tornando a prosa-sobria redundante sob a agregadora | prosa-sobria, sober-prose |
| A2 | ALTA | G2 + QG§6 | Sem "When NOT to apply": nenhuma fronteira negativa na description nem no corpo; viola o Quality Gate §6 do repo; desempate com a readme-writer existe só do lado dela; é a skill de gatilho mais amplo do catálogo | verbosity-reduction |
| A3 | MÉDIA-ALTA | G1 | `description` com 1.203 chars (> 1.024, limite do formato) e cobrindo 10 das 11 categorias (§11 ausente) | pt-br-fullness |
| A4 | MÉDIA | R1+R2+R3 | Corpo a ~5,8k tokens est. (> 5.000): segundo exemplo duplicado, "Como acionar" (material de README) e protocolo triplicado (passos/checklist/critérios); densidade compromete adesão | methodological-rigor |
| A5 | MÉDIA | convenção | Monolinguidade violada: description EN + corpo PT-BR, catalogada como EN | methodological-rigor |
| A6 | MÉDIA | sincronização | Contraparte PT atrás da EN: faltam #12, #13, o item do exemplo concreto e 2 itens de checklist; a prosa-completa já cobra #12/#13 que não existem na skill PT | prosa-sobria |
| A7 | MÉDIA | sincronização | Contagens desatualizadas: cabeçalho "dez categorias" (são 11) e description 10/11; agregadora manda percorrer "sete categorias" (são 11) | pt-br-fullness, prosa-completa |
| A8 | BAIXA-MÉDIA | G3/G1 | Agregação: modo de disparo ambíguo (auto vs /prosa-completa) e conjunto exposto 4–6 em revisão integral pt-BR, com re-aplicação das mesmas regras | prosa-completa (+ individuais) |
| A9 | BAIXA | G2 | Vizinhas não nomeadas no corpo que o agente lê (desempates vivem nas vizinhas, no AGENTS.md ou no README humano; na MR, em lugar nenhum da skill) | prosa-sobria, sober-prose, methodological-rigor |
| A10 | BAIXA | R2 | "Architectural mitigation" (para construtores de pipeline) no corpo de disparo; candidata a migrar para o README da skill | verbosity-reduction |
| A11 | BAIXA | R3 | Sem primazia declarada: 11 categorias + checklist de 11 sem "as 3 que mais importam" | pt-br-fullness |
| A12 | BAIXA | textual | Typo sistemático "acharcos" por "achados" (9 linhas, medido por grep) | methodological-rigor |

**INCONCLUSIVOs (§1.2 — primeira classe):**

- R1 da pt-br-fullness: 4.975 tokens estimados — na fronteira; sem tokenização
  real, nem conforme nem violação.
- Eficácia de qualquer skill do catálogo (E1): nenhum par com/sem medido;
  todas permanecem hipótese ex ante com fundamentação citada. Fora do escopo
  declarado desta revisão.
- Comportamento ex post de disparo: a revisão é estática; confusões reais do
  agente não foram observadas aqui — cobertas pela candidata já registrada
  "sinais ex post da §9 do persona-reference".
- Estimativa de tokens por chars/4: método declarado, não medição por
  tokenizador.

## Correções (fase Redigir)

Autorização: após o relatório, o usuário escolheu **"Corrigir todas (A1–A12)"**
(2026-07-04). Aplicadas via semântica `revise-skill` — sem mudar a intenção das
skills; as descriptions mudaram apenas onde o achado era o próprio gatilho
(A1, A2, A3, A8). Diff da fase: 10 arquivos, **447 inserções / 500 remoções**
(saldo −53 linhas — curadoria por subtração, E2).

| Achado | Correção aplicada |
|---|---|
| A1 | prosa-sobria: "em português" + contraparte na description; sober-prose: "in English, or in any language without a dedicated counterpart" + contraparte PT. Par 5 do G3 resolvido textualmente; coerente com a tabela de língua da prosa-completa (sober-prose segue default para línguas terceiras). |
| A2 | verbosity-reduction: fronteira negativa na description (curadoria de arquivo → readme-writer; criativa/persuasiva; detalhe pedido) + seção "When NOT to apply" com vizinhas e desempate. QG§6 satisfeito. |
| A3 | pt-br-fullness: description reescrita (1.203 → 852 chars) cobrindo as 11 categorias, exclusões preservadas (G2 intacta). |
| A4 | methodological-rigor: segundo exemplo completo e "Como acionar" removidos; "Sinais de que terminou" fundido nos critérios de completude. Corpo: 23.026 → 19.673 chars (~5,8k → ~4,9k tokens est.; 432 → 337 linhas). R1 satisfeito. |
| A5 | methodological-rigor: SKILL.md e README.md traduzidos para EN (catalogação EN mantida; README raiz já dizia "English" — sem mudança lá). |
| A6 | prosa-sobria sincronizada: #12 e #13 portados com exemplos (C2), item do exemplo concreto em "O que fazer em vez", checklist 6 → 8 itens, segunda passada com os dois novos alvos. Paridade 13/13 com a sober-prose. |
| A7 | pt-br-fullness: "onze categorias"; prosa-completa: passo 4 enumera as 11. |
| A8 | prosa-completa: description declara os dois modos (pedido de revisão integral OU /prosa-completa) e a subsunção ("executa as componentes por dentro; não as re-aplique em paralelo"); "Ordem de aplicação" repete a instrução; as três componentes ganharam a deferência recíproca no "quando não aplicar". Conjunto exposto do pior caso cai de 4–6 nominais para agregadora + readme-writer. |
| A9 | Vizinhas nomeadas com desempate nos corpos: prosa-sobria e sober-prose (contraparte, VC, prosa-completa); methodological-rigor ganhou "When NOT to apply" (sober-prose = forma da expressão; readme-writer = README; exemplos dos dois lados). |
| A10 | "Architectural mitigation" movida do corpo da VC para o README da skill (com ponteiro no "When NOT to apply"). |
| A11 | pt-br-fullness: prioridade de varredura §1–§3 declarada e rotulada [preferência editorial]; única medição citada continua sendo a da §2 (LDM-PT). |
| A12 | Typos "acharcos" (9 linhas) eliminados pela tradução A5. |

**Medidas pós-correção (mesmo método da Analisar):** todas as descriptions
≤ 1.024 chars (máx.: prosa-completa, 981); methodological-rigor a 19.673 chars
≈ 4,9k tokens est. (< 5.000). **Residuais declarados:** pt-br-fullness a
20.175 chars ≈ 5.044 tokens est. — segue INCONCLUSIVO na fronteira de R1 (a
nota de prioridade custou +276 chars; cortar substância estaria fora do escopo
autorizado); densidade da MR reduzida mas ainda alta (protocolo em duas formas:
abordagem + checklist — fusão total mudaria a intenção da skill). Ajuste de
calibração fora da lista: a linha "Validada — testada contra documentos reais"
do README da MR virou "Evidence status" com a declaração de que não há par
com/sem medido (persona §8.5); o fecho aforístico "O padrão está consolidado…"
foi removido na tradução (sober-prose #1) — ambos declarados aqui.

## Decisões

| Decisão | Alternativas consideradas | Justificativa | Data |
|---------|---------------------------|---------------|------|
| Revisão produz evidência, não correção: nenhuma skill alterada nesta fase | (a) corrigir achados triviais no mesmo passo; (b) revisar e corrigir skill a skill | Persona §1.4 (crítica em passo separado) e §8.6 (humano decide prioridade; ações irreversíveis exigem autorização); evita misturar diagnóstico com emenda | 2026-07-04 |
| Escopo dos protocolos: G1–G3/R1–R4 (não E1–E3, D, C, V) | (a) auditoria completa sob todos os protocolos; (b) incluir C1–C3 para as skills de prosa (persona B) | Escopo registrado da candidata no memory.md; E1 exige par com/sem (fora do alcance estático); achados de natureza C entram como nota rotulada, sem ampliar a revisão | 2026-07-04 |
| **Arquitetura de língua (A1):** prosa-sobria = prosa em português; sober-prose = inglês e default para línguas sem contraparte dedicada | (a) declarar língua nas duas simetricamente (PT ↔ EN estrito); (b) sober-prose universal sem contraparte declarada | Coerente com a tabela de gating da prosa-completa (sober-prose "aplicar com cautela" em outras línguas) e com a Key Decision das contrapartes; o desempate vira texto nas duas descriptions (G3: reescrever, não confiar no bom senso) | 2026-07-04 |
| **Direção da monolinguidade (A5):** traduzir a methodological-rigor para EN (não re-rotular como PT) | (a) re-rotular como skill PT e ajustar README raiz; (b) manter mista e registrar como aceita | A description já era EN, o catálogo (memory.md e README raiz) já a lista como EN e as irmãs de auditoria/qualidade em EN (sober-prose, readme-writer) formam o conjunto EN; traduzir alinha tudo sem churn de catálogo | 2026-07-04 |
| **Primazia da pt-br-fullness (A11) rotulada [preferência editorial]** | (a) declarar §1–§3 como "mais críticas" sem rótulo; (b) não declarar primazia (aceitar o achado) | C1: só a §2 tem medição externa citada (LDM-PT); declarar criticidade medida sem medição fabricaria racional (§1.5) — o rótulo separa preferência editorial de viés medido | 2026-07-04 |

## Blockers & Notas

- `readme-writer` não é re-revisada em G1–G2/R1–R4: nasceu sob os protocolos na
  007 (gatilho aprovado G1–G3; corpo sob R1–R4). Entra como vizinha nos pares
  G3 — o registro da 007 é reaproveitado.

## Referências

- **Oportunidade:** O-005 em [backlog.md](../backlog.md)
- **Intake:** [intake/Backlog/revisar-catalogo.md](../intake/Backlog/revisar-catalogo.md)
- **Protocolos de autoria:** [persona.md](../persona.md) (G1–G3, R1–R4, §1, §8, §9)
- **Registro G3 anterior:** [007-consolidar-readme-writer.md](007-consolidar-readme-writer.md) (Especificação)
- **Key Decisions pertinentes:** [memory.md](../memory.md) (`prosa-completa` agregadora; contrapartes PT↔EN)
