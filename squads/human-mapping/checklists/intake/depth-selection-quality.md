---
type: checklist
level: layer
layer: intake
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Seleção de Profundidade

## Propósito
Garantir que o nível de profundidade do mapeamento foi selecionado de forma adequada e justificada com base no objetivo e contexto do respondente.

## Critérios
- [ ] Nível de profundidade foi explicitamente selecionado — Evidência: `campo profundidade definido (essencial/padrão/avançado/completo)`
- [ ] Seleção foi justificada com base no objetivo declarado — Evidência: `campo justificativa_profundidade preenchido`
- [ ] Tempo disponível do respondente é compatível com a profundidade — Evidência: `campo tempo_disponivel >= tempo_estimado_profundidade`
- [ ] Complexidade do objetivo justifica a profundidade escolhida — Evidência: `análise de complexidade registrada`
- [ ] Respondente compreende o que cada nível de profundidade entrega — Evidência: `explicação dos níveis foi apresentada`
- [ ] Profundidade não foi inflada sem necessidade real — Evidência: `análise de adequação = aprovada`
- [ ] Profundidade não foi reduzida a ponto de comprometer o objetivo — Evidência: `flag cobertura_minima = true`
- [ ] Instrumentos necessários para a profundidade selecionada estão disponíveis — Evidência: `validação de instrumentos = OK`
- [ ] Respondente confirmou a profundidade selecionada — Evidência: `confirmação registrada`
- [ ] Estimativa de duração da sessão foi atualizada conforme profundidade — Evidência: `campo duracao_estimada atualizado`
- [ ] Regras de escalonamento de profundidade foram comunicadas — Evidência: `mensagem de escalonamento enviada`

## Ação se Falhar
Recalcular a profundidade adequada com base nos critérios disponíveis. Apresentar recomendação ao respondente com justificativa. Se houver conflito entre tempo disponível e profundidade necessária, negociar prioridades antes de prosseguir.

## Agente Responsável
intake-agent
