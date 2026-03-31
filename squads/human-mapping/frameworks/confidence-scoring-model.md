---
framework: confidence-scoring-model
category: operational
squad: human-mapping
version: "2.0.0"
---

# Confidence Scoring Model

## Propósito

O Confidence Scoring Model é o sistema completo de quantificação de confiança do squad. Cada conclusão de assessment tem um grau de certeza associado, e esse grau deve ser transparente para o facilitador, o squad e o solicitante. Este modelo define a fórmula de cálculo, os fatores que aumentam ou reduzem confiança, os thresholds mínimos por camada e as ações quando a confiança é insuficiente.

O score de confiança não mede a "qualidade" da pessoa avaliada. Mede a qualidade dos DADOS e da INTERPRETAÇÃO. Um score de 0.50 não significa que a pessoa é "mediana" — significa que temos certeza moderada sobre nossas conclusões.

## Quando Usar

- Em TODA conclusão de assessment, sem exceção
- Ao finalizar cada camada de avaliação
- No cálculo do confidence global para a Persona Synthesis
- Na tabela de confiança do Executive Brief
- Quando o solicitante questiona a certeza de uma conclusão
- Na calibração do squad para definir thresholds

## Modelo / Estrutura

### Escala de Confiança: 0.0 a 1.0

```
0.90 - 1.00  │  MUITO ALTA   │  Múltiplos instrumentos oficiais convergentes, respondente
             │               │  engajado, dados observacionais confirmam. Conclusões firmes.
─────────────┼───────────────┼──────────────────────────────────────────────────────────────
0.75 - 0.89  │  ALTA         │  Instrumentos oficiais ou proxy de qualidade, boa convergência,
             │               │  poucas contradições. Conclusões confiáveis com ressalvas mínimas.
─────────────┼───────────────┼──────────────────────────────────────────────────────────────
0.60 - 0.74  │  ADEQUADA     │  Mix de instrumentos oficiais e proxy, convergência razoável,
             │               │  algumas contradições resolvidas. Conclusões válidas com ressalvas.
─────────────┼───────────────┼──────────────────────────────────────────────────────────────
0.45 - 0.59  │  MODERADA     │  Predominantemente proxy, convergência parcial, contradições
             │               │  não totalmente resolvidas. Conclusões cautelosas.
─────────────┼───────────────┼──────────────────────────────────────────────────────────────
0.30 - 0.44  │  BAIXA        │  Poucos instrumentos, modo proxy, convergência fraca.
             │               │  Conclusões tentativas. Recomendar triangulação adicional.
─────────────┼───────────────┼──────────────────────────────────────────────────────────────
0.00 - 0.29  │  INSUFICIENTE │  Dados insuficientes ou não confiáveis. Não emitir conclusões.
             │               │  Re-aplicar ou declarar camada incompleta.
```

### Fatores do Score de Confiança

#### Fator 1: Número de Frameworks Convergentes (peso: 0.30)

| Condição | Score do Fator |
|----------|---------------|
| 3+ frameworks convergem na mesma camada | 1.0 |
| 2 frameworks convergem | 0.75 |
| 1 framework isolado (oficial) | 0.50 |
| 1 framework isolado (proxy) | 0.30 |
| Nenhum framework aplicado na camada | 0.00 |

#### Fator 2: Qualidade das Respostas (peso: 0.20)
Derivado do Response Reliability Model.

| Condição | Score do Fator |
|----------|---------------|
| Reliability score > 0.85 | 1.0 |
| Reliability score 0.70-0.84 | 0.80 |
| Reliability score 0.50-0.69 | 0.55 |
| Reliability score 0.30-0.49 | 0.30 |
| Reliability score < 0.30 | 0.10 |

#### Fator 3: Modo de Aplicação (peso: 0.20)

| Condição | Score do Fator |
|----------|---------------|
| Instrumento oficial, aplicação supervisionada | 1.0 |
| Instrumento oficial, auto-aplicação | 0.85 |
| Proxy com dados ricos (entrevista longa, múltiplas fontes) | 0.60 |
| Proxy com dados moderados | 0.40 |
| Proxy com dados mínimos (apenas conversa breve) | 0.20 |

#### Fator 4: Completude da Camada (peso: 0.15)

| Condição | Score do Fator |
|----------|---------------|
| Camada completamente avaliada (todos os construtos relevantes) | 1.0 |
| Camada majoritariamente avaliada (>75% dos construtos) | 0.80 |
| Camada parcialmente avaliada (50-75%) | 0.55 |
| Camada minimamente avaliada (<50%) | 0.30 |
| Camada com gap crítico (construto essencial ausente) | 0.15 |

#### Fator 5: Ausência de Contradições Não-Resolvidas (peso: 0.15)

| Condição | Score do Fator |
|----------|---------------|
| Zero contradições preocupantes ou todas resolvidas | 1.0 |
| 1 contradição preocupante resolvida satisfatoriamente | 0.80 |
| 1-2 contradições preocupantes parcialmente resolvidas | 0.55 |
| 3+ contradições preocupantes ou 1 não resolvida | 0.30 |
| Contradição invalidante presente | 0.10 |

### Fórmula de Cálculo

```
Confidence Score (camada) =
    (F1 × 0.30) + (F2 × 0.20) + (F3 × 0.20) + (F4 × 0.15) + (F5 × 0.15)

Confidence Score (global) =
    Média ponderada dos scores por camada, usando os pesos do Persona Synthesis Model

Exemplo:
  F1 (convergência)  = 0.75  × 0.30 = 0.225
  F2 (qualidade)     = 0.80  × 0.20 = 0.160
  F3 (modo)          = 0.60  × 0.20 = 0.120
  F4 (completude)    = 0.80  × 0.15 = 0.120
  F5 (contradições)  = 1.00  × 0.15 = 0.150
  ─────────────────────────────────────────
  TOTAL                               0.775 → ALTA confiança
```

### Thresholds Mínimos por Camada

| Camada | Threshold para Emitir Conclusão | Threshold para Decisão de Alto Impacto |
|--------|-------------------------------|---------------------------------------|
| Traços (Big Five, Hogan) | 0.50 | 0.70 |
| Tipos (MBTI, DISC) | 0.45 | 0.65 |
| Motivação (Reiss, Eneagrama) | 0.45 | 0.65 |
| Forças (CliftonStrengths) | 0.50 | 0.70 |
| Conação (Kolbe) | 0.45 | 0.65 |
| Inteligência/Referencial | 0.55 | 0.75 |
| Carreira (Holland, Schein) | 0.45 | 0.65 |
| Papéis de Time (Belbin) | 0.45 | 0.65 |

## Como Aplicar (step by step)

### Step 1: Calcular Cada Fator para a Camada
- F1: Quantos frameworks convergem nesta camada?
- F2: Qual o score de confiabilidade das respostas? (do Response Reliability Model)
- F3: Os instrumentos foram oficiais ou proxy?
- F4: A camada está completa ou há gaps?
- F5: Há contradições não resolvidas?

### Step 2: Aplicar a Fórmula
- Multiplicar cada fator pelo seu peso
- Somar para obter o score da camada
- Registrar com justificativa

### Step 3: Verificar Threshold
- O score atingiu o threshold mínimo para emitir conclusão?
- Se decisão de alto impacto (contratação, demissão, promoção): threshold mais alto
- Se abaixo do threshold: NÃO emitir conclusão. Documentar como "dados insuficientes"

### Step 4: Calcular Score Global
- Usar os pesos do Persona Synthesis Model por contexto
- Exemplo (contexto contratação): Traços × 0.30 + Tipos × 0.20 + Motivação × 0.15 + ...
- O global nunca pode ser maior que a maior camada individual (cap)

### Step 5: Reportar no Executive Brief
- Incluir tabela de confiança no brief
- Se alguma camada está abaixo de 0.60, incluir nota explicativa
- Se o global está abaixo de 0.65, incluir recomendação de triangulação adicional

### Step 6: Ação quando Confiança é Insuficiente
- Score 0.45-0.59: Emitir conclusões com qualificação "moderada confiança"
- Score 0.30-0.44: Emitir apenas observações preliminares, recomendar mais dados
- Score < 0.30: Não emitir conclusão. Recomendar re-aplicação ou fonte adicional.
- Nunca inflar o score. Se os dados são fracos, dizer que são fracos.

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Objetividade | Score calculado por fórmula, não por impressão |
| Transparência | Cada fator é documentado e justificado |
| Calibração | Dois facilitadores calculam scores similares (±0.05) |
| Ação vinculada | Scores abaixo do threshold geram ação concreta |
| Não inflacionado | O squad resiste à tentação de "arredondar para cima" |

## Integração com Pipeline

### Input
- **Response Reliability Model** → Fator 2
- **Social Desirability Screen** → afeta Fator 2
- **Contradiction Baseline** / **Cross-Framework Reconciliation** → Fator 5
- Dados de todos os instrumentos → Fatores 1, 3, 4

### Output
- Score por camada → **Persona Synthesis Model**
- Tabela de confiança → **Executive Brief Model**
- Decisão de emitir/não emitir conclusão → facilitador e solicitante

### Posição no Pipeline
```
[Todos os Frameworks Operacionais] → [Confidence Scoring Model] → [Persona Synthesis]
                                                                        ↓
                                                               [Executive Brief]
```

## Exemplos

### Exemplo: Assessment Completo (Full Battery Oficial)
| Camada | F1 | F2 | F3 | F4 | F5 | Score |
|--------|-----|-----|-----|-----|-----|-------|
| Traços | 1.0 | 0.90 | 1.0 | 1.0 | 1.0 | **0.97** |
| Tipos | 0.75 | 0.85 | 0.85 | 0.80 | 0.80 | **0.81** |
| Motivação | 0.75 | 0.80 | 0.60 | 0.80 | 1.0 | **0.78** |
| Forças | 0.50 | 0.85 | 0.85 | 1.0 | 1.0 | **0.80** |
| **Global (Liderança)**: **0.85** — ALTA confiança |

### Exemplo: Assessment Rápido (Proxy Only)
| Camada | F1 | F2 | F3 | F4 | F5 | Score |
|--------|-----|-----|-----|-----|-----|-------|
| Traços | 0.30 | 0.55 | 0.40 | 0.55 | 0.55 | **0.45** |
| Tipos | 0.30 | 0.55 | 0.40 | 0.30 | 0.80 | **0.44** |
| **Global**: **0.45** — MODERADA. Conclusões cautelosas apenas. |
