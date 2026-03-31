---
type: checklist
level: layer
layer: report
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Acionabilidade

## Proposito
Verificar que todas as recomendacoes do relatorio sao genuinamente acionaveis, com responsavel, acao e prazo definidos, evitando conselhos vagos ou abstratos.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Cada recomendacao tem responsavel definido (quem faz) — Evidencia: `coluna de responsavel por recomendacao`
- [ ] Cada recomendacao tem acao clara (o que fazer) — Evidencia: `descricao da acao em verbo no infinitivo`
- [ ] Cada recomendacao tem prazo sugerido (quando) — Evidencia: `prazo ou faixa temporal por recomendacao`
- [ ] Nenhuma recomendacao e apenas descritiva sem acao — Evidencia: `revisao: todas recomendacoes contem verbo de acao`
- [ ] Recomendacoes estao priorizadas (nao e uma lista flat) — Evidencia: `ranking ou categorizacao por urgencia/importancia`
- [ ] Dependencias entre recomendacoes estao identificadas — Evidencia: `mapa de dependencias entre acoes`
- [ ] Recomendacoes sao realistas dado o contexto do respondente — Evidencia: `validacao de viabilidade por recomendacao`
- [ ] Primeiro passo concreto esta explicito para cada recomendacao — Evidencia: `next step imediato definido`
- [ ] Resultado esperado de cada recomendacao esta descrito — Evidencia: `outcome esperado por acao`

### Desejaveis (aumentam confianca)
- [ ] Recomendacoes foram agrupadas por tema ou horizonte temporal
- [ ] Custo estimado (tempo, dinheiro, energia) foi indicado
- [ ] Alternativas foram oferecidas para recomendacoes de alto custo
- [ ] Respondente validou viabilidade das recomendacoes

## Evidencia Necessaria
- Tabela de recomendacoes com responsavel, acao, prazo
- Ranking de priorizacao
- Mapa de dependencias
- Validacao de viabilidade
- Next step por recomendacao
- Outcome esperado

## Acao se Falhar
- Se recomendacao nao tem responsavel: definir quem deve executar (respondente, gestor, RH, coach)
- Se acao e vaga: reformular com verbo de acao e objeto especifico
- Se prazo nao existe: estimar prazo realista com margem
- Se recomendacao e irrealista: ajustar ao contexto ou substituir por alternativa viavel
- Se primeiro passo nao esta claro: decompor recomendacao em micro-acoes

## Agente Responsavel
- **Agente principal**: Agente de Relatorio
- **Agentes de suporte**: Agente de Carreira, Agente de Sintese
- **Aprovador final**: Agente de Qualidade
