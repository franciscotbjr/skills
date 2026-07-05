---
name: prosa-completa
description: >-
  Skill agregadora que aplica em uma única passada as três skills de qualidade
  de prosa do vault: sober-prose (suprime viéses retóricos de RLHF),
  verbosity-reduction (remove Verbosity Compensation) e pt-br-fullness
  (preserva artigos, conectivos e demais elementos coesivos do pt-BR). Use
  quando estiver redigindo ou revisando prosa expositiva, técnica, filosófica
  ou analítica e quiser cobertura completa em uma só checagem. A pt-br-fullness
  é aplicada apenas se o texto-alvo for pt-BR; a sober-prose e a
  verbosity-reduction são aplicadas independentemente da língua. Não substitui
  as três skills individuais — é um atalho de invocação combinada com ordem
  explícita de aplicação, gating de língua e resolução de conflitos. Dispara
  em pedidos de revisão completa ou integral de texto longo e via
  /prosa-completa; quando dispara, executa as três componentes por dentro da
  própria ordem — não as re-aplique em paralelo. Para escopo específico,
  prefira a skill individual correspondente.
---

# Prosa Completa

## O que esta skill faz

Reúne em uma única chamada as três skills de qualidade de prosa do vault e define a ordem em que devem ser aplicadas, o gating de língua e a resolução das poucas tensões aparentes entre elas. As três continuam acionáveis isoladamente; a `prosa-completa` é um atalho para quando se quer cobertura combinada sem ter que pré-diagnosticar qual das três dimensões está pior.

As três skills componentes:

- **sober-prose** — suprime viéses retóricos típicos do treinamento RLHF: fechamentos aforísticos, construções "X é Y, não Z", paralelismos ternários, adjetivos enfáticos, dashes decorativos, jargão cru usado como âncora definicional, metáfora definicional vinda de outro domínio, aspas decorativas (scare quotes) e fragmentos imitando antítese. Também recomenda **uma adição** — exemplo concreto ancorando alegação abstrata sobre o funcionamento de um mecanismo.
- **verbosity-reduction** — remove Verbosity Compensation: spans compressíveis sem perda de informação que sobrevivem na resposta como compensação de incerteza interna do modelo.
- **pt-br-fullness** — preserva os elementos morfossintáticos e coesivos que o português brasileiro usa com mais frequência do que o inglês: artigos definidos, conectivos discursivos, regência verbal, pronomes oblíquos, modo subjuntivo, crase e pro-drop.

## Quando acionar

Casos típicos de uso da `prosa-completa`:

- Prosa expositiva longa (mais de três ou quatro parágrafos), em que percorrer as três skills isoladamente custa três invocações.
- Pedido genérico de "revisão completa" pelo usuário, sem indicação de qual dimensão está em jogo (retórica, densidade ou fidelidade linguística).
- Iteração com o usuário sobre um documento que receberá várias rodadas — aplicar a `prosa-completa` na primeira passada reduz a quantidade de iterações posteriores em que o usuário aponta resíduos um a um.
- Texto que está sendo gerado a partir de um pensamento ou prompt em inglês e que vai ser entregue em pt-BR (combinação típica em que os três tipos de drift aparecem juntos).

## Ordem de aplicação

Quando a `prosa-completa` conduz a revisão, as três componentes são executadas
por dentro desta sequência — não as acione em paralelo por fora. Aplique em
uma única passada:

1. **Gere ou edite o texto sem checklist.** O conteúdo precisa estar minimamente coerente antes que as três skills possam fazer trabalho útil. Tentar aplicar as três simultaneamente à primeira escrita produz paralisia.

2. **verbosity-reduction (primeiro filtro).** Identifique e remova os spans compressíveis sem perda. Esta passada reduz a área de trabalho das outras duas, porque parte dos casos que a sober-prose pegaria (p.ex., fechamentos aforísticos) também são VC e somem aqui. Atenção especial ao princípio de *commit the answer token first* e ao tratamento do uncertainty signal (localizar o hedge no span incerto em vez de marcá-lo globalmente).

3. **sober-prose (segundo filtro).** Aplique já com a "second pass" da própria skill incorporada — cace fragmentos de antítese (anti-pattern #10), jargão usado cru sem desdobramento (anti-pattern #11) e os resíduos retóricos que tipicamente sobrevivem à primeira aplicação. Se o texto-alvo for pt-BR, traduza mentalmente os exemplos das anti-patterns (que estão em inglês na SKILL.md original) para o equivalente em pt-BR antes de aplicar.

4. **pt-br-fullness (terceiro filtro, condicional).** Aplique apenas se o texto-alvo for pt-BR. Percorra as onze categorias da skill: artigos definidos, conectivos discursivos, regência verbal, pronomes oblíquos, modo subjuntivo, crase, pro-drop, estrangeirismos lexicais, calques semânticos, títulos sem sujeito e barra-como-ou. Se o texto for em inglês ou em outra língua, pule esta etapa.

5. **Passada cruzada final.** Releia o texto com as três checklists em mente ao mesmo tempo, procurando casos em que uma correção feita por uma das skills tenha introduzido drift de outra dimensão. É raro, mas acontece — ver a seção de resolução de conflitos abaixo.

## Gating de língua

A aplicabilidade de cada skill depende da língua do texto-alvo:

| Língua-alvo | sober-prose | verbosity-reduction | pt-br-fullness |
|---|---|---|---|
| pt-BR | aplicar | aplicar | aplicar |
| Inglês | aplicar | aplicar | pular |
| Outra língua | aplicar com cautela | aplicar | pular |
| Texto bilíngue ou com citações | aplicar ao texto principal | aplicar ao texto principal | aplicar se a parte principal for pt-BR |

Em qualquer caso, preserve citações literais — não as edite, mesmo que apresentem drift. A skill atua sobre o texto de autoria do modelo, não sobre a fonte citada.

## Resolução de conflitos

As três skills cobrem dimensões diferentes e raramente entram em conflito real. Quando houver tensão aparente, os quatro casos abaixo cobrem a maioria das situações:

**Conectivos variados (pt-br-fullness) vs paralelismos ternários (sober-prose).** A pt-br-fullness recomenda alternar entre *porém*, *contudo*, *no entanto*, *entretanto* para evitar repetição de *mas*. A sober-prose alerta contra paralelismos ternários (três adjetivos sinônimos em série, três frases na mesma estrutura). As duas não entram em conflito real: conectivos variados são informacionais (carregam relação lógica distinta entre orações); paralelismos ternários são decorativos (carregam ritmo simétrico sem informação extra). Mantenha os conectivos variados; corte os paralelismos decorativos.

**Hedges epistêmicos (sober-prose) vs Verbosity Compensation tipo 3 (verbosity-reduction).** A sober-prose recomenda hedges onde há incerteza ("provavelmente", "uma leitura possível"). A verbosity-reduction alerta contra hedges genéricos que são VC do tipo 3 (ambiguidade). A resolução está na localização do hedge: um hedge local, ligado ao span específico que é incerto, é informação e deve ser mantido. Um hedge global, que poderia preceder qualquer resposta, é VC e deve ser cortado. A regra prática: se o hedge não diz **o que** está incerto, é VC.

**Artigos antes de possessivo (pt-br-fullness) vs concisão (verbosity-reduction).** O artigo em *o meu carro* ocupa dois tokens em vez de um. A verbosity-reduction poderia, na superfície, sugerir cortá-lo. Não corte: o artigo carrega informação morfossintática (gênero, registro, marcação de prosa expositiva) que o pt-BR usa para processar o texto. Não é padding — é fidelidade linguística. Mantenha o artigo.

**Fragmentos sem verbo (sober-prose anti-pattern #10) vs prosa expositiva pt-BR.** A sober-prose alerta contra fragmentos imitando antítese ("a condição a performar, não problema a esconder"). A pt-br-fullness, indiretamente, também: prosa expositiva em pt-BR pede sentenças completas com verbo finito. As duas convergem na mesma direção — complete a sentença ou apague o fragmento.

**Exemplo concreto aditivo (sober-prose) vs verbose detail / VC #4 (verbosity-reduction).** A sober-prose, em *What to do instead*, passou a recomendar exemplo concreto após alegação abstrata sobre o funcionamento de um mecanismo — único caso em que a skill prescreve adição em vez de corte. A verbosity-reduction alerta contra parágrafos de explicação não pedida (VC tipo 4). A resolução está na **carga** do exemplo: se ele *mostra o mecanismo em ação* — um caso específico que o leitor não derivaria sozinho da alegação geral — é informacional e deve ser mantido; se ele *parafraseia a alegação em outras palavras* — recita o caso geral com outro vocabulário — é decorativo e é VC. Regra prática: o exemplo válido acrescenta um caso novo; o exemplo inválido reembrulha o caso geral.

## Checklist combinada antes de enviar

Antes de finalizar a resposta, percorra a checklist condensada. Os primeiros dez itens valem para qualquer língua; os quatro últimos só se aplicam quando o texto for pt-BR.

1. Há fechamento aforístico no final do parágrafo que não acrescenta informação? (sober-prose #1)
2. Há construções "X é Y, não Z" desnecessárias ou fragmentos imitando antítese? (sober-prose #2, #7, #10)
3. Há jargão técnico usado cru sem desdobramento prévio em prosa? (sober-prose #11)
4. Há metáfora em posição definicional cujo domínio-fonte (estatística, geologia, mecânica, biologia) importa um frame inferencial que não casa com o conceito sendo definido? (sober-prose #12)
5. Há aspas decorativas (scare quotes) em torno de uma palavra que pediria termo mais preciso ou compromisso sem hedging tipográfico? (sober-prose #13)
6. Há paralelismos ternários ou adjetivos enfáticos sem conteúdo funcional? (sober-prose #3, #4)
7. Há alegação abstrata sobre o funcionamento de um mecanismo que pediria exemplo concreto ancorador, e o exemplo, se presente, mostra o mecanismo em ação em vez de parafrasear a alegação? (sober-prose *What to do instead*; ver resolução de conflito com VC #4)
8. Há padding compressível sem perda de informação — restatement, decoração, hedges globais? (verbosity-reduction tipos 1, 3, 4, 5 e o bloco "VC in expository prose")
9. Cada hedge está ligado ao span específico que é incerto, em vez de marcar a resposta inteira? (resolução de conflito sober-prose × verbosity-reduction)
10. A primeira frase compromete-se com a resposta, em vez de repetir a pergunta ou de carregar contexto desnecessário? (verbosity-reduction "primary move")
11. (pt-BR) Os artigos definidos estão presentes antes de possessivos, partes do corpo, expressões temporais, substantivos abstratos e nomes próprios geográficos com artigo? (pt-br-fullness §1)
12. (pt-BR) Os conectivos discursivos estão explícitos e variados, em vez de "mas" e "então" repetidos? (pt-br-fullness §2)
13. (pt-BR) A regência verbal está correta, os clíticos preservados, o subjuntivo aplicado onde a norma o exige, as crases marcadas, o sujeito pronominal redundante elidido? (pt-br-fullness §§3–7)
14. (pt-BR) Há barras `/` em prosa expositiva unindo conceitos relacionados que pediriam conjunção explícita, fora dos casos legítimos (identificadores técnicos, nomes próprios, alternativa de grafia)? (pt-br-fullness §11)

Se qualquer item indicar drift, revise antes de enviar.

## Quando NÃO aplicar

- Mensagens muito curtas (uma ou duas frases), em que o custo da checklist combinada é maior do que o ganho. Use uma skill individual ou a intuição direta.
- Prosa criativa, poesia, ficção, copywriting — em que o efeito retórico é parte do produto. As três skills componentes desligam-se nesse contexto, e a `prosa-completa` herda essa restrição.
- Citações literais ou edição de texto cuja autoria seja do usuário. Preserve a fonte; não a corrija.
- Quando o usuário pediu explicitamente uma das três skills isoladamente. Respeite o escopo pedido — invocar a `prosa-completa` por cima seria expandir o pedido.
- Texto puramente técnico — especificação de API, schema, código, comandos de terminal — em que prosa expositiva não está envolvida.

## Relação com as três skills individuais

A `prosa-completa` não substitui as três skills individuais. Cada uma delas continua acionável sozinha quando o escopo for específico:

- Acione **sober-prose** isolada quando o texto estiver bom em densidade e fidelidade linguística mas carregar flourish retórico — fechamentos aforísticos, antíteses simétricas, adjetivos enfáticos.
- Acione **verbosity-reduction** isolada quando o problema for apenas padding — restatement, hedges globais, decoração formatística — e a retórica e a fidelidade linguística estiverem em ordem.
- Acione **pt-br-fullness** isolada quando o texto estiver em pt-BR e o único drift for anglicização estrutural — artigos omitidos, conectivos colapsados, regência calcada — sem problema retórico ou de densidade.

A `prosa-completa` é o caminho quando não se quer (ou não se consegue) pré-diagnosticar qual das três dimensões está em pior estado. Em iterações longas com o usuário sobre um mesmo documento, costuma ser a invocação mais eficiente.
