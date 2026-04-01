---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/templates/synthesis/integrated-profile-map.md
---
# Checklist: Multi-Layer Integration Quality

## Proposito
Verificar que todas as 7+ camadas do pipeline estao representadas na sintese final, com pesos corretos, conexoes documentadas e nenhuma omissao silenciosa.

## Criterios Obrigatorios

- [ ] **Layer Count Check** — All 7+ layers represented in synthesis
  - Threshold: trait-map, type-map, motivation-map, strength-map, career-fit, mode-of-action, team-role all referenced; delta between executed layers and reported layers = 0
  - Evidence: Compare `session-log.camadas_executadas` with `relatorio.camadas_presentes`; list both counts
  - Fail action: synthesis-architect adds missing layers before re-submission

- [ ] **Key Finding Trace** — Each layer's key finding appears in the final integrated map
  - Threshold: >= 2 conclusions per layer, each referencing >= 1 observed behavioral data point
  - Evidence: Cross-reference table showing layer -> key finding -> location in final map
  - Fail action: synthesis-architect traces missing findings and inserts them

- [ ] **Layer Weight Compliance** — Layer weights follow prescribed hierarchy
  - Threshold: traits(0.30 +/-0.05) > types(0.20 +/-0.05) > motivation(0.20 +/-0.05) > strengths(0.15 +/-0.05) > career(0.10 +/-0.05) > conation(0.05 +/-0.05); sum = 1.00 exact
  - Evidence: Weight table in synthesis document with numeric values per layer
  - Fail action: synthesis-architect recalculates weights per `frameworks/confidence-scoring-model.md`

- [ ] **No Silent Omission** — No layer omitted without documented justification
  - Threshold: Field "camadas_excluidas" is empty OR each exclusion has >= 2 sentence justification in session-log
  - Evidence: Session-log exclusion field content
  - Fail action: synthesis-architect provides justification or includes the omitted layer

- [ ] **Cross-Layer Connections** — Explicit connections between layers documented
  - Threshold: >= 3 explicit connections between distinct layers (e.g., "High Openness [Traits] + Explorer Type [MBTI] = innovation pattern")
  - Evidence: Connection table or narrative section listing cross-layer patterns
  - Fail action: synthesis-architect identifies and documents missing connections

- [ ] **Emergent Insights** — At least 1 insight that only appears from layer intersection
  - Threshold: >= 1 insight not visible in any single layer alone
  - Evidence: Documented emergent insight with source layers cited
  - Fail action: synthesis-architect performs cross-layer analysis to identify emergent patterns

- [ ] **Contradiction Resolution** — All inter-layer contradictions have documented resolution
  - Threshold: 0 unresolved contradictions; each resolution includes framework of origin, conflict nature, and decision taken
  - Evidence: Contradiction log with resolution entries
  - Fail action: synthesis-architect resolves each contradiction with chief oversight

## Criterios Desejaveis
- [ ] Convergence points across >= 3 layers highlighted as high-confidence findings
- [ ] Productive tensions identified as nuances (not errors)
- [ ] Integrative narrative connects all layers into a coherent story
- [ ] Visual map of layer integration generated

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios obrigatorios atendidos, gaps documentados com plano de correcao
- **FAIL**: <50% criterios obrigatorios atendidos -> rework obrigatorio

## Acao se Falhar
1. synthesis-architect receives specific list of failing criteria
2. synthesis-architect re-integrates missing layers, recalculates weights, documents connections
3. Re-submit for checklist re-evaluation
**Bloqueio**: Nao avancar para report-writer ate todos os criterios obrigatorios passarem.

## Agente Responsavel
synthesis-architect — Arquivo: `agents/synthesis-architect.md`
