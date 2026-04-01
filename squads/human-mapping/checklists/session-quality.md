---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/checklists/intake/intake-quality.md
  - squads/human-mapping/checklists/calibration/calibration-quality.md
  - squads/human-mapping/checklists/contradiction/contradiction-audit-quality.md
  - squads/human-mapping/checklists/synthesis/barnum-prevention-quality.md
  - squads/human-mapping/checklists/synthesis/narrative-coherence-quality.md
  - squads/human-mapping/checklists/chief/chief-report-approval-quality.md
---
# Checklist: Session Quality

## Proposito
Verificar que a sessao de mapeamento foi conduzida do inicio ao fim com todas as etapas cumpridas, thresholds numericos atingidos e integridade do resultado garantida.

## Criterios Obrigatorios

- [ ] **Intake Completed** — Intake realizado e registrado antes do inicio da sessao
  - Threshold: Intake record exists with timestamp, objective, context, and scope fields all populated
  - Evidence: Intake artifact with timestamp; ref: `intake/intake-quality.md` with PASS status
  - Fail action: Session must restart from intake

- [ ] **Calibration Approved** — Calibracao do respondente aprovada com confidence suficiente
  - Threshold: Calibration confidence >= 0.50; calibration status = "approved"; consistency score >= 0.60
  - Evidence: Calibration result artifact with numeric scores; ref: `calibration/calibration-quality.md`
  - Fail action: Respondent must be recalibrated before proceeding

- [ ] **All Layers Completed** — Todas as camadas definidas no escopo foram completadas
  - Threshold: Count of completed layers = count of planned layers; delta = 0
  - Evidence: Layer status list showing each layer as "completed" or "skipped with justification"
  - Fail action: Complete missing layers or provide >= 2 sentence justification for each exclusion

- [ ] **No Silent Layer Omission** — Nenhuma camada ignorada sem justificativa
  - Threshold: Field "camadas_incompletas" empty OR each incomplete layer has >= 2 sentence justification
  - Evidence: Session log completude field
  - Fail action: Provide justification or complete the layer

- [ ] **Contradiction Audit Completed** — Auditoria de contradicoes executada sobre os resultados
  - Threshold: Audit report exists with findings list (may be empty); >= 80% of contradictions resolved or classified as "valid tension"; 0 high-severity contradictions unresolved
  - Evidence: Contradiction audit artifact; ref: `contradiction/contradiction-audit-quality.md`
  - Fail action: Execute contradiction audit before generating report

- [ ] **Global Confidence >= 0.50** — Confianca media da sessao atinge limiar minimo
  - Threshold: Arithmetic mean of all layer confidence scores >= 0.50; no layer below 0.30 without "inconclusive" label
  - Evidence: Confidence map with per-layer and global scores; numeric values documented
  - Fail action: Investigate low-confidence layers; consider re-evaluation for layers < 0.30

- [ ] **Per-Layer Confidence Documented** — Confianca por camada registrada
  - Threshold: Every completed layer has a confidence score in [0.0, 1.0] in the confidence map
  - Evidence: Confidence map artifact with complete per-layer scores
  - Fail action: Chief assigns confidence scores to unscored layers

- [ ] **Barnum Test Passed** — Teste Barnum executado e aprovado
  - Threshold: barnum-prevention-quality checklist status = PASS
  - Evidence: Reference to completed `synthesis/barnum-prevention-quality.md` checklist
  - Fail action: Return to respondent-quality-auditor for anti-Barnum rework

- [ ] **Narrative Coherence Verified** — Coerencia narrativa verificada
  - Threshold: narrative-coherence-quality checklist status = PASS
  - Evidence: Reference to completed `synthesis/narrative-coherence-quality.md` checklist
  - Fail action: Return to report-writer for coherence corrections

- [ ] **Report Approved by Chief** — Relatorio aprovado pelo Chief
  - Threshold: chief-report-approval-quality checklist status = PASS or CONDITIONAL PASS; approval record with Chief name and date
  - Evidence: Reference to completed `chief/chief-report-approval-quality.md` checklist
  - Fail action: Submit report to Chief for approval review

- [ ] **Session Duration Within Range** — Tempo total da sessao dentro do intervalo aceitavel
  - Threshold: Duration between 45 and 180 minutes; start and end timestamps recorded
  - Evidence: Timestamps of session start and end; calculated duration
  - Fail action: Document justification for out-of-range duration

- [ ] **Raw Data Preserved** — Dados brutos preservados para auditoria futura
  - Threshold: All raw artifacts archived with documented path/reference
  - Evidence: Archive location documented; artifacts accessible
  - Fail action: Reconstruct from available artifacts; document any data gaps

## Criterios Desejaveis
- [ ] Respondent confirmed comfort during session (qualitative feedback collected)
- [ ] No severe fatigue indicators in final responses (consistency maintained)
- [ ] Session conducted without significant interruptions (> 15min)
- [ ] Peer review of report completed
- [ ] Respondent qualitative feedback collected at session end

## Metricas Resumo da Sessao

| Metrica | Threshold Minimo | Valor |
|---|---|---|
| Global confidence mean | >= 0.50 | [value] |
| Contradictions resolved | >= 80% | [value] |
| Layers complete | 100% (or justified) | [value] |
| Barnum test | PASS | [status] |
| Session duration | 45-180 min | [value] |
| Calibration confidence | >= 0.50 | [value] |

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> session rework required

## Acao se Falhar
- Intake missing: restart from intake
- Calibration failed: recalibrate before proceeding
- Layers incomplete: complete or justify exclusion
- Contradictions not audited: execute audit before report
- Confidence < 0.50: investigate weak layers; consider re-evaluation
- Raw data not preserved: reconstruct from available artifacts
- Barnum failed: return to respondent-quality-auditor
- Chief approval missing: submit for Chief review

## Agente Responsavel
- **Principal**: human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
- **Suporte**: calibration-agent, contradiction-auditor, synthesis-architect
- **Aprovador**: human-mapping-chief
