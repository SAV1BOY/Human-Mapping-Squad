---
type: checklist
level: layer
layer: conation
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Identificacao de Forcas Conativas

## Proposito
Garantir que forcas conativas foram separadas de habilidades cognitivas e preferencias afetivas com clareza e precisao.

## Criterios Obrigatorios
- [ ] Forcas conativas do individuo foram explicitamente identificadas — Evidencia: `Strength classification per mode documentada com forcas derivadas dos Action Modes em zona Initiate (score 7-10)`
- [ ] Cada forca conativa esta descrita em termos de acao natural e espontanea — Evidencia: `Campo 'descricao_acao' na strength classification per mode usando verbos de acao (ex: 'inicia', 'organiza', 'pesquisa', 'constroi')`
- [ ] Forcas conativas foram separadas de habilidades cognitivas aprendidas — Evidencia: `Conative vs cognitive vs affective separation document com coluna diferenciando forca conativa de habilidade treinada`
- [ ] Forcas conativas foram separadas de preferencias afetivas e emocionais — Evidencia: `Conative vs cognitive vs affective separation document com coluna diferenciando impulso de acao de preferencia emocional`
- [ ] Descricao das forcas nao utiliza linguagem de tracos de personalidade — Evidencia: `Revisao linguistica no conative vs cognitive vs affective separation document confirmando ausencia de termos como 'extrovertido', 'consciente', 'aberto'`
- [ ] Forcas estao vinculadas aos Action Modes com scores mais altos — Evidencia: `Cada forca na strength classification per mode referencia o Action Mode e score Kolbe A correspondente (zona Initiate)`
- [ ] Impacto pratico de cada forca conativa foi descrito — Evidencia: `Campo 'impacto_pratico' na strength classification per mode com exemplos de resultados concretos gerados pela forca`
- [ ] Situacoes onde as forcas se manifestam com mais intensidade foram identificadas — Evidencia: `Campo 'contextos_alta_manifestacao' na strength classification per mode com tipos de tarefa e ambiente que ativam a forca`

## Criterios Desejaveis
- [ ] Relacao entre forcas conativas e produtividade foi explorada
- [ ] Ambientes de trabalho que potencializam as forcas foram sugeridos
- [ ] Riscos de subutilizacao das forcas conativas foram descritos
- [ ] Comparacao entre forcas conativas e forcas de outras camadas foi feita
- [ ] Estrategias para alavancar as forcas conativas no dia a dia foram incluidas

## Decisao
- **PASS**: Todos os 8 criterios obrigatorios atendidos com strength classification per mode completa e conative vs cognitive vs affective separation document validado sem mistura de dominios.
- **CONDITIONAL**: 6-7 criterios obrigatorios atendidos. Separacao entre dominios presente mas incompleta, ou impacto pratico nao descrito para todas as forcas.
- **FAIL**: Menos de 6 criterios obrigatorios atendidos, ou conative vs cognitive vs affective separation document ausente, ou linguagem de tracos de personalidade utilizada nas descricoes.

## Acao se Falhar
Retornar ao kolbe-analyst para revisao rigorosa da separacao entre conacao, cognicao e afeto. Verificar se a linguagem utilizada nao mistura os dominios. Re-submeter apos correcao.

## Agente Responsavel
kolbe-analyst
