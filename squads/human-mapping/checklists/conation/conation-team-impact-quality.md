---
type: checklist
level: layer
layer: conation
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Avaliacao de Impacto Conativo na Equipe

## Proposito
Garantir que o impacto do perfil conativo na dinamica de equipe foi avaliado com analise de complementaridades e friccoes.

## Criterios Obrigatorios
- [ ] Impacto do perfil conativo individual na equipe foi descrito — Evidencia: `Team conation compatibility matrix com coluna 'impacto_individual' descrevendo como cada Action Mode do individuo afeta a dinamica do grupo`
- [ ] Complementaridades conativas com outros membros foram identificadas — Evidencia: `Complementary modes identified na team conation compatibility matrix com pares de membros cujos Action Modes se complementam (ex: Quick Start alto + Follow Thru alto)`
- [ ] Friccoes conativas potenciais com outros membros foram identificadas — Evidencia: `Friction prediction documentada na team conation compatibility matrix com pares de membros com modos conflitantes e gatilhos especificos`
- [ ] Analise considera os Action Modes de outros membros da equipe — Evidencia: `Team conation compatibility matrix preenchida com Kolbe A scores de todos os membros da equipe e cruzamento par-a-par dos 4 Action Modes`
- [ ] Riscos de conflito conativo foram mapeados com cenarios especificos — Evidencia: `Secao 'riscos_conflito' na friction prediction com cenarios concretos (ex: deadline apertado, projeto ambiguo) e probabilidade de conflito por par`
- [ ] Sinergias conativas que potencializam a equipe foram descritas — Evidencia: `Secao 'sinergias' na team conation compatibility matrix com combinacoes de Action Modes que geram alto desempenho e exemplos de tarefas potencializadas`
- [ ] Impacto na divisao natural de tarefas foi analisado — Evidencia: `Secao 'divisao_tarefas' na team conation compatibility matrix mapeando quais tarefas cada membro assume naturalmente com base nas zonas Initiate`
- [ ] Recomendacoes para otimizar a interacao conativa na equipe foram fornecidas — Evidencia: `Secao 'recomendacoes_interacao' com acoes especificas para mitigar friccoes e alavancar complementary modes identified, incluindo protocolos de colaboracao`

## Criterios Desejaveis
- [ ] Matriz de compatibilidade conativa da equipe foi gerada
- [ ] Pares de alta friccao foram identificados com estrategias de mitigacao
- [ ] Pares de alta sinergia foram identificados com sugestoes de aproveitamento
- [ ] Impacto conativo em projetos especificos (inovacao, execucao, planejamento) foi diferenciado
- [ ] Evolucao prevista da dinamica conativa com mudancas na equipe foi considerada

## Decisao
- **PASS**: Todos os 8 criterios obrigatorios atendidos com team conation compatibility matrix completa, friction prediction documentada e complementary modes identified para todos os pares.
- **CONDITIONAL**: 6-7 criterios obrigatorios atendidos. Pares faltantes na compatibility matrix ou recomendacoes de interacao incompletas, corrigiveis com dados existentes.
- **FAIL**: Menos de 6 criterios obrigatorios atendidos, ou team conation compatibility matrix ausente, ou nenhuma friction prediction ou complementary modes documentados.

## Acao se Falhar
Retornar ao kolbe-analyst para revisao da analise de impacto. Coletar dados conativo de outros membros da equipe se ausentes. Re-executar a analise com foco nas complementaridades e friccoes nao identificadas.

## Agente Responsavel
kolbe-analyst
