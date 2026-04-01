---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/reference/psychology/barnum-forer-effect.md
---
# Checklist: Barnum Prevention Quality

## Proposito
Garantir que o perfil e ESPECIFICO para esta pessoa. Se >50% da populacao concordaria com uma descricao, ela e generica demais e deve ser eliminada ou reescrita com dados concretos.

## Criterios Obrigatorios

- [ ] **Barnum Test (50% Rule)** — Apply Barnum Test: Could >50% of people agree with this description? If yes = FAIL
  - Threshold: < 3 Barnum statements in entire report; >= 90% of all statements pass the specificity test
  - Evidence: Full report scan using methodology from `reference/psychology/barnum-forer-effect.md`; count statements where >50% of population would agree; list each flagged statement
  - Fail action: respondent-quality-auditor rewrites each flagged statement with specific score + framework + behavior

- [ ] **Numeric Specificity** — Each personality descriptor includes specific score/percentile
  - Threshold: 0 personality descriptors without numeric score or percentile from a framework
  - Evidence: Scan all personality descriptors; verify each has format "[Framework] -> [Score/Percentile] -> [Behavioral manifestation]"
  - Fail action: respondent-quality-auditor adds scores to each descriptor

- [ ] **Contextual Predictions** — Each behavioral prediction includes context (when/where/under what conditions)
  - Threshold: 0 behavioral predictions without situational context
  - Evidence: List all predictions; verify each specifies triggering conditions (e.g., "Under deadline pressure" not just "sometimes")
  - Fail action: respondent-quality-auditor adds contextual conditions to each prediction

- [ ] **No Unquantified Hedging** — Zero uses of "sometimes/often/tends to" without quantification
  - Threshold: 0 occurrences of "sometimes", "often", "tends to", "can be", "may" without accompanying score, frequency, or condition
  - Evidence: Text search for hedge words; verify each occurrence has quantification
  - Fail action: respondent-quality-auditor replaces each hedge with specific data

- [ ] **Unique Combination Highlighted** — The intersection of 3+ dimensions that makes this person unique is explicitly described
  - Threshold: >= 1 paragraph describing the unique trait combination; >= 2 "negative differentiators" (what this person is NOT)
  - Evidence: Locate uniqueness paragraph; count negative differentiators
  - Fail action: respondent-quality-auditor writes uniqueness section

- [ ] **Genuine Difficult Feedback** — Report includes at least 1 genuinely challenging development area
  - Threshold: >= 1 feedback item that is not a disguised compliment; >= 2 concrete risks with manifestation scenarios
  - Evidence: Identify challenging feedback items; verify they reference specific scores and are not euphemistic
  - Fail action: respondent-quality-auditor adds direct, evidence-based challenging feedback

- [ ] **Anti-Barnum Review Executed** — Formal anti-Barnum review completed and logged
  - Threshold: Field "revisao_anti_barnum" has status "executada", date, and reviewer name
  - Evidence: Review log entry with timestamp and reviewer
  - Fail action: respondent-quality-auditor executes the review before proceeding

## Criterios Desejaveis
- [ ] Specific behavioral examples included for each major description
- [ ] Comparison with generic profiles to validate differentiation
- [ ] Specificity percentage >= 95%

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> rework obrigatorio

## Acao se Falhar
1. respondent-quality-auditor replaces EVERY generic phrase with description including score + framework + behavior
2. respondent-quality-auditor adds negative differentiators and challenging feedback
3. respondent-quality-auditor re-executes all Barnum tests
**Bloqueio**: Relatorio NAO pode ser aprovado pelo chief com qualquer falha Barnum. Esta e a gate mais critica de qualidade.

## Agente Responsavel
respondent-quality-auditor — Arquivo: `agents/respondent-quality-auditor.md`
