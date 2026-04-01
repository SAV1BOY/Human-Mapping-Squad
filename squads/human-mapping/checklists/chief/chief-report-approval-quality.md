---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/checklists/synthesis/barnum-prevention-quality.md
  - squads/human-mapping/voice/language-guides/feedback-delivery-language.md
  - squads/human-mapping/frameworks/confidence-scoring-model.md
---
# Checklist: Chief Report Approval Quality

## Proposito
Arvore de decisao para aprovacao do relatorio final. O Chief aprova somente se Barnum test passou, confidence map esta completo, resumo e conciso e todas as recomendacoes sao acionaveis.

## Criterios Obrigatorios

- [ ] **Barnum Test Passed** — Barnum test passed per `synthesis/barnum-prevention-quality.md`
  - Threshold: barnum-prevention-quality checklist status = PASS; < 3 Barnum statements in entire report
  - Evidence: Reference to completed barnum-prevention-quality checklist with PASS result and date
  - Fail action: Return to respondent-quality-auditor for anti-Barnum rework; do NOT proceed to other gates

- [ ] **Confidence Map Attached** — Confidence map attached with per-layer scores
  - Threshold: Confidence map present as artifact; every completed layer has a score in [0.0, 1.0]; 0 layers missing
  - Evidence: Confidence map artifact attached to report with per-layer and global scores
  - Fail action: Chief generates confidence map before approval

- [ ] **Executive Summary Length** — Executive summary <= 1 page
  - Threshold: Executive summary word count <= 500 words
  - Evidence: Word count of executive summary section
  - Fail action: report-writer condenses executive summary to <= 500 words

- [ ] **Actionable Recommendations** — All recommendations are actionable (WHO does WHAT by WHEN)
  - Threshold: Every recommendation includes: actor (who), action (what), timeframe (when); 0 recommendations with only abstract advice
  - Evidence: Scan each recommendation for WHO/WHAT/WHEN structure
  - Fail action: report-writer rewrites non-actionable recommendations with concrete structure

- [ ] **Tone Compliance** — Report tone checked against `voice/language-guides/feedback-delivery-language.md`
  - Threshold: Tone is constructive and non-labeling; 0 instances of judgmental or diagnostic language; consistent register throughout
  - Evidence: Tone review log referencing specific language guide sections
  - Fail action: report-writer adjusts tone per language guide

- [ ] **Section Coherence Verified** — Chief verified coherence between all report sections
  - Threshold: 0 inter-section contradictions; narrative flows logically from traits through development
  - Evidence: Coherence review notes from Chief
  - Fail action: report-writer resolves identified incoherences

- [ ] **Evidence-Based Recommendations** — All recommendations grounded in profile evidence
  - Threshold: Every recommendation cites >= 1 specific profile finding with framework and score
  - Evidence: Recommendation-to-evidence trace table
  - Fail action: report-writer adds evidence citations or removes unsupported recommendations

- [ ] **Formal Approval Record** — Chief approval formally recorded
  - Threshold: Approval record includes: Chief name, date, decision status, conditions (if any)
  - Evidence: Approval field in report or session log
  - Fail action: Chief records formal approval decision

## Decision Tree

| Global Confidence | Decision |
|---|---|
| >= 0.7 | Approve — report released for delivery |
| 0.5 - 0.69 | Approve with caveats — caveats documented in report |
| < 0.5 | Rework required — return to synthesis-architect |

## Criterios Desejaveis
- [ ] Chief requested cross-review by another agent before approval
- [ ] Chief verified report language for clarity and accessibility
- [ ] Chief compared report quality against previous session standards
- [ ] Chief included context notes for the final reader

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold AND global confidence >= 0.5
- **CONDITIONAL PASS**: >=80% criterios, global confidence 0.5-0.69, caveats documented
- **FAIL**: <50% criterios OR global confidence < 0.5 -> rework obrigatorio

## Acao se Falhar
1. Chief returns report to report-writer with annotated failure points
2. report-writer corrects Barnum items, adds evidence, rewrites non-actionable recommendations
3. report-writer re-submits; Chief re-evaluates from first failing gate
**Bloqueio**: Report cannot be delivered without Chief PASS or CONDITIONAL PASS. Maximum 3 revision cycles; after 3 failures on same gate, escalate for process review.

## Agente Responsavel
human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
