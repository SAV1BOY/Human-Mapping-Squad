---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/templates/operational/session-log-template.md
---
# Checklist: Chief Session Oversight Quality

## Proposito
Verificar que o Chief manteve supervisao ativa durante toda a sessao, com todos os stages completos, confidence map preenchido e contradiction audit executado.

## Criterios Obrigatorios

- [ ] **Pipeline Completion** — All pipeline stages completed or explicitly skipped with justification
  - Threshold: Session completion >= 80% of planned layers; each skipped stage has >= 2 sentence justification in session log
  - Evidence: Session log showing stage-by-stage status (completed/skipped + justification)
  - Fail action: Chief documents missing justifications; incomplete stages are either completed or formally justified

- [ ] **Confidence Map Complete** — Confidence map has score for every completed layer
  - Threshold: 0 completed layers without a confidence score; each score in range [0.0, 1.0]
  - Evidence: Confidence map artifact with per-layer scores; verify count matches completed layers
  - Fail action: Chief assigns confidence scores to unscored layers before proceeding

- [ ] **Contradiction Audit Executed** — Contradiction audit was executed (not skipped)
  - Threshold: Audit log exists with timestamp, auditor name, and findings (even if "no contradictions found")
  - Evidence: Contradiction audit artifact with execution metadata
  - Fail action: Chief triggers contradiction audit before approving any output

- [ ] **Chief Sign-Off** — Chief reviewed and signed off on final synthesis
  - Threshold: Sign-off record with Chief name, date, and explicit approval/conditional/rejection status
  - Evidence: Sign-off field in session log or synthesis document
  - Fail action: Chief reviews and records sign-off decision

- [ ] **Agent Progress Verification** — Chief verified progress of each agent involved
  - Threshold: Each agent's output has a quality check recorded by Chief; 0 agents whose output was accepted without review
  - Evidence: Per-agent review log entries in session log
  - Fail action: Chief reviews unverified agent outputs

- [ ] **Data Quality Validation** — Chief validated input data quality before processing
  - Threshold: Input data quality check recorded before pipeline execution began; references `intake/intake-quality.md`
  - Evidence: Pre-processing validation entry in session log with pass/fail status
  - Fail action: Chief performs retroactive input validation and documents findings

- [ ] **Decision Log Complete** — Chief's decision log is available and covers all major decisions
  - Threshold: >= 1 decision log entry per pipeline stage; each entry includes: decision, rationale, timestamp
  - Evidence: Decision log artifact with structured entries
  - Fail action: Chief reconstructs decision log from session artifacts

- [ ] **No Gate Bypass** — No quality gate was bypassed or ignored
  - Threshold: Field "gates_bypassed" empty in session log; if not empty = automatic FAIL
  - Evidence: Session log gates_bypassed field
  - Fail action: Chief re-executes bypassed gates; session cannot proceed until all gates pass

## Criterios Desejaveis
- [ ] Chief provided proactive feedback to agents (>= 1 feedback per agent)
- [ ] Chief identified risks early and took preventive actions
- [ ] Chief documented lessons learned for future sessions
- [ ] Chief assessed workload distribution and rebalanced when necessary

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> rework obrigatorio

## Acao se Falhar
1. Chief reviews session log and identifies specific oversight gaps
2. Chief completes missing reviews, confidence scores, and sign-offs
3. If gate was bypassed: repeat the affected layer with reinforced supervision
4. If failures are recurrent (>= 2 sessions): escalate for squad process review
**Bloqueio**: Session output cannot be delivered without Chief sign-off.

## Agente Responsavel
human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
