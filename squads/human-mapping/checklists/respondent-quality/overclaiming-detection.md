---
type: checklist
level: layer
layer: respondent-quality
squad: human-mapping
version: "2.0.0"
---
# Checklist: Detecção de Overclaiming

## Propósito
Detectar quando o respondente exagera qualidades positivas ou competências, comprometendo a validade do mapeamento.

## Critérios
- [ ] Frequência de autoavaliações no extremo positivo foi calculada — Evidência: `campo freq_extremo_positivo preenchido`
- [ ] Proporção de pontos fortes vs. fracos relatados foi analisada — Evidência: `razão fortes/fracos calculada`
- [ ] Respostas foram comparadas com distribuição esperada da população — Evidência: `análise de desvio populacional realizada`
- [ ] Itens âncora de overclaiming foram incluídos e analisados — Evidência: `itens âncora verificados`
- [ ] Linguagem superlativa excessiva foi detectada — Evidência: `análise linguística de superlativos`
- [ ] Ausência de nuances nas respostas positivas foi sinalizada — Evidência: `flag ausencia_nuances verificado`
- [ ] Consistência entre autoavaliação e exemplos concretos foi verificada — Evidência: `análise de consistência autoavaliação-exemplos`
- [ ] Contexto motivacional do respondente foi considerado — Evidência: `campo motivacao_sessao avaliado`
- [ ] Score de risco de overclaiming foi calculado — Evidência: `campo score_overclaiming preenchido`
- [ ] Impacto do overclaiming nos resultados foi estimado — Evidência: `campo impacto_overclaiming definido`
- [ ] Estratégias de mitigação foram aplicadas — Evidência: `log de mitigação de overclaiming`
- [ ] Relatório final inclui nota sobre nível de overclaiming detectado — Evidência: `nota de overclaiming no relatório`

## Ação se Falhar
Aplicar correção estatística nos construtos afetados. Inserir perguntas situacionais adicionais que exigem exemplos concretos. Incluir aviso no relatório de que as autoavaliações podem estar infladas e recomendar validação com feedback 360.

## Agente Responsável
respondent-quality-agent
