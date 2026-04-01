---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [trait-agent, synthesis-agent]
related_files:
  - frameworks/confidence-scoring-model.md
  - frameworks/cross-framework-reconciliation.md
  - templates/audit/confidence-map-template.md
  - templates/audit/contradiction-map-template.md
  - templates/reports/executive-snapshot-template.md
---
# Trait Map — Fillable Template

> Instrucoes: Preencha o perfil de tracos de personalidade do respondente utilizando os resultados dos instrumentos Big Five, HEXACO e facetas detalhadas quando disponiveis. Cada campo tem definicao, formato e orientacao de preenchimento.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico da sessao | HMS-YYYY-MMDD-NNN | _______________ |
| Instrumentos utilizados | Lista de todos os instrumentos de trait aplicados | Lista separada por virgula (ex: "NEO-PI-R, IPIP-300, BFI-2") | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |

---

## Big Five Profile

> Para cada dimensao: preencha Score, Confidence, Descricao Comportamental, Implicacao no Trabalho, e Fonte. Se o instrumento nao foi aplicado, escrever "N/A — instrumento nao disponivel" e Confidence = 0.0.

### Openness to Experience (Abertura)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) comparado a populacao geral | Inteiro 0-100 + raw score entre parenteses | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score, conforme `frameworks/confidence-scoring-model.md` | Decimal 0.0-1.0 (1 casa). >=0.7 Alta, 0.5-0.7 Moderada, <0.5 Baixa | ___/1.0 |
| Descricao comportamental | 2-3 frases descrevendo COMPORTAMENTOS OBSERVAVEIS associados a este score. NAO incluir interpretacoes internas ou suposicoes. Focar em: o que a pessoa FAZ, nao o que SENTE. | Max 50 words. Cada frase = 1 comportamento observavel. | _______________ |
| Implicacao no trabalho | 1-2 frases sobre como este traco se manifesta no ambiente profissional | Max 30 words. Foco em: decisoes, comunicacao, colaboracao. | _______________ |
| Fonte | Instrumento que gerou este score | Nome do instrumento + tipo (oficial/proxy/inferido) | _______________ |

### Conscientiousness (Conscienciosidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis | Max 50 words | _______________ |
| Implicacao no trabalho | 1-2 frases de impacto profissional | Max 30 words | _______________ |
| Fonte | Instrumento de origem | Nome + tipo | _______________ |

### Extraversion (Extroversao)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis | Max 50 words | _______________ |
| Implicacao no trabalho | 1-2 frases de impacto profissional | Max 30 words | _______________ |
| Fonte | Instrumento de origem | Nome + tipo | _______________ |

### Agreeableness (Amabilidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis | Max 50 words | _______________ |
| Implicacao no trabalho | 1-2 frases de impacto profissional | Max 30 words | _______________ |
| Fonte | Instrumento de origem | Nome + tipo | _______________ |

### Neuroticism (Neuroticismo)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca neste score | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis | Max 50 words | _______________ |
| Implicacao no trabalho | 1-2 frases de impacto profissional | Max 30 words | _______________ |
| Fonte | Instrumento de origem | Nome + tipo | _______________ |

---

## HEXACO Additions

**REGRA DE DECISAO:** Preencher esta secao SOMENTE se dados de Honesty-Humility estiverem disponiveis via instrumento HEXACO (HEXACO-PI-R, HEXACO-60, ou equivalente). Se nao disponivel, escrever: "Secao nao preenchida — instrumento HEXACO nao aplicado neste assessment."

### Honesty-Humility (Honestidade-Humildade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | ___/100 (Raw: ___) |
| Confidence | Grau de confianca | Decimal 0.0-1.0 | ___/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis. Focar em: sinceridade, fairness, aversao a manipulacao, modestia. | Max 50 words | _______________ |
| Implicacao no trabalho | 1-2 frases. Focar em: etica profissional, negociacao, lideranca. | Max 30 words | _______________ |
| Fonte | Instrumento HEXACO utilizado | Nome + versao | _______________ |

### Emotionality vs Neuroticism — Diferencas notaveis

> Preencher apenas se AMBOS Big Five Neuroticism e HEXACO Emotionality estao disponiveis. Descrever em 2-3 frases as diferencas relevantes entre os dois construtos para este respondente. Max 50 words.

_______________

---

## Facet Detail

**REGRA DE PREENCHIMENTO:** Preencher a tabela completa apenas se dados de faceta estiverem disponiveis. No campo "Destaque", marcar SOMENTE as 3 facetas mais extremas por dimensao (top 3 mais altas OU mais baixas). Usar "HIGH" para percentil >= 75, "LOW" para percentil <= 25, deixar em branco se entre 26-74.

| Dimensao | Faceta | Score (0-100) | Destaque (HIGH/LOW/em branco) |
|---|---|---|---|
| Openness | Fantasy | ___ | ___ |
| Openness | Aesthetics | ___ | ___ |
| Openness | Feelings | ___ | ___ |
| Openness | Actions | ___ | ___ |
| Openness | Ideas | ___ | ___ |
| Openness | Values | ___ | ___ |
| Conscientiousness | Competence | ___ | ___ |
| Conscientiousness | Order | ___ | ___ |
| Conscientiousness | Dutifulness | ___ | ___ |
| Conscientiousness | Achievement Striving | ___ | ___ |
| Conscientiousness | Self-Discipline | ___ | ___ |
| Conscientiousness | Deliberation | ___ | ___ |
| Extraversion | Warmth | ___ | ___ |
| Extraversion | Gregariousness | ___ | ___ |
| Extraversion | Assertiveness | ___ | ___ |
| Extraversion | Activity | ___ | ___ |
| Extraversion | Excitement-Seeking | ___ | ___ |
| Extraversion | Positive Emotions | ___ | ___ |
| Agreeableness | Trust | ___ | ___ |
| Agreeableness | Straightforwardness | ___ | ___ |
| Agreeableness | Altruism | ___ | ___ |
| Agreeableness | Compliance | ___ | ___ |
| Agreeableness | Modesty | ___ | ___ |
| Agreeableness | Tender-Mindedness | ___ | ___ |
| Neuroticism | Anxiety | ___ | ___ |
| Neuroticism | Angry Hostility | ___ | ___ |
| Neuroticism | Depression | ___ | ___ |
| Neuroticism | Self-Consciousness | ___ | ___ |
| Neuroticism | Impulsiveness | ___ | ___ |
| Neuroticism | Vulnerability | ___ | ___ |

---

## Resumo do Perfil de Tracos

| Campo | Definicao | Formato |
|---|---|---|
| Tracos mais salientes | Top 2-3 dimensoes com scores mais extremos (>=75 ou <=25 percentil) | Lista de dimensoes com percentil. Max 3 items. |
| Tracos menos salientes | Dimensoes proximas da media (40-60 percentil) | Lista de dimensoes. Max 2 items. |
| Combinacoes notaveis | Pares de tracos que interagem de forma relevante (ex: High C + Low N = resiliencia meticulosa) | 1-2 combinacoes com implicacao. Max 30 words cada. |
| Implicacoes gerais | Sintese para o contexto avaliado (pessoal/profissional/lideranca) | 2-3 frases. Max 60 words total. |

- **Tracos mais salientes:** _______________
- **Tracos menos salientes:** _______________
- **Combinacoes notaveis:** _______________
- **Implicacoes gerais para o contexto avaliado:** _______________

---

## QUALITY CRITERIA

Um trait map preenchido corretamente atende a TODOS os seguintes criterios:

1. **Completude:** Todas as 5 dimensoes Big Five preenchidas com Score, Confidence, Descricao, Implicacao e Fonte
2. **Observabilidade:** Descricoes comportamentais referem-se apenas a comportamentos observaveis, NUNCA a estados internos
3. **Rastreabilidade:** Cada score cita instrumento de origem; confidence segue rubrica do confidence-scoring-model
4. **Consistencia:** Scores de facetas sao coerentes com dimensao principal (facetas extremas explicadas se divergem)
5. **HEXACO condicional:** Secao HEXACO preenchida somente com dados reais, nunca inferidos
6. **Facet economy:** Destaques marcados apenas para facetas extremas (top 3 por dimensao)

---

## EXEMPLO PREENCHIDO — Conscientiousness

### Conscientiousness (Conscienciosidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Percentil normativo (0-100) | Inteiro 0-100 + raw score | 88/100 (Raw: 4.2/5.0) |
| Confidence | Grau de confianca neste score | Decimal 0.0-1.0 | 0.85/1.0 |
| Descricao comportamental | 2-3 frases de comportamentos observaveis | Max 50 words | Entrega tarefas antes do prazo em 90%+ dos casos. Mantem listas de tarefas detalhadas e atualiza status diariamente. Revisa trabalho proprio antes de submeter, raramente necessita correcoes. |
| Implicacao no trabalho | 1-2 frases de impacto profissional | Max 30 words | Altamente confiavel para projetos com multiplas dependencias. Pode ser percebida como inflexivel quando processos nao sao seguidos por colegas. |
| Fonte | Instrumento de origem | Nome + tipo | NEO-PI-R (oficial, administrado por psicologo) |

**Facetas destaque para esta dimensao:**

| Dimensao | Faceta | Score (0-100) | Destaque |
|---|---|---|---|
| Conscientiousness | Competence | 82 | HIGH |
| Conscientiousness | Order | 91 | HIGH |
| Conscientiousness | Dutifulness | 85 | HIGH |
| Conscientiousness | Achievement Striving | 78 | HIGH |
| Conscientiousness | Self-Discipline | 90 | HIGH |
| Conscientiousness | Deliberation | 88 | HIGH |
