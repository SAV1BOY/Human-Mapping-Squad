---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
---
# Checklist: Chief Methodology Update Quality

## Proposito
Garantir que toda atualizacao metodologica e aprovada com evidencia de >= 3 sessoes, impacto em scoring avaliado, validacao retroativa executada e plano de rollback definido.

## Criterios Obrigatorios

- [ ] **Evidence from Sessions** — Change proposal includes evidence from >= 3 sessions showing the issue
  - Threshold: >= 3 distinct session IDs cited with specific examples of the problem the change addresses
  - Evidence: Session reference list with problem description per session (session ID, date, problem observed)
  - Fail action: Proposer collects additional session evidence before resubmitting

- [ ] **Scoring Impact Assessment** — Impact assessment on scoring formulas documented
  - Threshold: Document specifies: which scoring formulas change, which pipeline stages are affected, estimated number of future sessions impacted
  - Evidence: Impact assessment document with formula-level detail and affected file paths
  - Fail action: Proposer writes impact assessment before Chief review

- [ ] **Rollback Plan Defined** — Rollback plan exists and is executable
  - Threshold: Plan includes: original files preserved/versioned, rollback steps (max 5), executable in < 30 minutes, trigger criteria defined (e.g., "confidence drops > 0.10 in 3+ sessions")
  - Evidence: Rollback plan document with versioned file locations and quantitative trigger criteria
  - Fail action: Proposer creates rollback plan before approval

- [ ] **Retroactive Validation** — Change applied retroactively to 3 past sessions, results compared
  - Threshold: >= 3 past sessions re-analyzed with the proposed change; before/after comparison shows measurable improvement (higher confidence, better accuracy, or more completeness)
  - Evidence: Comparison table: session ID -> metric before -> metric after -> delta -> improvement (yes/no)
  - Fail action: Proposer runs retroactive validation and documents results

- [ ] **No Methodology Contradiction** — Change does not contradict existing methods without explicit supersession
  - Threshold: Compatibility check completed; new method compatible with current pipeline OR explicit supersession declaration
  - Evidence: Compatibility check document or supersession declaration with rationale
  - Fail action: Proposer resolves contradictions or documents what is being superseded

- [ ] **Peer Review Completed** — At least one agent besides the proposer reviewed and agreed
  - Threshold: >= 1 reviewer for patterns; >= 2 for rubric changes; all agents for pipeline changes (see table below)
  - Evidence: Reviewer sign-off entries with name, date, and approval
  - Fail action: Proposer obtains required reviews

- [ ] **Documentation Updated Simultaneously** — All associated docs updated in the same changeset
  - Threshold: Every affected rubric, template, and script updated; changelog entry added with date and description
  - Evidence: List of updated file paths; changelog entry
  - Fail action: Proposer updates all associated documentation before implementation

- [ ] **Affected Agents Notified** — All agents whose workflow is impacted have been notified
  - Threshold: Notification log exists with agent names, notification date, and confirmation of receipt
  - Evidence: Notification log artifact
  - Fail action: Chief ensures all agents are notified before implementation

## Niveis de Aprovacao

| Tipo de Mudanca | Revisores | Casos Teste Minimos |
|---|---|---|
| Template error correction | Chief | >= 1 case |
| New pattern in library | Chief + 1 reviewer | >= 2 real cases |
| Scoring rubric change | Chief + 2 reviewers | >= 3 real cases |
| New framework integration | Chief + full validation | >= 5 real cases + research |
| Analysis script change | Chief + automated test | >= 3 cases + before/after comparison |
| Structural pipeline change | Chief + all agents | >= 5 cases + 30-day test period |

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados com deadline para resolucao
- **FAIL**: <50% criterios -> proposal returned for more evidence

## Acao se Falhar
1. Chief returns proposal to proposer with specific failing criteria listed
2. Proposer collects additional evidence, runs retroactive validation, creates rollback plan
3. Proposer re-submits with complete documentation
4. If rejected 2x: escalate for collective squad review
**Bloqueio**: No methodology change is implemented without Chief PASS.

## Monitoramento Pos-Implementacao
- Impact review scheduled for 30 days after implementation
- Monitoring metrics defined at approval time (>= 2 metrics)
- Designated monitor assigned by name
- Rollback triggered automatically if trigger criteria are met

## Agente Responsavel
human-mapping-chief — Arquivo: `agents/human-mapping-chief.md`
