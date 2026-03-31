---
type: checklist
level: layer
layer: respondent-quality
squad: human-mapping
version: "2.0.0"
---
# Checklist: Auditoria de Ambiguidades

## Propósito
Garantir que ambiguidades nas respostas do respondente foram detectadas e esclarecidas antes da fase de interpretação.

## Critérios
- [ ] Respostas com linguagem vaga foram identificadas — Evidência: `lista de respostas vagas gerada`
- [ ] Termos ambíguos foram catalogados (ex: "às vezes", "depende") — Evidência: `campo termos_ambiguos preenchido`
- [ ] Perguntas de clarificação foram formuladas para cada ambiguidade — Evidência: `perguntas de follow-up registradas`
- [ ] Respondente forneceu clarificações quando solicitado — Evidência: `respostas de clarificação coletadas`
- [ ] Respostas que podem ter múltiplas interpretações foram sinalizadas — Evidência: `flag multiplas_interpretacoes aplicado`
- [ ] Contexto foi utilizado para desambiguar quando possível — Evidência: `log de desambiguação por contexto`
- [ ] Ambiguidades não resolvidas foram documentadas com impacto estimado — Evidência: `campo ambiguidades_residuais preenchido`
- [ ] Score de clareza geral das respostas foi calculado — Evidência: `campo score_clareza preenchido`
- [ ] Ambiguidades culturais ou linguísticas foram consideradas — Evidência: `análise cultural aplicada`
- [ ] Nenhuma ambiguidade crítica permaneceu sem tratamento — Evidência: `validação de ambiguidades críticas = resolvidas`
- [ ] Decisão de interpretação para ambiguidades menores foi registrada — Evidência: `log de decisões de interpretação`
- [ ] Relatório final sinaliza onde ambiguidade afetou confiança — Evidência: `notas de ambiguidade no relatório`

## Ação se Falhar
Retornar ao respondente com perguntas específicas de clarificação. Se o respondente não puder esclarecer, registrar a ambiguidade como limitação e reduzir a confiança dos construtos afetados. Incluir nota no relatório final.

## Agente Responsável
respondent-quality-agent
