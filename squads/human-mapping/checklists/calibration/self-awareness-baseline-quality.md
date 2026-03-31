---
type: checklist
level: layer
layer: calibration
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade do Baseline de Autoconhecimento

## Propósito
Medir o nível de autoconhecimento base do respondente para calibrar a interpretação das respostas autorrelatadas.

## Critérios
- [ ] Perguntas de meta-cognição foram aplicadas no início da sessão — Evidência: `itens de meta-cognição respondidos`
- [ ] Respondente avaliou sua própria capacidade de autoavaliação — Evidência: `campo autoavaliacao_capacidade preenchido`
- [ ] Experiência prévia com feedback estruturado foi registrada — Evidência: `campo experiencia_feedback preenchido`
- [ ] Histórico de participação em processos de desenvolvimento foi coletado — Evidência: `campo historico_desenvolvimento preenchido`
- [ ] Capacidade de distinguir entre comportamento e identidade foi testada — Evidência: `teste de distinção comportamento-identidade aplicado`
- [ ] Nível de vocabulário emocional do respondente foi avaliado — Evidência: `campo vocabulario_emocional classificado`
- [ ] Respondente demonstrou capacidade de identificar contradições em si — Evidência: `teste de auto-contradição aplicado`
- [ ] Score de autoconhecimento base foi calculado — Evidência: `campo score_autoconhecimento preenchido`
- [ ] Score foi categorizado (baixo/moderado/alto) — Evidência: `campo categoria_autoconhecimento definido`
- [ ] Estratégia de interpretação foi ajustada conforme baseline — Evidência: `campo estrategia_interpretacao atualizado`
- [ ] Respondente foi informado sobre como o baseline será usado — Evidência: `mensagem explicativa enviada`
- [ ] Baseline será comparado com resultados finais para validação — Evidência: `flag comparacao_final = true`

## Ação se Falhar
Se o baseline de autoconhecimento for baixo, aumentar o peso de evidências comportamentais e situacionais em relação a autoavaliações diretas. Registrar o baseline no relatório para contextualizar os resultados. Considerar adicionar perguntas situacionais extras para compensar.

## Agente Responsável
calibration-agent
