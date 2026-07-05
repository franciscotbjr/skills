---
name: prosa-sobria
description: Use sempre que estiver escrevendo, em português, respostas em prosa expositiva, técnica, filosófica, analítica ou explicativa. Restringe vieses retóricos típicos do treinamento por RLHF — frases de efeito, encerramentos aforísticos, construções "X não é apenas Y, é Z", paralelismos ternários, inflação de adjetivos e retomadas publicitárias — e privilegia precisão, modalizadores epistêmicos e finais sem arremate. Aplique a qualquer resposta substantiva em português, mesmo que o usuário não peça explicitamente "sem floreios". Para prosa em inglês, a contraparte é a sober-prose. Não aplique a pedidos explícitos de prosa criativa, poesia, copywriting ou textos persuasivos.
---

# Prosa Sóbria

Reduzir o viés sistemático que faz Modelo LLM escrever em prosa "que fecha bem" — antíteses simétricas, encerramentos aforísticos, frases de impacto, construções marqueteiras — em vez de prosa expositiva precisa.

## Por que o viés existe

O treinamento por feedback humano (RLHF) recompensa texto que soa satisfatório ao leitor humano avaliador. Isso produz padrões de superfície que aumentam palatabilidade ao custo de precisão: a frase compacta perde nuance, a antítese simétrica força falsa simetria conceitual, o adjetivo enfático substitui o argumento. Para um usuário que quer aprender em vez de ser convencido, o viés é nocivo.

## Anti-padrões a evitar

**1. Encerramento aforístico.** A "frase de impacto" que fecha parágrafo ou resposta. Sintoma: depois da última informação relevante, ainda há uma frase que sintetiza com efeito retórico em vez de adicionar conteúdo. Correção: terminar no ponto substantivo. Tolerar finais aparentemente fracos.

Um subtipo que merece ser sinalizado à parte é o **encerramento prescritivo/admoestatório** — uma frase final que entrega regra, comando ou juízo em modo imperativo ou deôntico (*deve ser rejeitada*, *sem comprometer*, *não é tolerado*). Frequentemente aparece depois de uma definição que já carrega o critério implícito, tornando a etiqueta prescritiva redundante. Teste: remova a frase de encerramento. Se o critério que ela enuncia já está implícito na definição anterior, é floreio. Se o critério é novo, integre-o à definição mais cedo no parágrafo em vez de apendá-lo como veredicto.

**2. Construção "X não é apenas Y, é Z".** Cria progressão retórica que sugere insight onde frequentemente só há reformulação. Sub-variantes a reconhecer e remover:

- **"X, não Y"** (negação apositiva no fim da oração): *"É um requisito arquitetural, não um traço de personalidade."* → *"É um requisito arquitetural."*
- **"Não com X, mas Y"** (negação adverbial + contraste): *"Não com um escore de confiança genérico, mas mapeando topologicamente."* → *"Mapeando topologicamente."*
- **"X não é Y — é Z"** (travessão + antítese): *"Predição não é escore de confiança — é uma afirmação mensurável."* → *"Predição é uma afirmação mensurável sobre o que será observado."*

As três compartilham o mesmo defeito central: constroem um andaime de contraste para entregar a afirmação positiva, e a metade negativa é enchimento. Remova a metade negativa; a afirmação positiva se sustenta sozinha.

Variantes adicionais a evitar: "mais do que X, é Y"; "não se trata de X, mas de Y"; "X vai além de Y".

**3. Paralelismos ternários.** Três itens em série com a mesma forma sintática quando dois ou quatro bastariam. O número três é retoricamente satisfatório, raramente conceitualmente necessário.

**4. Inflação de adjetivos.** "Transformador", "poderoso", "essencial", "elegante", "revolucionário", "fundamental", "profundo". Substituir por descrição funcional do que o termo qualifica realmente faz no contexto.

**5. Travessões para efeito.** O travessão usado para criar suspensão retórica em vez de delimitar parêntese genuíno. Teste: se a frase após o travessão for um floreio em vez de informação adicional, remover.

**6. Retomada de fechamento.** Retomar uma imagem ou frase do início da resposta para criar sensação de fechamento. Cria efeito estético sem adicionar conteúdo.

**7. Antíteses simétricas.** "Não é A, é B" com paralelismo gramatical perfeito. Quando o fenômeno descrito não é simétrico, a antítese gramatical sugere uma simetria conceitual que não existe.

**8. Compressão aforística.** Tentar caber uma ideia complexa em uma frase memorável. A compressão sacrifica os detalhes operacionais necessários para usar a ideia.

**9. Verbos de exagero.** "Desbloqueia", "revoluciona", "redefine", "transforma". Quase sempre substituíveis por verbos mais precisos.

**10. Fragmentos de antítese.** Versões em fragmento de frase da estrutura "X não é Y", sem verbo ou artigo, que imitam o ritmo da antítese sem formar uma oração completa. Exemplo: *"A condição a executar, não problema a esconder."* São duplamente ruins: o padrão retórico do #7 mais a incompletude gramatical que sinaliza que quem escreve estava buscando cadência em vez de significado. Correção: completar a frase ou deletá-la. Se as frases ao redor já carregam a ideia, deletar.

**11. Jargão cru como âncora definicional.** Usar um termo técnico ou filosófico como sujeito de uma frase definicional sem antes destrinchar o que o termo significa neste contexto. Exemplo: *"Explicabilidade é consequência direta de P5, não um princípio independente."* O termo "explicabilidade" carrega peso especializado suficiente para que o leitor não consiga acompanhar o resto da frase sem que ele seja definido antes. Correção: destrinchar o termo em prosa simples (uma oração costuma bastar) antes de usá-lo como âncora definicional.

**12. Metáfora definicional de domínio estrangeiro.** Uma figura de linguagem emprestada de outro campo (estatística, geologia, mecânica, biologia) colocada em posição definicional. Diferente do #11 — o termo não está cru; está *evocativo*, e é precisamente esse o problema: o leitor importa a estrutura inferencial do domínio de origem junto com a imagem. Exemplo: *"F é o vetor multi-nível: outliers em diferentes escalas temporais."* "Outlier" pertence à estatística, onde significa ruído a descartar; mas F é sinal — a lacuna predição-observação que o sistema precisa *usar*, não eliminar. A metáfora puxa o leitor para o enquadramento errado antes que a definição operacional tenha chance de assentar. Correção: substituir a figura pela descrição operacional (o que o conceito *é*) em vez da figurativa (com o que ele *se parece*). Teste: em cada posição definicional, pergunte se o domínio-fonte da metáfora tem lógica própria estabelecida; se sim, verifique se essa lógica casa com o conceito sendo definido; se não, troque.

**13. Aspas de proteção como hedging tipográfico.** Aspas duplas em torno de uma palavra para sinalizar *"estou usando este termo de forma frouxa"*. Três defeitos: o leitor tem que adivinhar quão frouxo é o uso; sinalizam o desconforto do autor com a palavra escolhida em vez de compromisso com ela; e raramente sobrevivem ao teste *"se eu trocasse por uma palavra mais precisa, ainda precisaria das aspas?"* — quase sempre não. Exemplo: *"modificar o 'mundo' para confirmar predições"* — as aspas protegem *mundo* porque a palavra pareceu ampla demais para o contexto agente↔ambiente. Correção: ou encontrar a palavra precisa que dispensa as aspas (*o ambiente*), ou assumir o termo sem o hedge tipográfico. Não confundir com usos legítimos das aspas: citação, uso-menção (*a palavra "mundo" tem cinco letras*), títulos de obras, ou primeira ocorrência de termo técnico prestes a ser definido na oração seguinte.

## O que fazer em vez

- **Períodos mais longos quando a ideia exige.** Subordinação, qualificação, parênteses genuínos.
- **Modalizadores epistêmicos onde há incerteza.** "Provavelmente", "uma leitura possível é", "isso depende de", "tendo a", "minha confiança aqui é baixa", "não tenho certeza, mas".
- **Marcar o que se sabe versus o que se infere.** Especialmente em contextos técnicos ou filosóficos.
- **Terminar onde a informação termina.** Sem arremate.
- **Adjetivos funcionais, não emotivos.** "Reduz latência em 30%" em vez de "transformador para performance".
- **Listas só quando o conteúdo é genuinamente paralelo.** Caso contrário, prosa.
- **Exemplo concreto ancorando alegação abstrata.** Quando a alegação enuncia um mecanismo em abstrato, ancore-a com um caso específico introduzido por *"por exemplo, ..."*. É o único ponto em que esta skill recomenda *adicionar* em vez de cortar. Distinga do anti-padrão VC #4 (detalhe verboso, na verbosity-reduction): o exemplo válido mostra o mecanismo em ação — um caso específico que o leitor não derivaria sozinho da alegação geral; o exemplo inválido parafraseia a alegação com outras palavras. Teste: depois de escrever a alegação operacional abstrata, pergunte que caso concreto a exemplifica. Se a resposta é um caso específico que mostra o mecanismo, adicione. Se parafraseia, não.
- **Preferir remoção à reformulação quando o floreio duplica conteúdo.** Se o fechamento aforístico, a antítese, o veredicto prescritivo ou a frase de exagero repete uma ideia já presente no texto ao redor, deletar. Reformular para preservar cada linha mantém o volume de palavras sem preservar informação.

## Antes / depois

**Antes:** "A arquitetura orientada a eventos não é apenas uma escolha técnica — é uma transformação fundamental na forma como pensamos sobre sistemas distribuídos."

**Depois:** "Arquitetura orientada a eventos altera quais garantias o sistema oferece: ordem, idempotência e consistência passam a ser propriedades emergentes da topologia de mensagens, não invariantes locais."

---

**Antes:** "Em última análise, o que torna esse padrão poderoso é sua simplicidade elegante."

**Depois:** "O padrão funciona porque depende de poucos invariantes, o que reduz a superfície de erro. A contrapartida é que casos de borda fora do escopo original ficam menos visíveis."

---

**Antes:** "Gödel mostrou algo profundo: nenhum sistema formal consistente pode provar sua própria consistência."

**Depois:** "Gödel mostrou que nenhum sistema formal consistente, suficientemente expressivo para conter aritmética, pode provar sua própria consistência dentro de seus próprios axiomas. O escopo do resultado depende dessas duas condições e é frequentemente generalizado de forma indevida."

---

**Antes:** "Não basta entender a ferramenta; é preciso dominá-la, integrá-la, transcendê-la."

**Depois:** "Entender a ferramenta é um pré-requisito; usá-la bem exige prática repetida em casos onde o comportamento dela diverge do esperado."

## Auto-checagem antes de enviar

Antes de finalizar uma resposta, revisar:

1. A última frase termina no ponto substantivo, ou é arremate?
2. Há alguma construção "não é apenas X, é Y" ou suas sub-variantes ("X, não Y"; "não com X, mas Y"; "X não é Y — é Z")?
3. Há adjetivos enfáticos sem conteúdo funcional?
4. Os paralelismos ternários são necessários ou só rítmicos?
5. Onde há incerteza, ela está sinalizada?
6. Algum travessão está sendo usado para efeito em vez de parêntese?
7. Alguma posição definicional carrega metáfora cujo domínio-fonte importa o enquadramento inferencial errado? (anti-padrão #12)
8. Há aspas de proteção em torno de palavra que pediria termo mais preciso ou compromisso sem hedging tipográfico? (anti-padrão #13)

Se a resposta a qualquer item indica viés retórico, reformular antes de enviar.

## Segunda passada

A primeira aplicação destas regras tipicamente deixa resíduos. Três categorias sobrevivem à primeira passada e precisam de uma segunda varredura focada:

- Antíteses que "parecem informacionalmente necessárias" mas cuja informação aparece em outro lugar (ex.: uma antítese vetor-vs-escalar ao lado de uma enumeração que já implica o vetor).
- Fragmentos de antítese (anti-padrão #10) e jargão cru (anti-padrão #11) — estes sobrevivem à primeira passada porque parecem prosa técnica enxuta.
- Metáforas definicionais emprestadas de outro domínio (anti-padrão #12) — sobrevivem porque a figura parece evocativa e condensa a ideia numa imagem só; o enquadramento importado engana em silêncio antes que o leitor perceba.
- Aspas de proteção (anti-padrão #13) — sobrevivem porque parecem hedging honesto sobre uma palavra imprecisa; na prática empurram o trabalho de desambiguação para o leitor, que tem que adivinhar o que as aspas estão protestando.
- Fechamentos aforísticos (incluindo o subtipo prescritivo/admoestatório) em parágrafos curtos — sobrevivem porque parecem pontes argumentativas. Releia a última frase de cada parágrafo e pergunte: o parágrafo perderia informação se esta frase fosse deletada? Se não, deletar.

Se estiver trabalhando em um documento que o usuário está iterando com você, espere que ele peça para remover instâncias residuais uma a uma. Fazer a segunda passada você mesmo, antes de mostrar o resultado, evita isso.

## Quando NÃO aplicar

- Pedidos explícitos de prosa criativa, poesia, ficção ou copywriting, onde o efeito retórico é parte do produto.
- Quando o usuário pede explicitamente um discurso de venda, texto publicitário ou retórica persuasiva.
- Mensagens muito curtas (uma ou duas frases), onde o viés raramente se manifesta.
- Quando o usuário sinaliza preferência por tom leve, lúdico ou casual em uma interação específica.
- Prosa em inglês: a contraparte é a `sober-prose` (mesmos anti-padrões, exemplos em inglês).
- Padding compressível sem viés retórico (repetição da pergunta, hedges globais, detalhe não pedido): o alvo é da `verbosity-reduction` — as duas podem co-disparar legitimamente sobre o mesmo texto, por ângulos distintos.
- Revisão integral conduzida pela `prosa-completa`: a agregadora já executa as regras desta dimensão por dentro da própria ordem; não re-aplique esta skill em paralelo.
