---
type: checklist
level: layer
layer: calibration
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade do Threshold de Confiança

## Propósito
Garantir que o threshold mínimo de confiança foi atingido antes de prosseguir para a interpretação dos resultados.

## Critérios
- [ ] Threshold mínimo de confiança foi definido para a sessão — Evidência: `campo threshold_minimo configurado`
- [ ] Score de confiança global foi calculado — Evidência: `campo score_confianca_global preenchido`
- [ ] Score de confiança por construto foi calculado — Evidência: `scores por construto registrados`
- [ ] Nenhum construto crítico está abaixo do threshold — Evidência: `validação de threshold por construto = OK`
- [ ] Fatores que reduziram a confiança foram documentados — Evidência: `campo fatores_reducao preenchido`
- [ ] Consistência interna contribuiu positivamente para confiança — Evidência: `score_consistencia integrado ao cálculo`
- [ ] Ausência de fadiga excessiva contribuiu para confiança — Evidência: `score_fadiga integrado ao cálculo`
- [ ] Desejabilidade social dentro do aceitável contribuiu para confiança — Evidência: `score_desejabilidade integrado ao cálculo`
- [ ] Baseline de autoconhecimento foi fator no cálculo de confiança — Evidência: `score_autoconhecimento integrado`
- [ ] Decisão de prosseguir foi tomada com base nos scores — Evidência: `campo decisao_prosseguir documentado`
- [ ] Construtos abaixo do threshold foram sinalizados para cautela — Evidência: `flags de cautela aplicados`
- [ ] Relatório final incluirá bandas de confiança por construto — Evidência: `flag bandas_confianca = true`

## Ação se Falhar
Não prosseguir para interpretação de construtos que estejam abaixo do threshold mínimo. Oferecer ao respondente a opção de responder itens adicionais para elevar a confiança. Se o threshold global não for atingido, considerar encerrar a sessão com relatório parcial e recomendação de retomada futura.

## Agente Responsável
calibration-agent
