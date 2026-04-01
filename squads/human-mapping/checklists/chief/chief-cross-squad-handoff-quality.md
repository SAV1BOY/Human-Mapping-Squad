---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/templates/operational/cross-squad-handoff-template.md
  - data/registries/cross-squad-deliveries.yaml
---
# Checklist: Chief Cross-Squad Handoff Quality

## Proposito
Garantir que dados transferidos para outros squads estao formatados por template, com confidence documentada, limitacoes explicitas, contexto para o receptor e registro no sistema de entregas.

## Criterios Obrigatorios

- [ ] **Template Compliance** — Data formatted per `templates/operational/cross-squad-handoff-template.md`
  - Threshold: All mandatory fields in the handoff template populated; 0 missing fields
  - Evidence: Field-by-field comparison of handoff document against template; list any missing fields
  - Fail action: Chief completes missing fields or returns to originating agent

- [ ] **Confidence Scores Included** — Every transferred insight has a confidence score
  - Threshold: 0 insights without confidence score; insights with confidence < 0.50 explicitly marked as "hypothesis" or "preliminary indication"
  - Evidence: Confidence score present per insight; low-confidence items flagged with appropriate label
  - Fail action: Chief adds confidence scores to unscored insights

- [ ] **Limitations Explicitly Stated** — Limitations of the data are documented
  - Threshold: Limitations section present with >= 3 specific limitations (e.g., instrument type, sample context, data age, unresolved contradictions)
  - Evidence: Limitations section in handoff document with concrete items
  - Fail action: Chief writes limitations section before delivery

- [ ] **Receiving Squad Context Explained** — Context for the receiving squad is provided
  - Threshold: Handoff includes all four: (1) original assessment objective, (2) "how to use" guidance, (3) "how NOT to use" warnings, (4) scope of transfer (which layers/dimensions included and excluded)
  - Evidence: Context section in handoff with all four elements present
  - Fail action: Chief adds missing context elements

- [ ] **Registry Entry Created** — Delivery registered in `data/registries/cross-squad-deliveries.yaml`
  - Threshold: Registry entry exists with: date, sending squad, receiving squad, respondent ID (anonymized), scope, confidence range, Chief approval status
  - Evidence: Registry file entry matching this handoff
  - Fail action: Chief creates registry entry before delivery

- [ ] **Privacy Authorization Obtained** — Respondent authorized data sharing with the receiving squad
  - Threshold: Authorization record exists with respondent consent, date, and scope of permitted sharing
  - Evidence: Authorization artifact with respondent identifier, date, and scope
  - Fail action: Chief obtains authorization or BLOCKS the handoff — this is an absolute blocker

- [ ] **Minimum Necessary Principle** — Detail level appropriate for receiving squad's purpose
  - Threshold: Only interpreted insights transferred (not raw assessment data); detail level matched to receiving squad type per squad-specific table below
  - Evidence: Review of transferred data against receiving squad needs
  - Fail action: Chief reduces detail level to minimum necessary

- [ ] **Actionable Recommendations Included** — Handoff includes recommendations tailored to the receiving squad
  - Threshold: >= 2 actionable recommendations for the receiving squad's domain; clear contact protocol for follow-up questions documented
  - Evidence: Recommendations section with squad-specific actions and contact protocol
  - Fail action: Chief adds tailored recommendations and contact protocol

## Squad-Specific Detail Levels

| Squad Receptor | Focus | Detail Level |
|---|---|---|
| Strategy/Product | Work style, communication preferences, leverage points | Low psychometric detail |
| People/HR | Development, coaching, cultural fit | High psychometric detail permitted |
| Leadership/Management | Leadership style, derailer risks, team management | Medium psychometric detail |
| External (outside org) | Aggregated insights only, max anonymization, additional sponsor approval required | Minimum detail |

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios OR privacy authorization missing -> handoff blocked

## Acao se Falhar
1. Chief identifies specific failing criteria and returns handoff for correction
2. Originating agent corrects format, adds confidence scores, writes limitations
3. Chief verifies registry entry and privacy authorization
4. Re-submit for checklist re-evaluation
**Bloqueio**: Handoff cannot be sent without Chief PASS. Privacy failures are absolute blockers — no conditional pass allowed.

## Agente Responsavel
human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
