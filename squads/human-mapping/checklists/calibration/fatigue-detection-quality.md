---
type: checklist
level: layer
layer: calibration
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Detecção de Fadiga

## Propósito
Garantir que a fadiga do respondente não comprometeu a qualidade das respostas coletadas durante a sessão.

## Critérios
- [ ] Tempo de resposta por item foi monitorado ao longo da sessão — Evidência: `série temporal de tempos de resposta registrada`
- [ ] Aumento significativo no tempo de resposta foi detectado — Evidência: `análise de tendência temporal calculada`
- [ ] Redução na variabilidade das respostas ao longo do tempo foi verificada — Evidência: `análise de variabilidade = sem achatamento`
- [ ] Padrão de respostas centrais crescentes foi verificado — Evidência: `análise de tendência central = sem viés crescente`
- [ ] Respostas dos últimos 20% dos itens foram comparadas com os primeiros 20% — Evidência: `comparação início vs. fim realizada`
- [ ] Número total de itens respondidos não excedeu limite recomendado — Evidência: `qtd_itens <= limite_maximo`
- [ ] Pausas foram oferecidas em intervalos adequados — Evidência: `log de pausas oferecidas registrado`
- [ ] Respondente utilizou pausas quando necessário — Evidência: `log de pausas realizadas registrado`
- [ ] Sinais verbais ou textuais de cansaço foram monitorados — Evidência: `análise de linguagem do respondente`
- [ ] Score de fadiga foi calculado — Evidência: `campo score_fadiga preenchido`
- [ ] Decisão de pausar, encurtar ou encerrar foi tomada quando necessário — Evidência: `campo decisao_fadiga documentado`
- [ ] Itens respondidos sob fadiga foram marcados com flag de cautela — Evidência: `flags de cautela aplicados`

## Ação se Falhar
Pausar a sessão e oferecer retomada posterior. Se respostas foram coletadas sob fadiga significativa, marcar esses itens com flag de baixa confiança. Considerar readministrar os itens afetados em momento de maior disposição do respondente.

## Agente Responsável
calibration-agent
