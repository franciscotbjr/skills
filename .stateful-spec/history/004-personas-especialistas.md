# 004 — personas-especialistas

- **Início:** 2026-07-04
- **Conclusão:** 2026-07-04
- **Status:** done
- **Tipo:** chore (pesquisa/persona)
- **Fase:** Analisar → Redigir → Verificar
- **Origem:** O-001 ([backlog.md](../backlog.md)) ← [intake/Backlog/prd.md](../intake/Backlog/prd.md)

## Objetivo

Pesquisar e estruturar **duas personas especialistas** para as evoluções deste
repositório, de forma análoga à pesquisa de persona SDD feita para o
stateful-spec (pesquisa pura no vault Jandi → consolidação em
`AGENTS.md`/`persona.md`/`persona-reference.md` do repo stateful-spec):

- **Persona A:** especialista em Skills para agentes de IA de propósito geral.
- **Persona B:** especialista em vieses linguísticos verificados nos outputs de
  LLMs (o caso das skills já existentes aqui).

A pesquisa na internet busca artigos que tragam **rigor conceitual e bases
empíricas** à estruturação dessas personas. O arquivo de pesquisa pura — anterior
a qualquer plano de aplicação neste repo — será criado em
`D:\franciscotbjr\Documents\Explorações\Jandi`, no modelo de
`Agente - Persona Especialista em Pesquisa, Design e Curadoria de Metodologias SDD.md`.

**Fora de escopo nesta iteração:** alterar as skills existentes.

## Critérios de aceite

- [x] Entendimento comum fechado via protocolo do PRD: perguntas exaustivas,
      **uma por vez**, percorrendo cada ramo da árvore de decisões e documentando
      alternativas consideradas + motivo de cada escolha.
- [x] Referências do PRD lidas e o modelo extraído (pesquisa SDD no vault;
      `AGENTS.md`, `persona.md` e `persona-reference.md` do stateful-spec).
- [x] Pesquisa na internet com fontes citadas (rigor conceitual + bases empíricas)
      cobrindo as duas personas.
- [x] Arquivo de pesquisa pura criado no vault Jandi, seguindo o modelo indicado.
- [x] Nenhuma alteração nas skills existentes.

## Tarefas

- [x] Ler os arquivos de referência do PRD (vault Jandi + repo stateful-spec).
- [x] Conduzir o questionário de alinhamento (uma pergunta por vez; responder
      sozinho o que a base do repo já responde) e registrar cada decisão na
      tabela abaixo.
- [x] Pesquisar artigos/papers: personas e expertise em prompts de agentes,
      autoria de skills, vieses linguísticos e retóricos de LLMs.
- [x] Redigir o arquivo de pesquisa pura no vault (modelo Jandi).
- [x] Validar com o usuário e fechar a iteração (aplicação no repo fica para
      iteração futura).

## Session Log

| Timestamp | Operation | Summary |
|-----------|-----------|---------|
| 2026-07-04 11:47 | start-session | Sessão aberta; O-001 triado e promovido; iteração 004 criada (fase Analisar). |
| 2026-07-04 11:59 | analisar | Referências do PRD lidas (2 docs do vault + 3 do stateful-spec); questionário de alinhamento concluído — 8 decisões registradas; entendimento comum confirmado; execução inline iniciada. |
| 2026-07-04 12:27 | redigir/verificar | Pesquisa inline das 9 frentes concluída (nenhuma vazia; B9 a mais rala, declarada). Documento escrito no vault Jandi (~40 fontes, formato do modelo SDD). Crítica adversarial em passo separado: 3 correções aplicadas (atribuição Opus 4.6; ponte interpretativa rebaixada em 6.2; ótimo 2–3 skills corrigido para "por tarefa"). Pendente: validação do usuário. |
| 2026-07-04 12:31 | end-session | Sessão encerrada. Sem incidentes no log; intake sem itens `ready`. Iteração permanece in-progress: falta só a validação do usuário sobre o doc do vault. |
| 2026-07-04 13:06 | resume-session | Sessão retomada; usuário validou o doc do vault; iteração fechada (done). |
| 2026-07-04 13:18 | write-commit-message | Mensagem bilíngue gerada e registrada: "Fecha a iteração 004: pesquisa das duas personas especialistas validada no vault; O-001 triado e estado stateful-spec persistido" (+ espelho EN). Commit executado a pedido do usuário. |
| 2026-07-04 13:18 | end-session | Sessão encerrada; sem incidentes; intake sem itens `ready`. Estado versionado no branch feature/004-personas-especialistas. Próximo sugerido: iteração de aplicação (persona.md + binding no AGENTS.md), a registrar em intake/Backlog. |

## Decisões

| Decisão | Alternativas consideradas | Justificativa | Data |
|---------|---------------------------|---------------|------|
| **Arquitetura:** Persona B estende a Persona A (base + especialização) | (a) independentes e alternadas por tarefa; (b) duas na pesquisa, fundidas na aplicação | A é a base de autoria válida para qualquer skill; B acrescenta só o domínio linguístico — compartilha frentes e evita duplicação | 2026-07-04 |
| **Entregável:** um único arquivo com as duas personas (parte A = base; parte B = deltas) | Dois arquivos, com B referenciando A | Espelha a relação base+extensão no próprio artefato; uma só nota de método e uma só seção de Fontes | 2026-07-04 |
| **Persona atual do `AGENTS.md`:** começar do zero, sem ancorar nela | Tratá-la como insumo a validar/corrigir na pesquisa | Evita enviesar a pesquisa pelo texto já escrito; o confronto fica para a iteração de aplicação | 2026-07-04 |
| **Estrutura:** sem seção de "Aplicação ao repo skills" (sem análoga ao §9 do modelo SDD) | Incluir aplicação-esboço para paridade estrutural com o modelo | Coerência com o PRD ("pesquisa pura, antes do plano de aplicação") e com a decisão de começar do zero | 2026-07-04 |
| **Frentes de pesquisa:** 9 aprovadas — A: formato Agent Skills; evidência empírica de instruções/contexto; instruction-following; ativação/colisão de skills; contrária de A. B: vieses retóricos RLHF; translationese EN→pt-BR; homogeneização estilística; contrária de B | Redesenhar/fundir frentes; priorizar B sobre A | Segue o protocolo P1 do modelo (frentes declaradas antes da busca), com as frentes contrárias obrigatórias | 2026-07-04 |
| **Herança sem re-pesquisa:** eficácia de personas em LLMs + postura epistêmica/calibração vêm do doc SDD como herança citada, com re-verificação pontual | Refazer as duas frentes do zero | Espelha o precedente do próprio modelo (SDD herdou das "zonas cinzentas"); evita duplicar pesquisa já ancorada | 2026-07-04 |
| **Nome do arquivo:** `Agente - Personas Especialistas em Autoria de Agent Skills e em Vieses Linguísticos de LLMs.md` | Singular com "(base + extensão linguística)" no título | Plural explícito nomeia as duas partes do documento | 2026-07-04 |
| **Execução da pesquisa:** inline nesta sessão (WebSearch/WebFetch sequencial, frente a frente) | Deep-research multi-agente; pausar para sessão dedicada | Escolha do usuário: mais leve, uma só linha de contexto; a escolha também confirmou o entendimento comum | 2026-07-04 |

## Notas

- O PRD exige o protocolo interativo de perguntas **antes** de qualquer execução;
  a fase Analisar começa por ele.
- Duas personas, dois públicos: a Persona B cobre o domínio atual do repo; a
  Persona A amplia para autoria de skills em geral.
- **Retomada (para `resume-session`):** o entregável está pronto em
  `D:\franciscotbjr\Documents\Explorações\Jandi\Agente - Personas Especialistas em Autoria de Agent Skills e em Vieses Linguísticos de LLMs.md`;
  falta apenas o usuário validá-lo. Ao validar: marcar o último critério de
  aceite, Status → done, mover para Recent Completions e atualizar o History
  Index. Se houver ajustes, tratá-los antes de fechar. Aplicação no repo
  (consolidação persona.md + binding no AGENTS.md) é iteração futura — candidata
  a nova entrada no intake/backlog.
- **Premissas assumidas sem pergunta** (respondidas pela base, conforme o PRD):
  formato do doc segue o modelo SDD (nota de honestidade do método no topo,
  seções numeradas, capacidades como protocolos gatilho→passos→saída observável,
  evidência contrária como achado de primeira classe, `# Fontes` por tema);
  idioma PT-BR (voz do vault); Persona B cobre EN **e** pt-BR (as skills atuais
  miram os dois); ordem de grandeza espelha o doc modelo (~9 seções, ~40 fontes).

## Referências

- **Oportunidade:** O-001 em [backlog.md](../backlog.md)
- **PRD:** [intake/Backlog/prd.md](../intake/Backlog/prd.md)
- **Modelo (pesquisa pura):** `D:\franciscotbjr\Documents\Explorações\Jandi\Agente - Persona Especialista em Pesquisa, Design e Curadoria de Metodologias SDD.md`
- **Concretização de referência:** `D:\franciscotbjr\Documents\Explorações\Jandi\Agente - System Prompt - Especialista em Pesquisa, Design e Curadoria de Metodologias SDD.md`
- **Consolidação de referência:** `D:\development\public\stateful-spec` (`AGENTS.md`, `.stateful-spec/persona.md`, `.stateful-spec/persona-reference.md`)
