---
type: checklist
level: layer
layer: team
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Analise de Gaps da Equipe

## Proposito
Garantir que gaps na composicao da equipe foram identificados com recomendacoes concretas para preenchimento.

## Criterios Obrigatorios
- [ ] Gaps na composicao da equipe foram identificados de forma explicita — Evidencia: `Gap identification document com lista de papeis/competencias ausentes e score de cobertura atual por area`
- [ ] Cada gap foi classificado por criticidade (critico, importante, desejavel) — Evidencia: `Coluna 'criticidade' no gap identification document com classificacao e justificativa por gap conforme priority ranking`
- [ ] Impacto de cada gap nos objetivos da equipe foi descrito — Evidencia: `Campo 'impacto_objetivos' no gap identification document vinculando cada gap a objetivos estrategicos afetados`
- [ ] Recomendacoes de preenchimento foram fornecidas para cada gap critico — Evidencia: `Recommendations for role filling documentadas com acoes especificas, responsavel e prazo para cada gap critico`
- [ ] Recomendacoes sao praticas e implementaveis — Evidencia: `Cada recomendacao no recommendations for role filling inclui recursos necessarios, viabilidade e passos de implementacao`
- [ ] Analise considerou se gaps podem ser cobertos por desenvolvimento interno — Evidencia: `Secao 'desenvolvimento_interno' no gap identification document com membros candidatos e plano de capacitacao por gap`
- [ ] Analise considerou se gaps requerem contratacao externa — Evidencia: `Secao 'contratacao_externa' no gap identification document com perfil ideal e justificativa de quando interno nao e viavel`
- [ ] Gaps foram identificados com base em dados, nao em intuicao — Evidencia: `Cada gap no gap identification document referencia Belbin assessment results e metricas de performance como fonte`
- [ ] Prioridade de preenchimento foi definida considerando o contexto da equipe — Evidencia: `Priority ranking com ordenacao dos gaps por urgencia, impacto e viabilidade, considerando objetivos e timeline da equipe`

## Criterios Desejaveis
- [ ] Perfil ideal para preenchimento de cada gap foi descrito
- [ ] Riscos de nao preencher cada gap foram documentados
- [ ] Timeline sugerida para acoes de preenchimento foi incluida
- [ ] Alternativas de curto prazo para mitigar gaps foram propostas
- [ ] Analise de custo-beneficio do preenchimento foi considerada

## Decisao
- **PASS**: Todos os 9 criterios obrigatorios atendidos com gap identification document completo, recommendations for role filling documentadas e priority ranking definido.
- **CONDITIONAL**: 7-8 criterios obrigatorios atendidos. Gaps identificados mas recomendacoes ou priority ranking incompletos, corrigiveis em ate 48h.
- **FAIL**: Menos de 7 criterios obrigatorios atendidos, ou gap identification document ausente, ou nenhuma recomendacao de preenchimento fornecida.

## Acao se Falhar
Retornar ao synthesis-architect para aprofundamento da analise de gaps. Coletar dados adicionais sobre os objetivos e desafios da equipe. Re-executar com foco nas recomendacoes praticas e implementaveis.

## Agente Responsavel
synthesis-architect
