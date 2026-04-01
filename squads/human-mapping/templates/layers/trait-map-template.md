---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [trait-agent, synthesis-agent]
---
# Trait Map — Fillable Template

> Instrucoes: Preencha o perfil de tracos de personalidade usando resultados de Big Five, HEXACO e facetas detalhadas. Cada campo tem definicao, formato e exemplo. Siga `lib/utilities/confidence-scoring-rubric.md` para scores de confianca.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico da sessao | HMS-YYYY-MMDD-NNN | _______________ |
| Instrumentos utilizados | Frameworks aplicados nesta layer | Lista separada por virgula | _______________ |

---

## Big Five Profile

> Para cada dimensao, preencha TODOS os 4 campos. Nao use adjetivos isolados — descreva comportamentos observaveis.

### Openness to Experience (Abertura)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) comparado a populacao geral | Inteiro 0-100 + raw score entre parenteses | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score, por `lib/utilities/confidence-scoring-rubric.md` | Decimal 0.0-1.0 (1 casa). Fatores: nro frameworks, convergencia, qualidade dados | ___/1.0 |
| Descricao comportamental | 2-3 comportamentos OBSERVAVEIS que evidenciam este nivel do traco | Frases curtas descrevendo acoes, NAO adjetivos. Max 3 frases | _______________ |
| Implicacao no trabalho | Como este nivel de traco afeta o desempenho profissional | 1-2 frases especificas ao contexto de trabalho | _______________ |

### Conscientiousness (Conscienciosidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 comportamentos observaveis | Max 3 frases, verbos de acao | _______________ |
| Implicacao no trabalho | Impacto profissional | 1-2 frases contextuais | _______________ |

### Extraversion (Extroversao)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 comportamentos observaveis | Max 3 frases, verbos de acao | _______________ |
| Implicacao no trabalho | Impacto profissional | 1-2 frases contextuais | _______________ |

### Agreeableness (Amabilidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 comportamentos observaveis | Max 3 frases, verbos de acao | _______________ |
| Implicacao no trabalho | Impacto profissional | 1-2 frases contextuais | _______________ |

### Neuroticism (Neuroticismo)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 comportamentos observaveis | Max 3 frases, verbos de acao | _______________ |
| Implicacao no trabalho | Impacto profissional | 1-2 frases contextuais | _______________ |

---

## HEXACO Additions

**REGRA CONDICIONAL:** Incluir esta secao SOMENTE se instrumento HEXACO foi aplicado. Se apenas Big Five foi usado, marcar "N/A — HEXACO nao aplicado".

### Honesty-Humility (Honestidade-Humildade)

| Campo | Formato | Valor |
|---|---|---|
| Score | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Descricao comportamental | 2-3 comportamentos observaveis | _______________ |
| Implicacao no trabalho | 1-2 frases contextuais | _______________ |

### Emotionality vs Neuroticism — Diferencas Notaveis

**DEFINICAO:** Descrever divergencias entre Emotionality (HEXACO) e Neuroticism (Big Five), se houver. Formato: 1-2 frases explicando a diferenca e o que ela revela.

_______________

---

## Facet Detail

**REGRA DE INCLUSAO:** Incluir uma faceta na tabela SOMENTE se o score da faceta desvia >15 pontos percentis do score do fator principal. Facetas dentro da faixa de 15 pontos do fator sao omitidas por serem consistentes.

**FORMATO POR FACETA:**
| Coluna | Definicao |
|---|---|
| Dimensao | Fator Big Five pai |
| Faceta | Nome da sub-faceta |
| Score | Percentil 0-100 da faceta |
| Desvio | Diferenca em pontos vs fator (ex: +22, -18) |
| Interpretacao | 1 frase explicando o que o desvio significa comportamentalmente |

| Dimensao | Faceta | Score | Desvio | Interpretacao |
|---|---|---|---|---|
| | | | | |
| | | | | |
| | | | | |

> Adicione linhas conforme necessario. Se nenhuma faceta desvia >15 pontos, escrever: "Todas as facetas consistentes com scores dos fatores — nenhum desvio significativo."

---

## Resumo do Perfil de Tracos

| Campo | Definicao | Formato |
|---|---|---|
| Tracos mais salientes | Top 2-3 dimensoes que mais definem a pessoa | Lista com percentil e 1 frase cada |
| Tracos menos salientes | Dimensoes com scores medianos (40-60) que pouco diferenciam | Lista breve |
| Combinacoes notaveis | Interacoes entre tracos que criam padroes unicos | 1-2 frases por combinacao |
| Implicacoes gerais | Sintese para o contexto avaliado (hiring, coaching, etc.) | 2-3 frases max |

- **Tracos mais salientes:** _______________
- **Tracos menos salientes:** _______________
- **Combinacoes notaveis:** _______________
- **Implicacoes gerais para o contexto avaliado:** _______________

---

## EXEMPLO PREENCHIDO — Dimensao Conscientiousness

### Conscientiousness (Conscienciosidade) — EXEMPLO

| Campo | Valor |
|---|---|
| Score | 88/100 (Raw: 4.3/5.0) |
| Confidence | 0.85/1.0 |
| Descricao comportamental | Mantem listas de tarefas atualizadas diariamente e raramente perde prazos. Organiza documentos em sistemas de pastas hierarquicas antes de iniciar projetos. Revisa entregas multiplas vezes antes de submeter. |
| Implicacao no trabalho | Alta confiabilidade em projetos de longo prazo com multiplas dependencias. Pode desacelerar em ambientes que exigem prototipacao rapida e tolerancia a erro — perfeccionismo potencial em contextos ageis. |

**Facetas desviantes (>15 pontos do fator 88):**

| Dimensao | Faceta | Score | Desvio | Interpretacao |
|---|---|---|---|---|
| Conscientiousness | Deliberation | 95 | +7 | Dentro da faixa — consistente (incluido como exemplo proximo ao limiar) |
| Conscientiousness | Self-Discipline | 68 | -20 | Apesar de organizada, tende a procrastinar em tarefas que considera tediosas — inicia forte mas pode perder momentum em projetos repetitivos |
| Conscientiousness | Order | 92 | +4 | Consistente com fator — nao reportar |

> Nota: Neste exemplo, apenas Self-Discipline seria reportada na versao final (desvio -20 > limiar de 15). Order e Deliberation ficam dentro da faixa.

---

## Checklist de Qualidade

Antes de finalizar o trait map, verificar:
- [ ] Todos os 5 fatores Big Five preenchidos com score, confidence, descricao e implicacao
- [ ] Descricoes usam verbos de acao (nao adjetivos como "criativo" ou "organizado")
- [ ] Confidence scores seguem rubrica de `lib/utilities/confidence-scoring-rubric.md`
- [ ] Facetas desviantes (>15 pts) identificadas e interpretadas
- [ ] HEXACO incluido/excluido conforme disponibilidade de dados
- [ ] Resumo do perfil sintetiza padroes, nao repete scores
