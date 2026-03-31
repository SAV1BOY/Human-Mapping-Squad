---
type: taxonomy
squad: human-mapping
version: "2.0.0"
---

# Trait Taxonomy

## Proposito

Organizar todos os personality traits utilizados pelo Human Mapping Squad em uma hierarquia
consistente, permitindo mapeamento preciso entre frameworks e identificacao de indicadores
comportamentais observaveis. Esta taxonomia serve como referencia canonical para qualquer
analise baseada em traits.

## Categorias

### 1. Big Five (OCEAN) Framework

#### 1.1 Openness to Experience
- **Facetas**: Fantasy, Aesthetics, Feelings, Actions, Ideas, Values
- **Indicadores comportamentais**: Curiosidade intelectual, preferencia por novidade, tolerancia a ambiguidade, criatividade expressa, interesse por arte e cultura
- **Polo oposto**: Closedness / Conventionality

#### 1.2 Conscientiousness
- **Facetas**: Competence, Order, Dutifulness, Achievement Striving, Self-Discipline, Deliberation
- **Indicadores comportamentais**: Organizacao, pontualidade, planejamento, persistencia, atencao a detalhes, cumprimento de compromissos
- **Polo oposto**: Lack of Direction

#### 1.3 Extraversion
- **Facetas**: Warmth, Gregariousness, Assertiveness, Activity, Excitement-Seeking, Positive Emotions
- **Indicadores comportamentais**: Sociabilidade, energia em grupos, iniciativa social, expressividade emocional, busca por estimulacao
- **Polo oposto**: Introversion

#### 1.4 Agreeableness
- **Facetas**: Trust, Straightforwardness, Altruism, Compliance, Modesty, Tender-Mindedness
- **Indicadores comportamentais**: Cooperacao, empatia, disposicao para ajudar, evitacao de conflito, gentileza
- **Polo oposto**: Antagonism

#### 1.5 Neuroticism
- **Facetas**: Anxiety, Angry Hostility, Depression, Self-Consciousness, Impulsiveness, Vulnerability
- **Indicadores comportamentais**: Reatividade emocional, preocupacao, sensibilidade ao stress, oscilacao de humor
- **Polo oposto**: Emotional Stability

### 2. HEXACO Framework (Adicoes ao Big Five)

#### 2.1 Honesty-Humility (dimensao exclusiva do HEXACO)
- **Facetas**: Sincerity, Fairness, Greed Avoidance, Modesty
- **Indicadores comportamentais**: Transparencia, rejeicao de manipulacao, desapego material, ausencia de pretensao

#### 2.2 Emotionality (substitui Neuroticism parcialmente)
- **Facetas**: Fearfulness, Anxiety, Dependence, Sentimentality
- **Diferenca do Big Five**: Inclui dependencia emocional e sentimentalidade; exclui raiva hostil

#### 2.3 Demais dimensoes HEXACO
- **eXtraversion**: Similar ao Big Five, com Social Self-Esteem, Social Boldness, Sociability, Liveliness
- **Agreeableness**: Forgiveness, Gentleness, Flexibility, Patience (exclui sentimentalidade)
- **Conscientiousness**: Organization, Diligence, Perfectionism, Prudence
- **Openness**: Aesthetic Appreciation, Inquisitiveness, Creativity, Unconventionality

## Definicoes

| Termo | Definicao Operacional |
|-------|----------------------|
| Trait | Disposicao estavel que descreve padroes consistentes de pensamento, sentimento e comportamento |
| Facet | Subdimensao de um trait que captura aspecto especifico do construto |
| Behavioral Indicator | Comportamento observavel que sinaliza a presenca/intensidade de um trait |
| Trait Score | Valor numerico (tipicamente 1-5 ou percentil) indicando intensidade do trait |
| Cross-Framework Trait | Trait que aparece em mais de um framework com nomes diferentes |

## Relacoes entre Categorias

### Mapeamento Big Five <-> HEXACO

| Big Five | HEXACO | Nota |
|----------|--------|------|
| Openness | Openness | Alta correspondencia |
| Conscientiousness | Conscientiousness | Alta correspondencia |
| Extraversion | eXtraversion | Alta correspondencia, HEXACO inclui Social Self-Esteem |
| Agreeableness | Agreeableness + Honesty-Humility | Big Five Agreeableness se divide em duas dimensoes HEXACO |
| Neuroticism | Emotionality (parcial) | HEXACO Emotionality exclui raiva, inclui dependencia |

### Traits sem Correspondencia Direta
- **Honesty-Humility (HEXACO)**: Nao tem equivalente direto no Big Five; parcialmente capturado por facetas de Agreeableness
- **Angry Hostility (Big Five N)**: Migra para Agreeableness (invertido) no HEXACO
- **Impulsiveness (Big Five N)**: Parcialmente capturado por Conscientiousness (invertido) no HEXACO

## Uso no Pipeline

### Na Etapa de Coleta
- Identificar quais instrumentos de trait foram aplicados (NEO-PI-R, HEXACO-PI-R, BFI-2, etc.)
- Mapear resultados brutos para as categorias desta taxonomia

### Na Etapa de Analise
- Usar facetas (nao apenas dominios) para granularidade adequada
- Quando dois frameworks estiverem disponiveis, verificar convergencia usando a tabela de mapeamento
- Registrar confidence score baseado no numero de fontes convergentes

### Na Etapa de Sintese
- Priorizar traits com alta convergencia cross-framework
- Sinalizar divergencias como potenciais contradicoes (ver contradiction-taxonomy)
- Traduzir traits tecnicos em linguagem acessivel no report final

### Flags de Qualidade
- **HIGH**: Trait confirmado por 2+ frameworks com convergencia
- **MEDIUM**: Trait baseado em 1 framework com consistencia interna
- **LOW**: Trait inferido indiretamente ou com dados inconsistentes
