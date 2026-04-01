---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Longitudinal Change Detector

## Proposito

Detectar mudancas genuinas entre sessoes de assessment ao longo do tempo, separando sinal (mudanca real) de ruido (variacao por erro de medida, humor, contexto). Este script complementa a longitudinal-comparison-rubric com um algoritmo sistematico de deteccao.

## Input

- `assessment_t1`: Resultados do assessment no tempo 1 (anterior)
- `assessment_t2`: Resultados do assessment no tempo 2 (atual)
- `time_gap_months`: Tempo decorrido entre assessments em meses
- `life_events`: Eventos de vida significativos no periodo (lista)
- `development_actions`: Acoes de desenvolvimento realizadas no periodo (lista)
- `instruments_used`: Lista de instrumentos em cada tempo (idealmente os mesmos)

## Algoritmo

### Passo 1: Validar Comparabilidade

```
comparability_check:
  same_instruments: (t1_instruments intersect t2_instruments) / t1_instruments
  minimum_time_respected: time_gap_months >= minimum_for_instrument
  same_conditions: (mesmo formato, mesma lingua, contexto similar)

Se comparability_check < 0.5:
  WARN: "Comparacao tem limitacoes significativas — interpretar com cautela"
  confidence_penalty: -0.20
```

### Passo 2: Calcular Deltas por Dimensao

Para cada dimensao comparavel entre t1 e t2:

```yaml
delta_analysis:
  - dimension: "Big Five Openness"
    t1_score: ___
    t2_score: ___
    delta: t2 - t1
    delta_percentile_points: abs(delta)
    instrument_SEM: ___ (erro padrao de medida do instrumento)
    delta_in_SEM_units: delta / instrument_SEM
```

### Passo 3: Classificar Cada Delta

```
Para cada delta:
  Se abs(delta_in_SEM_units) < 1.0:
    classification: "RUIDO" (dentro do erro de medida)
    confidence_of_change: 0.15

  Se 1.0 <= abs(delta_in_SEM_units) < 1.5:
    classification: "POSSIVEL_MUDANCA" (zona ambigua)
    confidence_of_change: 0.45

  Se 1.5 <= abs(delta_in_SEM_units) < 2.0:
    classification: "MUDANCA_PROVAVEL" (acima do ruido)
    confidence_of_change: 0.70

  Se abs(delta_in_SEM_units) >= 2.0:
    classification: "MUDANCA_SIGNIFICATIVA" (forte evidencia)
    confidence_of_change: 0.85
```

### Passo 4: Cross-Framework Validation

```
Para cada mudanca classificada como POSSIVEL ou superior:
  Verificar se outros frameworks mostram mudanca na mesma direcao:

  convergence_count = numero de frameworks que mostram mudanca similar

  Se convergence_count >= 2:
    confidence_boost: +0.10
    note: "Mudanca convergente entre frameworks"
  Se convergence_count == 1:
    confidence_boost: 0
    note: "Mudanca detectada em framework unico — cautela"
  Se convergence_count == 0 e delta significativo:
    confidence_penalty: -0.15
    note: "Mudanca isolada — possivel artefato"
```

### Passo 5: Contextual Validation

```
Para cada mudanca detectada:

  life_event_support:
    Se life_events contem evento relevante para a dimensao:
      confidence_boost: +0.10
      note: "Evento de vida consistente com mudanca"
    Senao:
      note: "Sem evento de vida aparente — investigar"

  development_support:
    Se development_actions inclui acao relevante para a dimensao:
      confidence_boost: +0.10
      note: "Desenvolvimento intencional na direcao da mudanca"
    Senao:
      note: "Mudanca nao associada a desenvolvimento intencional"

  direction_check:
    Se mudanca na direcao esperada para idade/maturidade:
      confidence_boost: +0.05
      note: "Consistente com maturacao natural"
    Se mudanca na direcao OPOSTA ao esperado:
      confidence_penalty: -0.05
      note: "Direcao inesperada — investigar"
```

### Passo 6: Gerar Report de Mudanca

```
Para cada dimensao, calcular confidence_final:
  confidence_final = base_confidence + sum(boosts) + sum(penalties)
  Floor: 0.10
  Ceiling: 0.90
```

## Output

```yaml
longitudinal_change_report:
  respondent_id: ___
  t1_date: ___
  t2_date: ___
  time_gap_months: ___
  comparability_score: ___

  changes_detected:
    - dimension: ___
      t1: ___
      t2: ___
      delta: ___
      classification: "(RUIDO / POSSIVEL_MUDANCA / MUDANCA_PROVAVEL / MUDANCA_SIGNIFICATIVA)"
      confidence: ___
      cross_framework_support: (Sim / Nao)
      contextual_support: ___
      interpretation: "Texto explicativo"

  stable_dimensions:
    - dimension: ___
      t1: ___
      t2: ___
      note: "Estavel conforme esperado para este construto"

  summary:
    total_dimensions_compared: ___
    genuine_changes: ___
    noise: ___
    ambiguous: ___
    overall_profile_stability: "(Alta / Moderada / Baixa)"

  growth_indicators:
    - area: ___
      direction: "(Positiva / Negativa / Neutra)"
      evidence: ___

  recommendations:
    - ___
```

## Valores de Referencia para SEM (Erro Padrao de Medida)

| Instrumento | Dimensao | SEM Tipico (percentis) |
|-------------|----------|----------------------|
| NEO-PI-R | Dominios Big Five | 4-6 percentis |
| NEO-PI-R | Facetas | 6-9 percentis |
| DISC | Quadrantes | 5-8 percentis |
| CliftonStrengths | Ranking top 10 | 2-3 posicoes |
| Kolbe | MO scores | 1-2 pontos |
| Birkman | Componentes | 5-8 percentis |

## Limitacoes

- SEM varia por instrumento e por populacao — usar valores do manual tecnico quando disponivel
- Efeito de pratica pode inflacionar ou deflacionar mudancas se o intervalo for curto
- Mudancas em Enneagram tipo e MBTI tipo nao sao bem capturadas por delta numerico — tratar qualitativamente
- Este script detecta mudanca, mas nao explica a causa — a interpretacao e humana
