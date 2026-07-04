# 007 — consolidar-readme-writer

- **Início:** 2026-07-04
- **Conclusão:** 2026-07-04
- **Status:** done
- **Tipo:** new-skill (`readme-writer`, EN)
- **Fase:** Especificar → Redigir → Verificar (ciclo concluído; validado pelo
  usuário)
- **Origem:** O-004 ([backlog.md](../backlog.md)) ← [intake/Backlog/consolidar-readme-writer.md](../intake/Backlog/consolidar-readme-writer.md)

## Objetivo

Consolidar no catálogo a skill **`readme-writer`** — especialista em escrita de
README files — derivando `SKILL.md` + `README.md` (EN) do doc de pesquisa da
iteração 006 (`D:\franciscotbjr\Documents\Explorações\Jandi\Agente - Persona
Especialista em Escrita de README Files.md`): os três ofícios (captar
fundamentos F1–F3, projetar a comunicação P1–P5, manter o registro vivo M1–M3),
as fronteiras e o checklist, condensados em corpo procedimental sob R1–R4, com
gatilho (`description`) passando G1–G3.

Decisões herdadas da 006 (não reabertas): skill em EN; alcance genérico com
adaptação ao público; contraparte PT-BR futura sem compromisso. Persona
vinculada: **A** — o objeto é comunicação de READMEs, não a linguagem do modelo.

**Fora de escopo:** alterar as skills existentes; criar a contraparte PT-BR.

## Critérios de aceite

- [x] Diretório `readme-writer/` com exatamente `SKILL.md` + `README.md` (EN,
      monolíngue).
- [x] `description` passa em G1 (o quê + quando + palavras-chave; ~860 chars),
      G2 (fronteira negativa com vizinhos nomeados) e G3 (teste de colisão
      contra o catálogo, registrado nesta iteração).
- [x] Corpo procedimental sob R1–R4: 206 linhas, regras críticas (F1/P1/M1) no
      primeiro terço, enquadramento positivo com fronteira.
- [x] Anti-padrões nomeados (7), pares antes/depois (4) e seção "When NOT to
      apply" presentes.
- [x] Toda afirmação normativa ancorada em fonte (âncoras do doc da 006);
      evidência empírica rotulada **[empirical]** e prescrição de praticante
      **[practitioner]**.
- [x] A prosa da própria skill segue `sober-prose` (5 violações encontradas e
      corrigidas no passo de crítica — ver Session Log).
- [x] README raiz atualizado (linha `readme-writer` na tabela).
- [x] Checklist de saída do `persona.md` §9 executado em passo separado de
      crítica, com resultado (incl. INCONCLUSIVOs) registrado no Session Log.

## Tarefas

- [x] Especificar: rascunhar gatilho (G1/G2) e rodar o teste de colisão G3
      contra as 6 skills do catálogo, registrando pares e resultado.
- [x] Redigir `readme-writer/SKILL.md` a partir do doc de pesquisa.
- [x] Redigir `readme-writer/README.md` (uso, quando aplica/não aplica,
      cross-references).
- [x] Atualizar a tabela do README raiz.
- [x] Verificar: Quality Gates §6 + checklist §9 em passo separado; registrar no
      Session Log.

## Session Log

| Timestamp | Operation | Summary |
|-----------|-----------|---------|
| 2026-07-04 15:31 | start-session | Sessão aberta; intake sem itens `ready`; foco escolhido: consolidar `readme-writer`. Item consolidar-readme-writer.md criado e triado a O-004; iteração 007 criada (fase Especificar); branch skill/readme-writer. |
| 2026-07-04 15:33 | especificar | Gatilho rascunhado (G1/G2) e teste de colisão G3 rodado contra as 6 skills: 5 tarefas ambíguas, nenhuma reescrita de vizinha exigida, co-disparos legítimos (sober-prose, pt-br-fullness), conjunto exposto 2–3. Registrado na seção Especificação. |
| 2026-07-04 15:36 | redigir | `readme-writer/SKILL.md` (206 linhas) + `README.md` derivados do doc da 006: 3 regras críticas no primeiro terço (F1/P1/M1), procedimento em 3 passos, 7 anti-padrões, 4 pares antes/depois, self-check, "When NOT to apply", nota de status da evidência; rótulos [empirical]/[practitioner]. README raiz atualizado. |
| 2026-07-04 15:40 | verificar (crítica em passo separado) | Passo adversarial: 5 correções aplicadas — 1 factual (doc do vault chama status de "segunda categoria mais ausente", mas 21,4% < 25,7% torna status a MAIS ausente; skill corrigida para não propagar) + 4 violações sober-prose ("gets an anchor or gets cut", "decoration, not structure", "never a gap to fill", fecho aforístico de M3, ternário da abertura). Gates §6: todos passam. Checklist §9: âncoras resolvem; evidência contrária no corpo; nota de método com INCONCLUSIVOs (eficácia ex ante sem par com/sem; sem evidência de comprimento ideal); nada removido/obsoletado pela skill (adição ao catálogo); G1–G3 pass. Pendente: revisão do usuário; commit/PR sob demanda. |
| 2026-07-04 19:51 | write-commit-message | Usuário validou a skill ("job done" + pedido de commit — mesmo critério da 005/006). Mensagem bilíngue gerada; commit na branch skill/readme-writer; texto de PR entregue em MD. |
| 2026-07-04 19:51 | end-session | Sessão encerrada; iteração 007 fechada (done). Sem entradas [INCIDENT] no log; intake sem itens `ready`. Estado movido para Recent Completions/History Index. Próximos sugeridos: revisão do catálogo sob G1–G3/R1–R4, contraparte PT-BR da readme-writer, correção do achado factual no doc do vault. |

## Especificação (fase Especificar)

**Gatilho (rascunho aprovado para o frontmatter):** dispara ao escrever,
reestruturar ou revisar um **README** (página de entrada de repositório,
biblioteca, ferramenta, dataset ou projeto documentation-first) — criação do
zero, auditoria de primeira impressão, escolha de estrutura de seções,
sincronização com o repositório. Palavras-chave: README, project front page,
repository entry point, badges, quick start. Fronteira negativa (G2):
documentação profunda (tutoriais, how-to, referência de API — Diátaxis),
changelogs, comentários de código e estilo de prosa geral (vizinho:
`sober-prose`, que pode co-disparar legitimamente sobre a prosa do README).

**Teste de colisão G3 (contra as 6 skills do catálogo):**

| Tarefa ambígua | Dispara | Não dispara | Veredito |
|----------------|---------|-------------|----------|
| "Write a README for my new library" | readme-writer + sober-prose (estilo da prosa) | demais | Co-disparo legítimo: conteúdo/estrutura vs. estilo. Conjunto exposto = 2. |
| "Revise a documentação do meu projeto" (ambígua) | readme-writer só se o alvo for o README | methodological-rigor (não é auditoria de argumento) | Fronteira declarada na description resolve: docs profundas ficam fora. |
| "Make my project's README shorter" | readme-writer (M2, subtração por pergunta do público) | verbosity-reduction (alvo dela é resposta gerada do agente, não curadoria de arquivo) | Desempate declarado no "When NOT to apply". |
| "Audit this analysis before publishing" | methodological-rigor | readme-writer (não é README) | Sem colisão. |
| "Escreva o README bilíngue do repo" (PT) | readme-writer (M3) + pt-br-fullness (texto PT) | — | Co-disparo legítimo. Conjunto exposto = 2–3. |

Resultado: nenhuma colisão exige reescrita de `description` vizinha; co-disparos
são complementares e o conjunto exposto por tarefa fica em 2–3 skills (ótimo de
G3).

## Decisões

| Decisão | Alternativas consideradas | Justificativa | Data |
|---------|---------------------------|---------------|------|
| **Regras críticas do primeiro terço (R3):** F1 (fundamentos antes da forma), P1 (primeiro terço decide) e M1 (desatualizado pior que incompleto) | (a) usar os três ofícios como as três regras; (b) elevar P5 (exemplo antes de abstração) ao topo | São as três com evidência mais direta de modo de falha: lacuna do "porquê" 25,7% (Prana et al.), escaneamento 79% (NN/g), inconsistência versão-doc ~80% (Does Documentation Matter?) | 2026-07-04 |
| **Corpo enxuto (~1/3 do doc de pesquisa):** protocolos condensados em procedimento de 3 passos + anti-padrões + pares + checklist, sem as seções de método da pesquisa | (a) transplantar os 11 protocolos com gatilho/passos/saída na íntegra; (b) só checklist | R2 (procedimental, não panorâmico) e R3 (adesão degrada com densidade); o racional integral permanece ancorado no doc do vault, citado no README da skill | 2026-07-04 |

## Notas

- A skill nasce como **hipótese ex ante com fundamentação citada** (E1): não há
  par com/sem skill medido. Declarar, não omitir.
- **Achado para o vault (fora do escopo desta iteração):** o doc
  `Agente - Persona Especialista em Escrita de README Files.md` chama o status
  do projeto de "a segunda categoria mais ausente" (§5, F1), mas pelos números
  de Prana et al. que o próprio doc cita (When 21,4% < Why 25,7%) o status é a
  categoria **mais** ausente. A skill usa a forma corrigida; a correção do doc
  do vault fica a cargo do usuário.
- Vizinho de gatilho mais próximo no catálogo: `sober-prose` (estilo da prosa em
  qualquer texto expositivo) — `readme-writer` cuida de conteúdo, estrutura e
  audiência do artefato README; co-disparo é legítimo e deve ser declarado.

## Referências

- **Oportunidade:** O-004 em [backlog.md](../backlog.md)
- **Intake:** [intake/Backlog/consolidar-readme-writer.md](../intake/Backlog/consolidar-readme-writer.md)
- **Pesquisa (entregável da 006):** `D:\franciscotbjr\Documents\Explorações\Jandi\Agente - Persona Especialista em Escrita de README Files.md`
- **Iteração anterior da linha O-003:** [006-readme-writer.md](006-readme-writer.md)
- **Protocolos de autoria:** [persona.md](../persona.md) (G1–G3, R1–R4, E1–E3, §9)
