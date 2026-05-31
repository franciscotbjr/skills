---
name: pt-br-fullness
description: >-
  Use sempre que estiver gerando texto em português do Brasil, especialmente
  quando o texto está sendo produzido a partir de pensamento ou prompt em
  inglês. Preserva elementos linguísticos que o pt-BR usa com mais frequência
  do que o inglês e que a geração default tende a deixar cair: artigos
  definidos (antes de possessivos, partes do corpo, expressões temporais,
  nomes próprios geográficos, abstratos), conectivos discursivos (porém,
  contudo, ademais, ou seja, à medida que, portanto, dessa forma), regência
  verbal (gostar DE, depender DE, assistir A, obedecer A), pronomes oblíquos
  (o, a, lhe, se), modo subjuntivo onde o inglês usa indicativo, crase, e
  pro-drop (não inserir sujeito pronominal redundante), estrangeirismos lexicais
  (substituir palavras inglesas por equivalentes pt-BR correntes), calques
  semânticos (reescrever expressões traduzidas literalmente sem circulação no
  idioma), e títulos sem sujeito (explicitar o sujeito em títulos com verbo
  na 3ª pessoa). Acione mesmo quando o
  usuário não pediu explicitamente — o viés é mais nocivo quando passa
  despercebido. Não aplique a texto em inglês, a citações literais, a
  registros deliberadamente coloquiais nem a normas do português europeu.
---

# pt-BR Fullness

## O que esta skill mira

Quando o modelo gera prosa em pt-BR — em especial quando o "pensamento" subjacente está em inglês —, ele tende a produzir texto que é gramaticalmente português mas estruturalmente anglicizado. Os sintomas são previsíveis: artigos definidos omitidos onde a norma do português pede, conectivos discursivos esvaziados, regência verbal calcada do inglês, pronomes oblíquos substituídos por construções analíticas, achatamento do modo subjuntivo para o indicativo, crase ausente, e sujeitos pronominais explícitos onde o português prefere o sujeito nulo.

O resultado é um texto que o leitor reconhece imediatamente como "traduzido" — não pela escolha lexical, que pode estar correta, mas pelo tecido morfossintático que faltou. Esta skill é o anteparo contra esse drift.

## Por que o viés existe

Três causas combinadas:

- **Skew de dados de treino.** O modelo viu muito mais texto em inglês do que em pt-BR, e a distribuição probabilística default da geração reflete isso. Onde o inglês omite artigo, o modelo tende a omitir; onde o inglês não tem subjuntivo, o modelo tende a usar indicativo; onde o inglês concatena com vírgula, o modelo tende a concatenar com vírgula.

- **Drift por tradução interna.** Mesmo quando o usuário não pediu tradução, a geração de pt-BR pode passar internamente por uma representação anglicizada antes de produzir os tokens portugueses. A pesquisa sobre tradução automática EN→PT documenta a perda sistemática de discourse markers nessa passagem (ver LDM-PT, com 252 pares marcador/sentido catalogados, e o estudo sobre relações discursivas em tradução automática referenciado no README).

- **Diferenças sistêmicas reais.** O inglês e o pt-BR têm sistemas diferentes para artigos, conectivos, sujeito nulo, modo subjuntivo, regência e pronomes oblíquos. O modelo, quando não tem um sinal forte para preservar a diferença, nivela na direção do inglês. A skill fornece esse sinal.

## Anti-padrões — dez categorias

Cada exemplo tem três formas: **EN-fonte** (o que o inglês diria), **drift** (o pt-BR calcado do inglês, que a geração default produz) e **pleno** (a forma idiomática em pt-BR que a skill deve restaurar).

### 1. Artigos definidos omitidos

O português distingue gênero (o/a) e número (os/as) onde o inglês tem um único *the*, e usa o artigo em muitos contextos em que o inglês o dispensa. Cinco sub-casos típicos:

**1.1 Antes de possessivos** (em prosa expositiva e formal).
- EN: *my car broke down*
- drift: *meu carro quebrou*
- pleno: *o meu carro quebrou*
- Nota: o registro coloquial admite a queda do artigo; em prosa expositiva, mantenha.

**1.2 Antes de partes do corpo e itens da esfera pessoal.**
- EN: *wash your hands*
- drift: *lave suas mãos*
- pleno: *lave as mãos*
- Nota: o pt-BR usa o artigo definido com posse implícita — o possessivo aparece em inglês mas se dissolve em português.

**1.3 Antes de expressões temporais (dias da semana, horas).**
- EN: *I'll see you on Monday at 9*
- drift: *vejo você em segunda em 9 horas*
- pleno: *vejo você na segunda-feira às 9 horas*
- Nota: a contração preposição + artigo (*na*, *às*) é obrigatória e não opcional.

**1.4 Antes de nomes próprios geográficos.**
- EN: *Brazil is the largest country in South America*
- drift: *Brasil é o maior país da América do Sul*
- pleno: *o Brasil é o maior país da América do Sul*
- Nota: a regra tem exceções conhecidas — *em Portugal*, *para Israel*, *em Cuba* — mas o default para a maioria dos topônimos é o artigo presente.

**1.5 Antes de substantivos abstratos em sentido genérico.**
- EN: *freedom matters*
- drift: *liberdade importa*
- pleno: *a liberdade importa*
- Nota: o inglês marca o uso genérico pela ausência de artigo; o pt-BR marca pela presença.

### 2. Conectivos discursivos omitidos ou empobrecidos

O pt-BR tem um repertório rico de conectivos com nuances próprias. A geração default tende a colapsar tudo em *mas*, *então* e *também*, perdendo as distinções de força, registro e relação lógica. Cinco sub-casos:

**2.1 Contrastivos.** *Porém*, *contudo*, *todavia*, *no entanto*, *entretanto* — cada um com seu peso. *Porém* é neutro; *contudo* é mais formal; *no entanto* introduz contraste forte; *entretanto* tem o duplo sentido de "enquanto isso" e "porém"; *todavia* é literário.
- EN: *The plan looked solid, but it ignored the deadline.*
- drift: *O plano parecia sólido, mas ignorava o prazo.*
- pleno: *O plano parecia sólido; no entanto, ignorava o prazo.* (ou *contudo*, conforme o registro)

**2.2 Aditivos.** *Ademais*, *além disso*, *outrossim* (formal), *também*. Em pt-BR formal, *ademais* e *além disso* fazem o trabalho que o inglês faz com vírgula ou com *and*.
- EN: *The migration is risky. The window is small.*
- drift: *A migração é arriscada. A janela é pequena.*
- pleno: *A migração é arriscada. Ademais, a janela é pequena.*

**2.3 Explicativos e reformulativos.** *Ou seja*, *isto é*, *vale dizer*, *quer dizer*. Em pt-BR, esses marcadores tornam explícita a reformulação que o inglês deixa implícita com dois-pontos ou *i.e.*
- EN: *The pattern is monoidal: it composes associatively.*
- drift: *O padrão é monoidal: compõe associativamente.*
- pleno: *O padrão é monoidal — ou seja, compõe-se associativamente.*

**2.4 Sequenciais e temporais.** *Em seguida*, *posteriormente*, *à medida que*, *à proporção que*, *na medida em que*. O inglês usa *then*, *as*, *while*; a geração default condensa tudo em *depois* e *quando*, perdendo a textura temporal.
- EN: *As the team grew, the architecture broke.*
- drift: *Quando o time cresceu, a arquitetura quebrou.*
- pleno: *À medida que o time crescia, a arquitetura se quebrava.*

**2.5 Causais e consequentivos.** *Portanto*, *logo*, *por conseguinte*, *dessa forma*, *destarte* (formal). O inglês usa *so*, *therefore*, *thus*; a geração default colapsa em *então*.
- EN: *The tests fail under load, so we cannot ship.*
- drift: *Os testes falham sob carga, então não podemos enviar.*
- pleno: *Os testes falham sob carga; portanto, não podemos liberar.* (ou *dessa forma*)

### 3. Regência verbal calcada do inglês

Verbos portugueses pedem preposições específicas que o inglês não exige (ou exige diferentes). A geração default tende a omitir ou trocar a preposição.

- *gostar* **de** alguma coisa (não *gostar alguma coisa*)
- *depender* **de** (não *depender em*)
- *assistir* **a** algo (em registro formal: *assistir ao filme*, não *assistir o filme*)
- *obedecer* **a** alguém (não *obedecer alguém*)
- *implicar* algo (transitivo direto em pt-BR formal: *isso implica retrabalho*, não *isso implica em retrabalho*)
- *visar* **a** algo (em sentido figurado: *visa ao lucro*, não *visa o lucro*)
- *namorar* alguém (não *namorar com*)

Exemplo:
- EN: *I depend on this library.*
- drift: *Eu dependo nesta biblioteca.* / *Eu dependo desta biblioteca.* (sem ajuste de registro)
- pleno: *Dependo desta biblioteca.* (sujeito elidido por pro-drop; ver §7)

### 4. Pronomes oblíquos (clíticos) perdidos

O pt-BR tem um sistema de clíticos (*o*, *a*, *lhe*, *se*, *me*, *te*, *nos*, *vos*) que funciona como mecanismo coesivo. O pt-BR coloquial moderno admite "ele/ela" no lugar do clítico em algumas posições, mas a prosa expositiva ainda usa os clíticos.

- *Eu o vi ontem.* (acusativo) — drift coloquial: *Eu vi ele ontem.*
- *Pediram-me silêncio.* / *Pediram-lhe silêncio.* (dativo) — drift: *Pediram silêncio para mim* / *para ele*.
- Reflexivos: *lembrar-se de algo* — drift: *lembrar de algo* (a queda do *se* é tolerada coloquialmente, mas perde a marca reflexiva).

Em prosa expositiva, mantenha o clítico. A próclise (clítico antes do verbo) é a preferida em pt-BR, ao contrário do pt-PT, que prefere ênclise.

### 5. Modo subjuntivo achatado

O subjuntivo carrega informação semântica que se perde quando achatado para o indicativo. Três contextos típicos:

**5.1 Após verbos de desejo, dúvida, emoção:**
- EN: *I hope he comes.*
- drift: *Espero que ele vem.*
- pleno: *Espero que ele venha.*

**5.2 Em orações condicionais e temporais futuras (futuro do subjuntivo, sem equivalente em inglês):**
- EN: *When I arrive, I'll call.*
- drift: *Quando eu chego, eu ligo.*
- pleno: *Quando eu chegar, ligarei.* (ou *vou ligar*)

**5.3 Em concessivas:**
- EN: *Although he is tired, he keeps working.*
- drift: *Embora ele é cansado, continua trabalhando.*
- pleno: *Embora esteja cansado, continua a trabalhar.*

### 6. Crase omitida ou mal-aplicada

A crase — contração da preposição *a* com o artigo *a* (ou com pronomes demonstrativos *aquele*, *aquela*, *aquilo*) — é marcada pelo acento grave (à). Sua omissão é um dos drifts mais visíveis.

- Expressões temporais: *às 9 horas*, *à noite*, *à tarde*, *à medida que*.
- Objeto indireto feminino: *entreguei o livro à Maria*; *referiu-se à proposta*.
- Locuções: *à vista*, *à mão*, *à beira de*, *à custa de*.

Drifts comuns: escrever *a 9 horas*, *a noite*, *a Maria*, *a vista*. A regra prática: se a substituição por *ao* (masculino) cabe, há crase no feminino.

### 7. Pro-drop violado (sujeito explícito redundante)

O pt-BR é uma língua pro-drop: o sujeito pronominal pode (e geralmente deve) ser omitido quando a desinência verbal já o identifica. A geração default tende a inserir *eu*, *ele*, *nós* em todas as orações, calcando o inglês.

- EN: *I came early. I saw it was empty.*
- drift: *Eu cheguei cedo. Eu vi que estava vazio.*
- pleno: *Cheguei cedo. Vi que estava vazio.*

A regra não é absoluta: o sujeito explícito tem função quando desambigua (*ele saiu, mas ela ficou*), enfatiza (*eu mesmo fiz*) ou contrasta. Nos demais casos, o default é elidir.

### 8. Estrangeirismos lexicais

Palavras ou expressões do inglês mantidas no texto em pt-BR sem necessidade — há equivalente consolidado. O drift é mais visível em textos técnicos, onde o modelo trata o inglês como "a língua do domínio" e não traduz termos que têm forma portuguesa corrente.

Exemplos frequentes:
- EN: *claim* → drift: *claim* → pleno: *afirmação* (ou *asserção*, conforme o registro)
- EN: *confidence* → drift: *confidence* → pleno: *grau de confiança*
- EN: *gap* → drift: *gap* → pleno: *lacuna* (reforçar com *(gap)* entre parênteses na primeira ocorrência, se o termo é central ao domínio)
- EN: *brief* → drift: *brief* → pleno: *resumo*
- EN: *decay* → drift: *decay* → pleno: *decaimento*
- EN: *perform* (no sentido de *enact/disclose*) → drift: *performar* → pleno: *explicitar, tornar visível*
- EN: *tool* → drift: *tool* → pleno: *ferramenta* (em prosa; preservar em nomes de crates e identificadores técnicos)

Regra: se a palavra inglesa é o termo canônico do domínio e não tem equivalente em uso (ex.: *JSON-RPC*, *trait*, *crate*, *prompt*), preservar. Se há equivalente pt-BR em circulação corrente, substituir. Em caso de dúvida, a primeira ocorrência pode usar o parêntese de reforço: *lacuna (gap)*, *afirmação (claim)*.

### 9. Calques semânticos

Frases gramaticalmente corretas em pt-BR mas estruturadas como tradução literal de uma expressão inglesa — a sintaxe é portuguesa, a semântica da combinação é importada. O leitor entende as palavras mas não a expressão como unidade, porque ela não tem circulação independente no idioma.

Exemplos:
- EN: *knowledge work* → drift: *trabalho de conhecimento* → pleno: *trabalho de conhecimento* como categoria (reposicionar: *domínios de trabalho de conhecimento — código, escrita, pesquisa*) ou substituir por paráfrase
- EN: *executive zeal* → drift: *zelo executivo* → pleno: *ímpeto de agir* ou definir a expressão na primeira ocorrência
- EN: *scope drift* → drift: *deriva de escopo* → pleno: *perda de escopo* ou *expansão não controlada do escopo*

Regra: se a expressão não tem circulação independente em pt-BR (não aparece em dicionários, não é usada na imprensa ou na literatura técnica do idioma), reescreva com a estrutura idiomática equivalente. Se o conceito é novo e precisa de um termo, defina-o explicitamente na primeira ocorrência em vez de importar a expressão inglesa como se fosse transparente.

### 10. Títulos sem sujeito

Títulos de seção ou abertura de parágrafo com verbo conjugado na 3ª pessoa e sujeito omitido. Diferente do pro-drop (§7): aqui a desinência verbal não desambigua (*é criada* — criada o quê?), e o leitor precisa buscar o sujeito no parágrafo anterior ou no título da seção-pai.

Exemplos:
- drift: *Quando é criada.* → pleno: *Quando a predição é criada.*
- drift: *Como é calculado.* → pleno: *Como F é calculado.*

Regra: títulos e aberturas de parágrafo com verbo na 3ª pessoa devem explicitar o sujeito, exceto quando o sujeito é o tema único e inequívoco de toda a seção e o título está imediatamente sob o cabeçalho que o nomeia. Na dúvida, inclua o sujeito.

### 11. Barra-como-ou (`/`) em prosa expositiva

A barra `/` usada para juntar dois termos relacionados em prosa corrente (*crenças/definições*, *observações/dados*, *código/teste*, *espec/implementação*) é atalho tipográfico de origem anglicizada. Em prosa expositiva pt-BR, a forma idiomática é a conjunção explícita (*crenças e definições*, *observações e dados*), e, em registros formais, com restauração do artigo definido da lista (*as crenças e as definições*). O custo da barra é duplo: rompe o tecido prosódico do português e devora os artigos que §1 desta skill recomenda preservar.

- EN: *update beliefs/definitions based on observations/data*
- drift: *atualizar crenças/definições com base em observações/dados*
- pleno: *atualizar as crenças e as definições à luz das observações e dos dados*

**Quando preservar a barra**: identificadores técnicos (`Producer/Consumer`, `read/write`, `dev/prod`), nomes próprios (`TCP/IP`, `I/O`), tabelas, listas de keywords, conteúdo de configuração ou de código, glossários de equivalência inter-linguística (*EN: foo / pt-BR: bar*). **Quando substituir**: prosa expositiva corrente em pt-BR onde a barra une conceitos que o autor escreveria por extenso se estivesse lendo o trecho em voz alta.

**Teste sonoro**: ler em voz alta. Se a barra obriga uma pausa esquisita ("crenças barra definições") ou se o leitor a verbaliza como continuum forçado ("crenças ou definições" dito sem hesitação), é forte sinal de que a forma natural pediria conjunção explícita.

**Não confundir com**: a barra usada para indicar alternativa **legítima** num único termo composto (`he/she`, `s/he`, `e-mail/email`) — aí a barra é parte da grafia, não substituto da conjunção. Também não confundir com a barra inversa (`\`) ou com a barra em URLs, paths e datas — usos puramente técnicos.

## O que fazer em vez disso

Diretrizes positivas a seguir durante a geração em pt-BR:

- Antes de cada possessivo em prosa expositiva, verifique se o artigo definido cabe e o mantenha por default.
- Onde o inglês usaria virgula ou *and* / *but* / *so* para concatenar orações com relação lógica, prefira um conectivo discursivo explícito e varie entre as opções (*porém*, *contudo*, *no entanto* para contraste; *ademais*, *além disso* para adição; *portanto*, *dessa forma* para consequência).
- Antes de cada verbo, lembre-se da regência que o português pede e mantenha a preposição obrigatória mesmo quando o equivalente inglês a dispensa.
- Em prosa expositiva, prefira clíticos (*o*, *a*, *lhe*, *se*) a construções analíticas (*ele*, *ela*, *para ele*).
- Em orações que pedem subjuntivo pela norma, conjugue no subjuntivo, especialmente o futuro do subjuntivo após *quando*, *se* e *enquanto* com referência futura.
- Marque toda crase obrigatória.
- Suprima o sujeito pronominal redundante; mantenha-o apenas quando desambigua, enfatiza ou contrasta.
- Substitua palavras inglesas pelo equivalente pt-BR onde houver termo corrente no idioma (*gap* → *lacuna*, *confidence* → *grau de confiança*, *claim* → *afirmação*); preserve estrangeirismos apenas quando forem o termo canônico do domínio sem equivalente.
- Identifique calques semânticos — expressões gramaticalmente corretas mas sem circulação independente no idioma — e as reescreva com estrutura idiomática pt-BR ou as defina na primeira ocorrência.
- Em títulos e aberturas de parágrafo, explicite o sujeito de verbos na 3ª pessoa quando a desinência verbal não o desambigua.
- Em prosa expositiva, substitua a barra `/` que une dois termos relacionados (*crenças/definições*, *observações/dados*) pela conjunção explícita, restaurando o artigo definido da lista quando o registro pedir (*as crenças e as definições*). Preserve a barra em identificadores técnicos, nomes próprios e usos não-prosais.

## Auto-check antes de enviar

Antes de finalizar uma resposta em pt-BR, percorra a checklist:

1. Os possessivos em prosa expositiva estão precedidos pelo artigo definido onde a norma pede?
2. Os conectivos lógicos entre orações estão explícitos, com variação registral entre as opções disponíveis?
3. As preposições obrigadas pela regência verbal estão presentes (*depender de*, *gostar de*, *assistir a*, *obedecer a*)?
4. Os pronomes oblíquos aparecem onde a prosa expositiva os exige, em vez das construções analíticas equivalentes?
5. O subjuntivo está sendo usado nas orações que pedem o modo (desejo, dúvida, condicional futura, concessiva)?
6. As crases obrigatórias estão marcadas, especialmente nas expressões temporais e nos objetos indiretos femininos?
7. Há sujeitos pronominais (*eu*, *ele*, *nós*) inseridos por reflexo do inglês, que poderiam ser elididos sem perda de clareza?
8. Há palavras em inglês (*gap*, *claim*, *confidence*, *brief*, *decay*, *tool*) que poderiam ser substituídas pelo equivalente pt-BR corrente?
9. Há expressões que, embora gramaticalmente corretas, são traduções literais sem circulação independente no idioma (*trabalho de conhecimento*, *zelo executivo*)?
10. Títulos e aberturas de parágrafo com verbo na 3ª pessoa têm sujeito explícito quando a desinência não o desambigua?
11. Há barras `/` em prosa expositiva unindo conceitos relacionados (*crenças/definições*, *observações/dados*) que pediriam conjunção explícita em pt-BR, e o caso não é identificador técnico, nome próprio nem alternativa legítima de grafia?

Se qualquer item da checklist apontar drift, revise antes de enviar.

## Relação com sober-prose e verbosity-reduction

Em algum ponto pode parecer haver tensão: esta skill recomenda usar conectivos discursivos com variação, e a sober-prose alerta contra paralelismos ternários e enumerações decorativas. As duas instruções são compatíveis. Conectivos discursivos carregam relação lógica (são informacionais); paralelismos ternários carregam ritmo (são decorativos). Variar entre *porém*, *no entanto* e *contudo* ao longo de um texto é diferente de listar três adjetivos sinônimos em série para criar cadência. Em caso de conflito aparente, prefira a forma que carrega informação e descarte a que carrega só ritmo.

Em relação à verbosity-reduction: nenhum dos elementos que esta skill recomenda preservar (artigos, conectivos, clíticos, crase) é VC — todos carregam informação morfossintática ou lógica que o leitor pt-BR usa para processar o texto. A queda desses elementos não é compressão, é mutilação.

## Quando NÃO aplicar

- Texto em inglês ou em qualquer outra língua que não seja pt-BR.
- Citações literais, mesmo que a citação contenha drifts. Preserve a fonte.
- Registro deliberadamente coloquial, oral, informal ou regional, em que alguns dos itens (clíticos, artigo antes de possessivo, subjuntivo) podem cair sem problema. Use sensibilidade de registro.
- Texto técnico em que uma estrutura inglesa é o termo canônico — nomes de variáveis, APIs, comandos de terminal, bibliotecas. Não traduza esses.
- Citações ou texto em português europeu (pt-PT). As normas de regência, clíticos (ênclise vs. próclise), crase e algumas escolhas lexicais divergem. A skill é específica para pt-BR.
- Mensagens muito curtas (uma ou duas frases), em que o viés raramente se manifesta de forma visível.
