# Methodological Rigor

Skill para auditoria crítica de argumentação, metodologia e robustez epistêmica.

## O que faz

Aplica uma persona **implacavelmente crítica** que questiona:
- Premissas não declaradas
- Vieses estruturais incorporados
- Claims não verificados
- Gaps lógicos e circular reasoning
- Hipocrisia epistêmica (você viola seu próprio padrão?)
- Hipocrisia normativa (você recomenda X mas não faz X?)

O objetivo não é destruir uma análise, mas **expor sua fragilidade para fortalecer argumentação**.

## Quando usar

**Antes de publicar** análise técnica, decisão de produto ou recomendação que será usada como base para ação

**Quando você confia muito em sua conclusão** — risco de blind spots. Crítica deve ser severa quanto mais confiante você está

**Em comparações/rankings** que usam matrizes, tabelas ou critérios quantificados — detecta viés de estruturação

**Em propostas baseadas em especulação** ("isso seria diferencial") sem validação com stakeholders

**Quando você criticou outro documento por falta de rigor** — então aplique o mesmo padrão a si mesmo

## Como usar

```
/methodological-rigor
[documento a criticar ou resumo dele]
```

Forneça:
- O documento completo, OU
- Link para ele, OU  
- Resumo de 3-5 sentenças do argumento central

## Resultado esperado

A skill retorna:

1. **Achado mais duro** — a crítica que mais enfraquece a análise
2. **Acharcos específicos** (2-8 acharcos) — cada um com localização, razão e severidade
3. **Hipocrisias detectadas** (se houver) — epistêmica e/ou normativa
4. **Priorização** — "o que corrigir primeiro" ordenado por severidade
5. **Veredito final** — robustez da análise (frágil / tem limitações / sólida)

## Exemplo rápido

**Entrada:**
```
Meu documento propõe Feature X como diferencial competitivo. 
Análise de mercado sugere nenhum concorrente oferece isso.
Mas não validei com clientes antes de propor.
```

**Saída esperada:**
- ❌ Achado: "Diferencial competitivo" não foi verificado contra concorrentes reais
- ❌ Achado: Validação com clientes recomendada mas não feita (hipocrisia normativa)
- ⚠️ Severidade: ALTO — decisão de produto poderia basear-se nessa especulação
- ✅ Correção: Consulte concorrentes antes de afirmar "ninguém oferece isto"

## Persona: O Crítico Implacável

O Crítico:
- **Sem compaixão pela confiança em si mesmo** — quanto mais seguro você parece, mais duro o questionamento
- **Específico** — não critica "falta de rigor em geral", aponta exatamente onde quebra
- **Auto-aplicado** — se você violou seu próprio padrão, isso é uma acusação
- **Atento a distinções** — entre "claim não verificado" (erro) vs "falta de date stamp" (formalismo)
- **Intolerante a hipocrisia** — recomenda X mas não faz X? O Crítico pega.
- **Destruidor de viés de matriz** — presença (✅) ≠ adequação ao propósito

## Estrutura da análise

A skill executa em **7 fases sistemáticas**:

1. **Premissas** — quais são explícitas, quais silenciosas?
2. **Verificabilidade** — cada claim factual pode ser auditado?
3. **Vieses estruturais** — a metodologia favorece alguém/algo?
4. **Circular reasoning** — há auto-referência não sinalizada?
5. **Especulação vs fato** — o que é observado, o que é extrapolado?
6. **Lacunas** — o que foi mencionado mas não endereçado?
7. **Auto-crítica** — você está aplicando seu próprio padrão a si mesmo?

## Critérios de completude

A análise termina quando:
- Encontrou **≥2 acharcos substantivos** (não formalismo)
- Testou cada achado contra "isto invalida a conclusão?"
- Identificou **hipocrisias** (se houver)
- Verificou se está sendo **justo ou injustamente implacável**
- Priorizou **3-5 itens de correção** (crítico → alto → médio → baixo)

**Limites:**
- Mínimo: 2 acharcos (menos disso é pré-crítica)
- Máximo: 8 acharcos (acima disso é análise paralela infinita)

## Anti-patterns detectados

A skill flagra 8 anti-patterns comuns:

1. **Menção ≠ Resolução** — documento menciona problema, leitor assume que foi resolvido
2. **Formalismo por formalismo** — criticar "falta de X" quando X está correto
3. **Matriz sem pesos** — presença marcada com ✅ sem considerar adequação
4. **Validação depois** — recomenda X como pré-requisito, mas fez Y sem X
5. **Alegação não verificada** — afirma sobre mercado/concorrentes sem verificação registrada
6. **Cutoff anterior às fontes** — análise de LLM usando fontes posteriores ao training, sem sinalizar
7. **Não implementado vs não documentado** — confunde "feature não tem" com "docs não mencionam"
8. **Sinalização escondida** — disclaimer no meio da seção, após leitor já incorporou a afirmação

## Documentação completa

Veja [Skill](Skill) para:
- Descrição detalhada de cada fase
- Checklist de auditoria
- Resolução de conflitos
- Exemplo completo de aplicação
- Notas de calibração

## Notas

- **Universalizável** — funciona para análise técnica, produto, estratégia, pesquisa
- **Sem viés de caso de uso** — exemplos genéricos, um exemplo histórico para pedagogia
- **Validada** — testada contra documentos reais, acharcos genuínos encontrados

## Contribuições

Esta skill foi desenvolvida através de:
1. Análise crítica de caso real ("LLM Wiki — Análise")
2. Identificação de padrões de erro epistêmico
3. Teste prático contra documento específico
4. Iteração com feedback de aplicação

O padrão está consolidado e pronto para uso em contextos diversos.
