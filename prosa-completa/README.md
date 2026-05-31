# prosa-completa

Skill agregadora que orquestra em uma única passada as três skills de qualidade de prosa do vault: [sober-prose](../sober-prose/), [verbosity-reduction](../verbosity-reduction/) e [pt-br-fullness](../pt-br-fullness/). Define a ordem de aplicação, o gating de língua (a pt-br-fullness é aplicada apenas se o texto-alvo for pt-BR) e a resolução das poucas tensões aparentes entre as três. Não substitui as skills individuais — é um atalho de invocação combinada.

## Uso

Acionável manualmente quando se quer cobertura combinada das três dimensões em uma única chamada:

```
/prosa-completa
```

As três skills componentes continuam invocáveis isoladamente (`/sober-prose`, `/verbosity-reduction`, `/pt-br-fullness`) quando o escopo for específico.

## Quando se aplica

- Revisão de prosa expositiva longa (mais de três ou quatro parágrafos).
- Pedido genérico do usuário por "revisão completa" sem indicação de qual dimensão está em jogo.
- Iteração com o usuário sobre documento que receberá várias rodadas — aplicar a `prosa-completa` na primeira passada reduz a quantidade de iterações posteriores em que o usuário aponta resíduos um a um.
- Texto gerado a partir de pensamento ou prompt em inglês e entregue em pt-BR (combinação típica em que os três tipos de drift aparecem juntos).

## Quando não se aplica

- Mensagens muito curtas (uma ou duas frases) — overhead maior do que ganho.
- Prosa criativa, poesia, ficção, copywriting — o efeito retórico é parte do produto.
- Citações literais ou edição de texto de autoria do usuário.
- Quando o usuário pediu explicitamente uma das três skills isoladamente — respeite o escopo.
- Texto puramente técnico (especificação, schema, código) sem prosa expositiva.

## Ideia central

As três skills cobrem dimensões diferentes da qualidade de prosa: retórica (sober-prose), densidade informacional (verbosity-reduction) e fidelidade linguística pt-BR (pt-br-fullness). Em qualquer revisão substantiva de prosa expositiva longa, as três têm trabalho a fazer simultaneamente. A `prosa-completa` define a ordem canônica de aplicação — verbosity-reduction primeiro (reduz a área de trabalho das outras), sober-prose segundo, pt-br-fullness terceiro (apenas se pt-BR) — e oferece uma seção dedicada à resolução dos quatro pares de tensão aparente entre as três (conectivos variados × paralelismos ternários; hedges locais × hedges globais como VC; artigos antes de possessivo × concisão; fragmentos sem verbo × prosa expositiva). A checklist combinada condensa os pontos das três em dez perguntas pré-envio.

## Skills componentes

- [sober-prose](../sober-prose/) — viéses retóricos do treinamento RLHF.
- [verbosity-reduction](../verbosity-reduction/) — Verbosity Compensation (padding compressível).
- [pt-br-fullness](../pt-br-fullness/) — fidelidade linguística pt-BR (artigos, conectivos, regência, clíticos, subjuntivo, crase, pro-drop).
