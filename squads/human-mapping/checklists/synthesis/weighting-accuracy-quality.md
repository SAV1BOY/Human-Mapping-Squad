---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
---
# Checklist: Weighting Accuracy Quality

## Proposito
Garantir que os pesos por camada foram aplicados conforme o modelo de confianca, que a hierarquia tracos > tipos > motivacao e respeitada, e que nenhuma conclusao depende de um unico framework.

## Criterios Obrigatorios

- [ ] **Trait Evidence Priority** — Trait evidence weighted highest in all conclusions
  - Threshold: Traits weight >= any other single layer weight; trait data cited in >= 80% of major conclusions in the final report
  - Evidence: Count trait citations in final report conclusions; verify traits weight is numerically highest in weight table
  - Fail action: synthesis-architect re-weights conclusions to prioritize trait evidence

- [ ] **Type Derived from Traits** — Type conclusions derived from trait base, not treated as independent
  - Threshold: Each type conclusion references >= 2 specific trait scores that support it
  - Evidence: Trace table showing type conclusion -> supporting trait scores (e.g., "INTJ typing supported by Openness 0.82, Extraversion 0.28")
  - Fail action: synthesis-architect adds trait-based justification to each type conclusion

- [ ] **Motivation Follows Type Context** — Motivation conclusions follow type context in the analytical sequence
  - Threshold: Each motivation finding references the type context within which it operates; sequence check: traits -> types -> motivation in reasoning chain
  - Evidence: Reasoning chain documented per motivation conclusion showing type context
  - Fail action: synthesis-architect restructures motivation conclusions to include type context

- [ ] **No Single-Framework Conclusions** — No conclusion relies on a single framework alone
  - Threshold: Every major conclusion in the synthesis cites >= 2 distinct frameworks
  - Evidence: Audit each conclusion in synthesis; flag any citing only 1 framework
  - Fail action: synthesis-architect either adds supporting framework evidence or downgrades conclusion confidence

- [ ] **Weight Sum Exact** — Sum of all layer weights = 1.00
  - Threshold: Mathematical sum = 1.00 with zero tolerance
  - Evidence: Computed sum from weight table
  - Fail action: synthesis-architect corrects arithmetic

- [ ] **Deviation Justification** — Every weight deviation from standard has documented rationale
  - Threshold: For each weight differing from standard (traits:0.30, types:0.20, motivation:0.20, strengths:0.15, career:0.10, conation:0.05), justification references layer confidence score
  - Evidence: Justification text per deviation (e.g., "Conation reduced from 0.05 to 0.03 due to confidence 0.35")
  - Fail action: synthesis-architect documents rationale or reverts to standard weights

## Criterios Desejaveis
- [ ] Sensitivity analysis performed: does result change significantly if weights vary +/- 0.05?
- [ ] Theoretical justification for weight hierarchy referenced
- [ ] Weight calibration based on past sessions documented

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> rework obrigatorio

## Acao se Falhar
1. synthesis-architect recalculates weights per `frameworks/confidence-scoring-model.md`
2. synthesis-architect adds trait-base justification to type and motivation conclusions
3. synthesis-architect ensures every conclusion cites >= 2 frameworks
**Bloqueio**: Sintese nao avanca ate pesos estarem conformes.

## Agente Responsavel
synthesis-architect — Arquivo: `agents/synthesis-architect.md`
