---
type: rubric
squad: human-mapping
version: "2.0.0"
---

# Confidence Scoring Rubric

## Proposito

Estabelecer criterios objetivos e replicaveis para atribuir confidence scores a cada
afirmacao, insight e recomendacao no perfil do Human Mapping Squad. O confidence score
comunica ao leitor quao fundamentada e cada conclusao, promovendo transparencia e
calibracao adequada de expectativas.

## Escala de Avaliacao

### Faixa 0.0 - 0.4: LOW Confidence
Dados insuficientes ou significativamente conflitantes. A afirmacao e uma hipotese,
nao uma conclusao.

### Faixa 0.4 - 0.7: MEDIUM Confidence
Dados parciais ou de fonte unica. A afirmacao e provavel mas nao confirmada por
multiplas evidencias.

### Faixa 0.7 - 1.0: HIGH Confidence
Dados robustos de multiplas fontes convergentes. A afirmacao e bem fundamentada
e confiavel para tomada de decisao.

## Criterios por Nivel

### 1. Data Quality (peso: 30%)

| Score | Criterio | Exemplo |
|-------|----------|---------|
| 0.0-0.2 | Dados de terceira mao ou sem fonte clara | "Alguem me disse que ele e introvertido" |
| 0.2-0.4 | Self-report informal, sem instrumento validado | Respondente descreveu-se em conversa casual |
| 0.4-0.6 | Self-report com instrumento validado, aplicacao unica | NEO-PI-R aplicado uma vez, sem feedback 360 |
| 0.6-0.8 | Assessment formal + entrevista de validacao | CliftonStrengths + entrevista de debrief |
| 0.8-1.0 | Multiplos assessments formais + observacao direta | NEO-PI-R + DISC + entrevista + feedback 360 |

### 2. Framework Convergence (peso: 30%)

| Score | Criterio | Exemplo |
|-------|----------|---------|
| 0.0-0.2 | Frameworks contradizem diretamente | Big Five E alto + MBTI I forte |
| 0.2-0.4 | Frameworks parcialmente conflitantes | DISC S alto + Enneagram tipo 7 |
| 0.4-0.6 | Um unico framework, sem contradicao nem confirmacao | Apenas resultado MBTI disponivel |
| 0.6-0.8 | Dois frameworks convergem | Big Five E alto + DISC I alto |
| 0.8-1.0 | Tres ou mais frameworks convergem | Big Five E + DISC I + MBTI E + Insights Yellow |

### 3. Respondent Consistency (peso: 20%)

| Score | Criterio | Exemplo |
|-------|----------|---------|
| 0.0-0.2 | Respondente deu respostas claramente contraditorias | "Adoro trabalhar sozinho" + "Preciso de gente por perto o tempo todo" |
| 0.2-0.4 | Respostas inconsistentes em areas relacionadas | Alta assertividade declarada mas comportamento passivo relatado |
| 0.4-0.6 | Respostas majoritariamente consistentes, com algumas variações | Perfil coerente com 1-2 pontos ambiguos |
| 0.6-0.8 | Respostas consistentes ao longo do assessment | Narrativa coerente, sem contradicoes aparentes |
| 0.8-1.0 | Alta consistencia interna + validacao externa | Respondente confirma resultados + chefe e colegas concordam |

### 4. Completeness (peso: 20%)

| Score | Criterio | Exemplo |
|-------|----------|---------|
| 0.0-0.2 | Apenas 1 dimensao avaliada, dados muito parciais | Apenas tipo MBTI sem detalhes |
| 0.2-0.4 | 2-3 dimensoes cobertas superficialmente | MBTI + DISC sem profundidade |
| 0.4-0.6 | Cobertura moderada das dimensoes principais | Traits + Types, sem motivacoes ou strengths |
| 0.6-0.8 | Cobertura ampla com algumas lacunas | Traits + Types + Motivacoes, strengths parciais |
| 0.8-1.0 | Cobertura completa de todas as dimensoes | Traits + Types + Motivacoes + Strengths + Contradicoes analisadas |

## Como Aplicar

### Passo 1: Avaliar cada criterio individualmente
Para cada afirmacao no report, avaliar os 4 criterios separadamente.

### Passo 2: Calcular score ponderado
```
Confidence Score = (Data Quality x 0.30) + (Framework Convergence x 0.30)
                 + (Respondent Consistency x 0.20) + (Completeness x 0.20)
```

### Passo 3: Aplicar ajustes
- **Bonus (+0.05)**: Quando ha evidencia comportamental direta (nao apenas self-report)
- **Penalidade (-0.10)**: Quando ha contradicao Level 3 nao resolvida (ver contradiction-taxonomy)
- **Penalidade (-0.20)**: Quando ha contradicao Level 4 (ver contradiction-taxonomy)
- **Floor**: Score minimo final = 0.1 (nunca zero — sempre ha alguma informacao)
- **Ceiling**: Score maximo final = 0.95 (nunca 1.0 — sempre ha margem de incerteza)

### Passo 4: Classificar e rotular
| Score Final | Label | Acao no Report |
|-------------|-------|---------------|
| 0.1 - 0.4 | LOW | Marcar como "hipotese" ou "indicacao preliminar" |
| 0.4 - 0.7 | MEDIUM | Apresentar como "analise com confianca moderada" |
| 0.7 - 0.95 | HIGH | Apresentar como "conclusao bem fundamentada" |

## Exemplos

### Exemplo 1: HIGH Confidence (Score = 0.82)
**Afirmacao**: "O respondente possui forte orientacao para Extraversion."
- Data Quality: 0.8 (NEO-PI-R formal + entrevista)
- Framework Convergence: 0.9 (Big Five E alto + MBTI E + DISC I + Insights Yellow)
- Respondent Consistency: 0.8 (respostas consistentes, auto-percepcao alinhada)
- Completeness: 0.7 (falta feedback 360)
- **Calculo**: (0.8 x 0.3) + (0.9 x 0.3) + (0.8 x 0.2) + (0.7 x 0.2) = 0.81

### Exemplo 2: MEDIUM Confidence (Score = 0.55)
**Afirmacao**: "A motivacao principal e busca por autonomia."
- Data Quality: 0.5 (Enneagram via questionario online)
- Framework Convergence: 0.6 (Enneagram 5 + Reiss Independence alta, sem SDI)
- Respondent Consistency: 0.6 (majoritariamente consistente)
- Completeness: 0.4 (apenas 2 frameworks motivacionais)
- **Calculo**: (0.5 x 0.3) + (0.6 x 0.3) + (0.6 x 0.2) + (0.4 x 0.2) = 0.53

### Exemplo 3: LOW Confidence (Score = 0.30)
**Afirmacao**: "O respondente tende a evitar conflito."
- Data Quality: 0.3 (comentario casual do gestor)
- Framework Convergence: 0.2 (DISC S alto mas Enneagram tipo 8 — contradicao)
- Respondent Consistency: 0.4 (dados limitados para avaliar)
- Completeness: 0.3 (dimensao pouco explorada)
- **Calculo**: (0.3 x 0.3) + (0.2 x 0.3) + (0.4 x 0.2) + (0.3 x 0.2) = 0.29

## Notas Importantes

- Confidence score e sobre a QUALIDADE DA EVIDENCIA, nao sobre a intensidade do trait
- Um trait pode ser forte (Extraversion alta) mas com LOW confidence (dados ruins)
- Sempre reportar o confidence score junto com a afirmacao — nunca omitir
- Recalibrar scores quando novos dados chegam ao longo do pipeline
