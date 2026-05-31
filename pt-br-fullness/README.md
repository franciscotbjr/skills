# pt-br-fullness

Uma skill que orienta a geração de texto em português do Brasil a preservar os elementos morfossintáticos e coesivos que o pt-BR usa com mais frequência do que o inglês e que a geração default tende a deixar cair: artigos definidos, conectivos discursivos, regência verbal, pronomes oblíquos, modo subjuntivo, crase e pro-drop (omissão do sujeito pronominal redundante).

## Uso

A skill é ativada automaticamente sempre que a resposta em curso for produzida em pt-BR, especialmente quando o "pensamento" subjacente está em inglês. Para invocar diretamente:

```
/pt-br-fullness
```

## Quando se aplica

- Geração de qualquer prosa expositiva, técnica, analítica ou ensaística em pt-BR.
- Tradução de inglês para pt-BR (a skill mira justamente o drift dessa passagem).
- Edição de texto pt-BR já produzido pelo modelo, para restaurar elementos que caíram na primeira passada.
- Acionável mesmo quando o usuário não pediu explicitamente — o viés é mais nocivo quando passa despercebido.

## Quando não se aplica

- Texto em inglês ou em outra língua que não pt-BR.
- Citações literais (preservar a fonte mesmo com drifts).
- Registros deliberadamente coloquiais, orais, informais ou regionais.
- Texto em português europeu (pt-PT) — a skill é específica para pt-BR.
- Mensagens muito curtas (uma ou duas frases), em que o viés raramente se manifesta.

## Ideia central

O modelo, treinado predominantemente em inglês, tende a gerar pt-BR que é gramatical mas estruturalmente anglicizado. Os sintomas — artigos definidos omitidos, conectivos colapsados em *mas* e *então*, regência verbal calcada, sujeitos pronominais redundantes — não comprometem a compreensão literal, mas tornam o texto reconhecidamente "traduzido". A skill atua como anteparo: lista as onze categorias mais frequentes de drift — incluindo artigos definidos, conectivos, regência, clíticos, subjuntivo, crase, pro-drop, estrangeirismos lexicais, calques semânticos, títulos sem sujeito e barra-como-ou — com pares bilíngues EN → pt-BR para cada uma e uma checklist pré-envio.

## Fontes

- Mendes, A. & Lejeune, P. **LDM-PT: A Portuguese Lexicon of Discourse Markers** (LREC 2018). [aclanthology.org/L18-1693.pdf](https://aclanthology.org/L18-1693.pdf) — lexicon com 252 pares marcador/sentido retórico em português.
- Morozova, M. A. **Discourse markers in English and European Portuguese translations: establishing functional equivalents and types of omission** (USP, Filologia e Linguística Portuguesa). [revistas.usp.br/flp/en/article/view/169242](https://revistas.usp.br/flp/en/article/view/169242) — estudo sobre omissão de discourse markers na tradução EN→PT.
- **Assessing Crosslingual Discourse Relations in Machine Translation** (arXiv:1810.03148). [arxiv.org/pdf/1810.03148](https://arxiv.org/pdf/1810.03148) — pesquisa sobre perda de relações discursivas em tradução automática.
- **Análise da Utilização dos Artigos Definidos no Português** — Dom Henrique. [domhenrique.com.br/analise-da-utilizacao-dos-artigos-definidos-no-portugues-uma-perspectiva-da-bbc-portuguese](https://domhenrique.com.br/analise-da-utilizacao-dos-artigos-definidos-no-portugues-uma-perspectiva-da-bbc-portuguese) — análise das diferenças sistêmicas no uso do artigo definido entre português e inglês.
- **Ciberdúvidas da Língua Portuguesa — O uso do artigo definido**. [ciberduvidas.iscte-iul.pt/consultorio/perguntas/o-uso-do-artigo-definido/5114](https://ciberduvidas.iscte-iul.pt/consultorio/perguntas/o-uso-do-artigo-definido/5114) — fonte normativa sobre uso do artigo.
- **Ensino de coesão textual e dos elementos conectivos** — Revista Linguística Rio (UFRJ), v. 6 n. 2 (2020). [linguisticario.letras.ufrj.br](https://www.linguisticario.letras.ufrj.br/uploads/7/0/5/2/7052840/revista_lingu%C3%ADstica_rio_-_v._6_n._2_-_ago._dez._2020-89-105.pdf) — sobre o papel dos conectivos na coesão textual em português.
- **Marcadores da Estruturação Textual** — Universidade de Trás-os-Montes e Alto Douro. [utad.pt/cel/.../CEL_Linguística_6.pdf](https://www.utad.pt/cel/wp-content/uploads/sites/7/2018/05/CEL_Lingu%C3%ADstica_6.pdf) — tipologia de marcadores discursivos em português.
