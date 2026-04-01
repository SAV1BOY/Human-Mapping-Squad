---
type: checklist
level: layer
layer: traits
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/reference/psychology/big-five-model.md
---
# Checklist: Big Five Measurement Quality

## Proposito
Garantir que os cinco fatores foram medidos com minimo 8 indicadores comportamentais por dimensao, confidence >= 0.50 por dimensao e validacao cruzada com >= 1 outro framework de tracos (HEXACO ou 16PF).

## Thresholds de Referencia

| Dimensao | Indicadores Minimos | Confidence Minima | Score Extremo (requer validacao extra) |
|---|---|---|---|
| Abertura a Experiencia | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Conscienciosidade | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Extroversao | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Amabilidade | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Neuroticismo | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |

## Criterios Obrigatorios

- [ ] **Openness Indicators** — Abertura medida com minimo 8 indicadores comportamentais
  - Threshold: >= 8 distinct behavioral indicators; each references observed behavior or specific response
  - Evidence: Numbered list of indicators with behavioral descriptions
  - Fail action: traits-agent applies additional items to reach >= 8 indicators

- [ ] **Conscientiousness Indicators** — Conscienciosidade medida com minimo 8 indicadores comportamentais
  - Threshold: >= 8 distinct behavioral indicators
  - Evidence: Numbered list of indicators with behavioral descriptions
  - Fail action: traits-agent applies additional items to reach >= 8 indicators

- [ ] **Extraversion Indicators** — Extroversao medida com minimo 8 indicadores comportamentais
  - Threshold: >= 8 distinct behavioral indicators
  - Evidence: Numbered list of indicators with behavioral descriptions
  - Fail action: traits-agent applies additional items to reach >= 8 indicators

- [ ] **Agreeableness Indicators** — Amabilidade medida com minimo 8 indicadores comportamentais
  - Threshold: >= 8 distinct behavioral indicators
  - Evidence: Numbered list of indicators with behavioral descriptions
  - Fail action: traits-agent applies additional items to reach >= 8 indicators

- [ ] **Neuroticism Indicators** — Neuroticismo medido com minimo 8 indicadores comportamentais
  - Threshold: >= 8 distinct behavioral indicators
  - Evidence: Numbered list of indicators with behavioral descriptions
  - Fail action: traits-agent applies additional items to reach >= 8 indicators

- [ ] **Per-Dimension Confidence** — Confidence >= 0.50 per dimension
  - Threshold: Each of the 5 dimensions has confidence >= 0.50; dimensions below 0.50 marked as "insufficient confidence"
  - Evidence: Confidence value documented per dimension (numeric, in [0.0, 1.0])
  - Fail action: traits-agent applies additional items; if confidence remains < 0.50 after reinforcement, dimension reported as "inconclusive" — never infer a score without adequate confidence

- [ ] **Cross-Validation with Another Trait Framework** — Cross-validation with >= 1 other trait framework (HEXACO or 16PF)
  - Threshold: >= 1 cross-validation point per dimension against HEXACO or 16PF findings; convergent/divergent results documented
  - Evidence: Cross-validation table: Big Five dimension -> corresponding HEXACO/16PF dimension -> convergence status (agree/diverge/partial)
  - Fail action: traits-agent performs cross-validation; divergences documented as findings, not suppressed

- [ ] **Score Normalization** — Scores normalized to reference population
  - Threshold: Normalization method documented (percentile, z-score, etc.); reference population identified
  - Evidence: Normalization method and population reference in profile artifact
  - Fail action: traits-agent applies normalization and documents method

- [ ] **Inter-Dimension Plausibility** — Correlations between dimensions are plausible
  - Threshold: No theoretically impossible correlations without special justification (e.g., all 5 dimensions at extreme without explanation); plausibility analysis recorded
  - Evidence: Plausibility check result documented
  - Fail action: traits-agent investigates implausible patterns and documents explanation

- [ ] **Qualitative Cross-Check** — Results crossed with qualitative session data
  - Threshold: >= 1 qualitative validation point per dimension (e.g., "Extraversion 0.75 confirmed by observed behavior X during session")
  - Evidence: Qualitative validation entries per dimension
  - Fail action: traits-agent adds qualitative cross-references

- [ ] **Extreme Score Validation** — Dimensions with extreme scores validated with additional questions
  - Threshold: Each dimension with score >= 0.85 or <= 0.15 has >= 2 additional validation questions applied and documented
  - Evidence: Validation question list and results per extreme dimension
  - Fail action: traits-agent applies validation questions for extreme scores

- [ ] **Standardized Profile Generated** — Big Five profile in standardized format
  - Threshold: Profile document includes all 5 dimensions with: numeric score, confidence score, classification (low/medium/high)
  - Evidence: Standardized profile artifact
  - Fail action: traits-agent generates profile in required format

## Criterios Desejaveis
- [ ] Facets (sub-dimensions) assessed for dimensions with >= 10 indicators
- [ ] Comparison with industry/function-specific norms when available
- [ ] Confidence interval estimated per score (+/- margin)
- [ ] Graphical visualization of Big Five profile generated

## Decisao
- **PASS**: All 5 dimensions have >= 8 indicators AND confidence >= 0.50 AND cross-validation completed
- **PARTIAL PASS**: >= 3 dimensions pass; insufficient dimensions marked as "inconclusive"
- **FAIL**: < 3 dimensions with sufficient data -> consider full re-evaluation

## Acao se Falhar
1. traits-agent applies additional behavioral indicators for dimensions with < 8 indicators
2. If confidence remains < 0.50 after reinforcement: report dimension as "inconclusive"
3. Never infer a score without adequate confidence — better to report a gap than fabricate data
4. If >= 3 dimensions inconclusive: consider complete re-evaluation
**Bloqueio**: Big Five profile with < 3 conclusive dimensions does not advance to synthesis.

## Agente Responsavel
traits-agent — Arquivo: `agents/traits-agent.md`
