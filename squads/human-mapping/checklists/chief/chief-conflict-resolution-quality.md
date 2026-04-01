---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/checklists/contradiction/contradiction-audit-quality.md
---
# Checklist: Chief Conflict Resolution Quality

## Proposito
Garantir que todo conflito entre frameworks foi identificado, classificado por severidade, resolvido com justificativa respondent-specific e confidence ajustada. Zero conflitos S3/S4 em aberto.

## Criterios Obrigatorios

- [ ] **Documented Resolution Per Conflict** — Each framework conflict has documented resolution
  - Threshold: 0 identified conflicts without a resolution entry; each resolution includes: Framework A position, Framework B position, resolution decision, rationale (>= 2 sentences)
  - Evidence: Conflict resolution log with structured entries per conflict
  - Fail action: Chief documents resolution for each unresolved conflict

- [ ] **Trustworthiness Rationale** — Resolution includes which framework is more trustworthy for THIS respondent and why
  - Threshold: Each resolution cites respondent-specific factors (data quality, response consistency, instrument fit) — not just generic framework hierarchy
  - Evidence: Per-conflict rationale referencing respondent data quality indicators
  - Fail action: Chief adds respondent-specific trustworthiness rationale

- [ ] **Confidence Adjustment** — Confidence adjusted downward for layers with unresolved conflicts
  - Threshold: Every layer with >= 1 unresolved or partially resolved conflict has confidence score reduced by >= 0.05 from baseline; adjustment documented with pre/post values
  - Evidence: Confidence map showing pre- and post-adjustment scores for affected layers
  - Fail action: Chief recalculates confidence scores for conflicted layers

- [ ] **Zero High-Severity Unresolved** — Zero high-severity (S3/S4) conflicts left unresolved
  - Threshold: 0 conflicts classified S3 (high impact) or S4 (critical impact) without full resolution
  - Evidence: Severity classification per conflict; filter for S3/S4; verify all resolved
  - Fail action: Chief resolves all S3/S4 conflicts with specialist agent consultation before proceeding

- [ ] **Severity Classification** — All conflicts classified by severity
  - Threshold: Every conflict has severity label: S1 (low), S2 (medium), S3 (high), S4 (critical)
  - Evidence: Severity field populated per conflict in resolution log
  - Fail action: Chief classifies unclassified conflicts

- [ ] **Specialist Consultation** — Chief consulted relevant specialist agents before deciding on direct contradictions
  - Threshold: Each S3/S4 conflict and each "direct contradiction" resolution references input from >= 1 specialist agent
  - Evidence: Consultation log entries with agent name and input summary
  - Fail action: Chief consults specialists and documents their input

- [ ] **Data Integrity Preserved** — Resolutions did not distort original framework data
  - Threshold: 0 cases where original scores or findings were altered; resolutions are interpretive, not data-modifying
  - Evidence: Original data preserved alongside resolution narrative
  - Fail action: Chief reverts any data modifications and re-resolves interpretively

- [ ] **Resolution Communicated** — Decision communicated to all impacted agents
  - Threshold: Each resolution has notification log entry per affected agent
  - Evidence: Notification records with agent names
  - Fail action: Chief notifies all affected agents

## Criterios Desejaveis
- [ ] Recurring conflict patterns across sessions identified
- [ ] Resolutions include cross-reference with behavioral evidence
- [ ] Process adjustment suggestions to prevent similar conflicts documented

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados; no S3/S4 unresolved
- **FAIL**: <50% criterios OR any S3/S4 unresolved -> rework obrigatorio

## Acao se Falhar
1. Chief reopens conflict analysis with specialist agents
2. Chief documents each contradiction with full resolution structure
3. Chief recalculates confidence for affected layers
4. Re-submit for checklist re-evaluation
**Bloqueio**: Synthesis cannot proceed with any S3/S4 conflict unresolved.

## Agente Responsavel
human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
