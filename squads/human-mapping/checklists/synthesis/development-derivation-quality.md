---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/templates/development/development-plan-template.md
---
# Checklist: Development Derivation Quality

## Proposito
Garantir que cada recomendacao de desenvolvimento tem cadeia de evidencia rastreavel: dado comportamental -> conclusao do perfil -> area de desenvolvimento -> recomendacao acionavel. Nenhuma recomendacao sem fundamentacao.

## Criterios Obrigatorios

- [ ] **Multi-Framework Citation** — Each development recommendation cites >= 2 framework findings
  - Threshold: Every recommendation references findings from >= 2 distinct frameworks
  - Evidence: Citation table per recommendation: recommendation -> framework 1 finding -> framework 2 finding
  - Fail action: development-planner adds supporting framework citations or removes the recommendation

- [ ] **Quick Win Confidence** — Quick wins trace to high-confidence findings (>= 0.7)
  - Threshold: Every item classified as "quick win" or "short-term (1-3 months)" is backed by findings with confidence >= 0.7
  - Evidence: Confidence score listed next to each quick win's supporting finding
  - Fail action: development-planner reclassifies low-confidence items as strategic or removes them from quick wins

- [ ] **Strategic Investment Convergence** — Strategic investments trace to convergent findings across >= 3 frameworks
  - Threshold: Every item classified as "strategic investment" or "long-term (6-12 months)" cites convergent evidence from >= 3 frameworks
  - Evidence: Convergence table per strategic item: item -> framework 1 + framework 2 + framework 3 findings
  - Fail action: development-planner adds convergent evidence or downgrades the recommendation

- [ ] **Complete Evidence Chain** — No recommendation without evidence chain: finding -> implication -> action
  - Threshold: 0 recommendations missing any link in the chain; format per recommendation: "[Finding: score X in framework Y] -> [Implication: behavioral pattern Z] -> [Action: do W]"
  - Evidence: Evidence chain documented per recommendation in structured format
  - Fail action: development-planner completes the chain or removes the recommendation

- [ ] **Profile Coherence** — Recommendations are coherent with the integrated profile
  - Threshold: 0 recommendations that contradict the profile (e.g., no "be more extroverted" for Extraversion 0.80); >= 50% of recommendations leverage existing strengths (score >= 0.60)
  - Evidence: Cross-check each recommendation against profile scores
  - Fail action: development-planner removes contradictory recommendations

- [ ] **Actionability** — Each recommendation describes WHO does WHAT by WHEN
  - Threshold: Every recommendation includes a concrete action (not just "improve X"), context, and timeframe classification (short/medium/long)
  - Evidence: Verify each recommendation has action verb, specific behavior, and time horizon
  - Fail action: development-planner rewrites vague recommendations with specific actions

- [ ] **Priority Cap** — Maximum 5 prioritized development areas
  - Threshold: <= 5 areas in priority list; additional areas listed as "future" if needed; prioritization criteria documented
  - Evidence: Count of priority areas; presence of prioritization rationale
  - Fail action: development-planner reduces to 5 and documents selection criteria

- [ ] **Progress Indicators** — Each area has a measurable progress indicator
  - Threshold: >= 1 metric or behavioral indicator per development area (e.g., "Success = delegate >= 2 tasks/week without rework")
  - Evidence: Indicator listed per area
  - Fail action: development-planner defines measurable indicators

## Criterios Desejaveis
- [ ] Timeline suggested for each area
- [ ] Specific development resources and strategies recommended
- [ ] Expected performance impact estimated
- [ ] Alignment with career objectives when available

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> rework obrigatorio

## Acao se Falhar
1. development-planner adds evidence chains for each unsupported recommendation
2. development-planner removes recommendations that cannot be grounded
3. development-planner specifies concrete actions for vague recommendations
**Bloqueio**: Plano de desenvolvimento nao avanca para relatorio final sem rastreabilidade completa.

## Agente Responsavel
development-planner — Arquivo: `agents/development-planner.md`
