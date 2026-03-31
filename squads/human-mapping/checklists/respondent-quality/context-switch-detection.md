---
type: checklist
level: layer
layer: respondent-quality
squad: human-mapping
version: "2.0.0"
---
# Checklist: Detecção de Mudança Involuntária de Contexto

## Propósito
Detectar quando o respondente muda involuntariamente o contexto de referência nas respostas, comprometendo a comparabilidade dos dados.

## Critérios
- [ ] Contexto de referência foi definido no início da sessão — Evidência: `campo contexto_referencia definido (trabalho/vida pessoal/geral)`
- [ ] Respostas foram monitoradas para mudanças de contexto ao longo da sessão — Evidência: `análise de contexto por resposta realizada`
- [ ] Mudanças de "eu no trabalho" para "eu em casa" foram detectadas — Evidência: `flag mudanca_trabalho_casa registrado`
- [ ] Mudanças de papel (líder vs. liderado vs. par) foram identificadas — Evidência: `flag mudanca_papel registrado`
- [ ] Mudanças temporais (presente vs. passado vs. aspiracional) foram flagradas — Evidência: `flag mudanca_temporal registrado`
- [ ] Frequência de mudanças de contexto foi calculada — Evidência: `campo freq_mudanca_contexto preenchido`
- [ ] Respondente foi alertado quando mudança de contexto foi detectada — Evidência: `alerta de contexto enviado`
- [ ] Respondente reconfirmou o contexto correto após alerta — Evidência: `reconfirmação registrada`
- [ ] Respostas afetadas por mudança de contexto foram marcadas — Evidência: `flags de mudança de contexto aplicados`
- [ ] Score de estabilidade de contexto foi calculado — Evidência: `campo score_estabilidade_contexto preenchido`
- [ ] Impacto das mudanças na validade dos construtos foi estimado — Evidência: `análise de impacto por construto`
- [ ] Relatório final diferencia resultados por contexto quando relevante — Evidência: `seção multi-contexto no relatório`

## Ação se Falhar
Pausar a coleta e reestabelecer o contexto de referência com o respondente. Reclassificar respostas por contexto quando possível. Se mudanças forem frequentes, considerar criar perfis separados por contexto. Incluir nota sobre instabilidade de contexto no relatório final.

## Agente Responsável
respondent-quality-agent
