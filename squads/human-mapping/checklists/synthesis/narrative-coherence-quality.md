---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
gate: mandatory
related_files:
  - squads/human-mapping/frameworks/confidence-scoring-model.md
  - squads/human-mapping/voice/language-guides/feedback-delivery-language.md
---
# Checklist: Narrative Coherence Quality

## Proposito
Garantir que o relatorio apresenta UMA pessoa coerente, sem contradicoes ocultas, com todas as afirmacoes rastreadas a evidencias especificas do perfil.

## Criterios Obrigatorios

- [ ] **Logical Sequence Check** — Read trait -> type -> motivation -> strength sequence: no logical contradictions
  - Threshold: 0 contradictions between consecutive sections; each section references >= 1 element from the previous section
  - Evidence: Sequential read-through audit documenting each cross-section reference and flagging any contradictions found
  - Fail action: report-writer resolves contradictions or adds reconciliation text

- [ ] **Contradiction Transparency** — All unresolved contradictions explicitly flagged (not hidden)
  - Threshold: 0 contradictions from the audit log that do not appear in the final report; each flagged contradiction includes: Framework A vs Framework B, nature of conflict, resolution
  - Evidence: Cross-reference contradiction audit log entries against report content
  - Fail action: report-writer adds explicit contradiction discussion for each missing entry

- [ ] **Recommendation Traceability** — Development recommendations trace back to specific profile findings
  - Threshold: Every recommendation cites >= 1 specific finding with score/percentile and framework
  - Evidence: Trace table: recommendation -> profile finding -> framework + score
  - Fail action: report-writer adds evidence chain or removes ungrounded recommendation

- [ ] **Zero Unattributed Claims** — No personality or behavioral claim without source
  - Threshold: 0 claims in the report without framework attribution and supporting data
  - Evidence: Full report scan; flag each claim and verify attribution exists
  - Fail action: report-writer attributes each claim or removes it

- [ ] **Person Unity** — The report describes ONE individual, not a collage of profiles
  - Threshold: Identifiable thread connecting >= 3 sections; executive summary captures the person in <= 5 sentences
  - Evidence: Executive summary present; thematic thread documented
  - Fail action: report-writer rewrites to establish unifying narrative thread

- [ ] **Consistent Tone** — Tone is consistent from start to finish
  - Threshold: No shift between technical and colloquial register; technical terms (Big Five, MBTI, Kolbe) always accompanied by plain-language explanation
  - Evidence: Sample 1 paragraph from beginning and 1 from end; verify same register
  - Fail action: report-writer normalizes tone throughout

- [ ] **Complete Dimension Coverage** — All assessed dimensions appear in the narrative
  - Threshold: Delta between assessed dimensions and mentioned dimensions = 0; dimensions with extreme scores (>= 0.85 or <= 0.15) highlighted with emphasis
  - Evidence: Dimension checklist: assessed vs mentioned
  - Fail action: report-writer adds missing dimensions

## Criterios Desejaveis
- [ ] Examples and metaphors are consistent between sections
- [ ] Narrative reviewed to eliminate redundancies (0 unnecessary repetitions)
- [ ] Thematic thread explicitly named (e.g., "The profile of a cautious strategist")

## Decisao
- **PASS**: Todos criterios obrigatorios atendem threshold
- **CONDITIONAL PASS**: >=80% criterios, gaps documentados
- **FAIL**: <50% criterios -> rework obrigatorio

## Acao se Falhar
1. report-writer receives annotated list of incoherence points with section numbers
2. report-writer resolves contradictions, adds attributions, establishes narrative thread
3. Re-submit for checklist re-evaluation
**Bloqueio**: Relatorio nao avanca para aprovacao do chief ate coerencia verificada.

## Agente Responsavel
report-writer — Arquivo: `agents/report-writer.md`
