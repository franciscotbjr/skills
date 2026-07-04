# 005 — aplicar-personas

- **Início:** 2026-07-04
- **Conclusão:** 2026-07-04
- **Status:** done
- **Tipo:** chore (consolidação de persona)
- **Fase:** Analisar → Redigir → Verificar
- **Origem:** O-002 ([backlog.md](../backlog.md)) ← [intake/Backlog/aplicar-personas.md](../intake/Backlog/aplicar-personas.md)

## Objetivo

Consolidar no repositório a pesquisa das duas personas (iteração 004, doc do
vault Jandi), nos moldes da consolidação SDD feita no repo stateful-spec:

- Derivar um **`persona.md` operacional** em `.stateful-spec/` a partir do doc
  de pesquisa: Persona A (base — autoria de Agent Skills em geral) + Persona B
  (extensão — vieses linguísticos de outputs de LLMs).
- Fazer o **binding no `AGENTS.md`**, confrontando a Persona atual (escrita
  antes da pesquisa) com o que a pesquisa sustenta — confronto explicitamente
  adiado na 004 para esta iteração.
- Avaliar se cabe um `persona-reference.md` (rastro pesquisa → persona), como
  no stateful-spec.

**Fora de escopo:** alterar as skills existentes.

## Critérios de aceite

- [x] Doc de pesquisa do vault relido e confrontado com a Persona atual do
      `AGENTS.md`; divergências documentadas (o que a pesquisa sustenta,
      corrige ou não cobre) — ver seção Confronto.
- [x] `persona.md` criado em `.stateful-spec/` com as duas personas
      (A = base; B = extensão), derivado da pesquisa com rastreabilidade às
      fontes.
- [x] Binding feito no `AGENTS.md` (seção Persona atualizada/apontando para o
      `persona.md`), sem quebrar as convenções existentes.
- [x] Decisão registrada sobre `persona-reference.md` (criar ou não, e por quê).
- [x] Nenhuma alteração nas skills existentes.
- [x] Quality Gates aplicáveis verificados (prosa sóbria nos docs novos;
      bilinguismo apenas onde a convenção exige).
- [x] Validação do usuário sobre os artefatos consolidados (implícita no pedido
      de commit + encerramento; usuário ajustou o `persona-reference.md` antes —
      ver Session Log).

## Tarefas

- [x] Reler o doc do vault (`Agente - Personas Especialistas em Autoria de
      Agent Skills e em Vieses Linguísticos de LLMs.md`) e a consolidação de
      referência do stateful-spec (`AGENTS.md`, `persona.md`,
      `persona-reference.md`).
- [x] Confrontar a Persona atual do `AGENTS.md` com a pesquisa; listar o que
      fica, o que muda e o que sai (com justificativa ancorada nas fontes).
- [x] Decidir a arquitetura da consolidação (conteúdo no `AGENTS.md` vs.
      ponteiro para `persona.md`; criar ou não `persona-reference.md`).
- [x] Redigir `persona.md` (e `persona-reference.md`, se decidido).
- [x] Atualizar o `AGENTS.md` com o binding.
- [x] Verificar Quality Gates (crítica em passo separado, registrada no
      Session Log).
- [x] Validar com o usuário e fechar a iteração.

## Confronto — Persona antiga do `AGENTS.md` × pesquisa

**Sai (a pesquisa contradiz):**

- *Enquadramento por credencial* ("especialista com formação de linguista") —
  personas declarativas não adicionam competência (Zheng et al.; Playing
  Pretend, `persona-reference.md` §2); a definição correta é por protocolos
  com saída observável.
- *Listas de capacidades sem protocolo* ("Competências linguísticas" /
  "Competências de construção") — "capacidade sem protocolo é rótulo" (§2);
  cada item vira protocolo com gatilho e saída, ou sai.
- *Enumeração dos fenômenos pt-BR* (clíticos, crase, subjuntivo, pro-drop...)
  — redundante com o catálogo da própria `pt-br-fullness` (o texto antigo
  admitia: "os fenômenos que `pt-br-fullness` cataloga"); reprova no teste de
  subtração (E2), e contexto redundante custa sem melhorar (AGENTbench, §4.6).
- *Repetição das convenções do repo* dentro da persona — já vivem nas seções
  próprias do `AGENTS.md` (Skill structure, Bilingual convention, Branch
  naming); duplicação reprovada pelo mesmo teste.

**Fica, transformado em protocolo:**

- "description como condição de gatilho, específica e acionável" → G1–G3
  (o quê + quando + palavras-chave; fronteira negativa; teste de colisão).
- "Fundamentação em fonte" → regra epistêmica 1 (âncora obrigatória) + C1.
- "Padrão de conteúdo: anti-padrões, antes/depois, checklist, Quando NÃO
  aplicar" → D1, C2, C3/G2 — a pesquisa endossa e explica o porquê (penhasco
  de hipercorreção, ambiguidade de mesma capacidade).
- Diagnóstico de translationese/vieses RLHF → domínio da Persona B com
  catálogo ancorado (D1) e distinção viés × sintoma (D2).
- Sensibilidade pt-BR × pt-PT → V1 (variedade declarada, travessia
  justificada — LDM-PT e a tipologia de omissão são de pt europeu).
- Lista de skills de referência → uma linha no binding, mapeando o catálogo
  às personas (skills de prosa sob B; `methodological-rigor` sob A).

**Novo (a persona antiga não tinha):**

- Postura epistêmica completa (5 regras), ofícios de corpo (R1–R4) e de
  avaliação/curadoria (E1–E3), fronteiras negativas (8) e checklist de saída
  com Sensor declarado no binding.

## Session Log

| Timestamp | Operation | Summary |
|-----------|-----------|---------|
| 2026-07-04 13:22 | start-session | Sessão aberta; item registrado em intake/Backlog, promovido a O-002 e iteração 005 criada (fase Analisar). |
| 2026-07-04 13:35 | analisar/redigir/verificar | Confronto Persona antiga × pesquisa documentado (4 saídas, 6 transformações, 3 adições). Arquitetura decidida (modelo stateful-spec, 4 decisões registradas). Criados `persona.md` (operacional) e `persona-reference.md` (verbatim do vault — verificado por diff: IDENTICAL); binding ambiente no `AGENTS.md`; estrutura do `project-definition.md` e constraint do `memory.md` atualizadas. Checklist §9 executado em passo separado: aprovado; skills existentes intocadas. Pendente: validação do usuário. |
| 2026-07-04 14:38 | write-commit-message | Usuário validou os artefatos (pedido de commit + encerramento) após editar o `persona-reference.md`: removeu o preâmbulo em blockquote (proveniência + nota de método), alinhando o formato ao `persona-reference.md` do stateful-spec; a nota de método integral permanece no doc do vault. Mensagem bilíngue gerada e commit executado a pedido; texto de PR entregue em MD. |
| 2026-07-04 14:38 | end-session | Sessão encerrada; iteração 005 fechada (done). Sem incidentes no Session Log; intake sem itens `ready` (ambos os itens `triaged`). Estado movido para Recent Completions/History Index. |

## Decisões

| Decisão | Alternativas consideradas | Justificativa | Data |
|---------|---------------------------|---------------|------|
| **Arquitetura:** modelo stateful-spec — `persona.md` operacional + `persona-reference.md` + binding fino no `AGENTS.md` | (a) persona completa dentro do `AGENTS.md`; (b) só `persona.md`, sem referencial | `AGENTS.md` carrega em toda sessão — contexto redundante custa sem melhorar (AGENTbench, ref. §4.6); paridade com a consolidação de referência facilita manutenção cruzada | 2026-07-04 |
| **`persona-reference.md`: criar**, como cópia verbatim do doc do vault | (a) apontar para o caminho do vault; (b) resumir a pesquisa no repo | O repo é público e o vault é local — âncora que não resolve é buraco no harness; resumo destruiria a proveniência (fold verbatim, não paráfrase) | 2026-07-04 |
| **Persona antiga substituída integralmente** pelo binding (nada preservado literalmente) | Emendar a seção antiga mantendo as listas de competências | O confronto reprovou o formato (credencial + rótulos sem protocolo) e o conteúdo redundante; o que a pesquisa sustenta foi transformado em protocolo no `persona.md`, não copiado | 2026-07-04 |
| **Binding ambiente com escopo A/B declarado:** A para toda autoria; B quando o objeto é a linguagem do modelo; peso escala com o tamanho da tarefa | Binding só nas operações de autoria (`create-skill-spec` etc.) | Espelha o binding do stateful-spec (ambient + carve-outs); as referências existentes das operations à "Persona do `AGENTS.md`" continuam resolvendo | 2026-07-04 |

## Notas

- A decisão da 004 ("começar do zero, sem ancorar na Persona atual") deixou o
  confronto Persona atual × pesquisa para esta iteração — é a primeira tarefa
  da fase Analisar.
- O modelo de consolidação é o do stateful-spec: pesquisa pura no vault →
  `persona.md` operacional no repo → binding no `AGENTS.md`.

## Referências

- **Oportunidade:** O-002 em [backlog.md](../backlog.md)
- **Item de intake:** [intake/Backlog/aplicar-personas.md](../intake/Backlog/aplicar-personas.md)
- **Pesquisa (entregável da 004):** `D:\franciscotbjr\Documents\Explorações\Jandi\Agente - Personas Especialistas em Autoria de Agent Skills e em Vieses Linguísticos de LLMs.md`
- **Consolidação de referência:** `D:\development\public\stateful-spec` (`AGENTS.md`, `.stateful-spec/persona.md`, `.stateful-spec/persona-reference.md`)
- **Iteração anterior:** [004-personas-especialistas.md](004-personas-especialistas.md)
