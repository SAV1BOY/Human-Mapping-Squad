---
type: checklist
level: layer
layer: traits
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Confiança nos Traços

## Propósito
Garantir que o nível de confiança nos traços medidos atinge o threshold mínimo definido para a sessão.

## Critérios
- [ ] Threshold mínimo de confiança por traço foi definido — Evidência: `campo threshold_tracos configurado`
- [ ] Score de confiança foi calculado para cada traço — Evidência: `scores de confiança por traço registrados`
- [ ] Número de itens por traço é suficiente para o threshold — Evidência: `qtd_itens >= minimo_por_traco`
- [ ] Consistência interna por traço (alpha de Cronbach ou equivalente) foi calculada — Evidência: `alpha por traço calculado`
- [ ] Traços com confiança abaixo do threshold foram listados — Evidência: `lista de traços abaixo do threshold`
- [ ] Fontes de incerteza por traço foram documentadas — Evidência: `campo fontes_incerteza preenchido por traço`
- [ ] Intervalo de confiança por traço foi estimado — Evidência: `intervalos de confiança calculados`
- [ ] Traços críticos para o objetivo da sessão atingiram confiança alta — Evidência: `validação de traços críticos = OK`
- [ ] Correlação entre múltiplas fontes de evidência foi verificada — Evidência: `análise de convergência multi-fonte`
- [ ] Decisão sobre traços insuficientes foi documentada — Evidência: `campo decisao_tracos_insuficientes preenchido`
- [ ] Bandas de confiança serão apresentadas no relatório — Evidência: `flag bandas_confianca_tracos = true`
- [ ] Score global de confiança nos traços foi calculado — Evidência: `campo score_confianca_tracos_global preenchido`

## Ação se Falhar
Administrar itens adicionais para traços abaixo do threshold. Se não for possível elevar a confiança, classificar o traço como "estimativa provisória" no relatório e recomendar avaliação complementar. Nunca apresentar um traço com baixa confiança como resultado definitivo.

## Agente Responsável
traits-agent
