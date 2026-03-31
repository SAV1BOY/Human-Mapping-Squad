---
type: checklist
level: layer
layer: calibration
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Consistência das Respostas

## Propósito
Garantir que as respostas do respondente são internamente consistentes e que inconsistências foram identificadas e tratadas.

## Critérios
- [ ] Respostas a itens paralelos (mesmo construto) foram comparadas — Evidência: `correlação entre itens paralelos calculada`
- [ ] Desvio entre itens paralelos está dentro do limite aceitável — Evidência: `desvio <= threshold definido`
- [ ] Respostas a itens reversos são coerentes com itens diretos — Evidência: `análise de itens reversos = consistente`
- [ ] Padrão de respostas não é aleatório (ex: todas no centro, todas no extremo) — Evidência: `análise de padrão de resposta = não aleatório`
- [ ] Narrativas qualitativas são coerentes com respostas quantitativas — Evidência: `análise quali-quanti = consistente`
- [ ] Respostas ao longo do tempo não apresentam drift sistemático — Evidência: `análise temporal de drift = dentro do limite`
- [ ] Inconsistências detectadas foram registradas com grau de severidade — Evidência: `log de inconsistências atualizado`
- [ ] Respondente foi consultado sobre inconsistências relevantes — Evidência: `perguntas de clarificação enviadas`
- [ ] Score de consistência geral foi calculado — Evidência: `campo score_consistencia preenchido`
- [ ] Decisão de prosseguir ou recalibrar foi documentada — Evidência: `campo decisao_calibracao definido`
- [ ] Inconsistências menores foram toleradas com ajuste de confiança — Evidência: `ajuste de confiança registrado`

## Ação se Falhar
Apresentar as inconsistências ao respondente e solicitar clarificação. Se a inconsistência persistir, reduzir o nível de confiança dos construtos afetados. Em casos graves, considerar reiniciar o bloco de perguntas afetado.

## Agente Responsável
calibration-agent
