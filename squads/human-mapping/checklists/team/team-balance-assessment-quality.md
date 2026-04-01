---
type: checklist
level: layer
layer: team
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Avaliacao de Balanco da Equipe

## Proposito
Garantir que o balanco da equipe foi analisado corretamente, com papeis presentes e ausentes identificados e gaps documentados.

## Criterios Obrigatorios
- [ ] Composicao atual da equipe foi mapeada com todos os papeis Belbin presentes — Evidencia: `Role distribution chart com cada membro e seus papeis primarios/secundarios na gap analysis table`
- [ ] Papeis ausentes na equipe foram explicitamente identificados — Evidencia: `Lista de papeis Belbin sem representante na equipe, documentada na secao 'papeis_ausentes' da gap analysis table`
- [ ] Gaps criticos na composicao foram priorizados por impacto — Evidencia: `Coluna 'prioridade' (critico/importante/desejavel) preenchida na gap analysis table com justificativa de impacto`
- [ ] Redundancias de papeis foram identificadas e avaliadas — Evidencia: `Papeis com 3+ membros listados na secao 'redundancias' da gap analysis table com avaliacao de risco/beneficio`
- [ ] Balanco entre papeis de acao, sociais e cerebrais foi avaliado — Evidencia: `Role distribution chart mostrando percentual de membros por categoria (acao/social/cerebral) e desvio do balanco ideal`
- [ ] Impacto dos gaps na performance da equipe foi descrito — Evidencia: `Secao 'impacto_dos_gaps' na gap analysis table com cenarios de risco especificos por papel ausente`
- [ ] Analise considerou o contexto e objetivos da equipe — Evidencia: `Campo 'contexto_equipe' preenchido com objetivos estrategicos e complementary roles identified para cada objetivo`
- [ ] Dados utilizados sao baseados em evidencias, nao em suposicoes — Evidencia: `Cada entrada na gap analysis table referencia o Belbin assessment result individual correspondente como fonte de dados`

## Criterios Desejaveis
- [ ] Cenarios de risco derivados dos gaps foram descritos
- [ ] Sugestoes de como membros existentes podem cobrir gaps foram incluidas
- [ ] Comparacao com equipes de alta performance foi referenciada
- [ ] Analise temporal considerou mudancas recentes na composicao da equipe
- [ ] Visualizacao grafica do balanco da equipe foi gerada

## Decisao
- **PASS**: Todos os 8 criterios obrigatorios atendidos com gap analysis table completa e role distribution chart gerado.
- **CONDITIONAL**: 6-7 criterios obrigatorios atendidos. Gaps na gap analysis table podem ser preenchidos sem re-coleta de dados individuais.
- **FAIL**: Menos de 6 criterios obrigatorios atendidos, ou gap analysis table ausente, ou role distribution chart nao gerado.

## Acao se Falhar
Revisar a analise de composicao da equipe com o belbin-analyst. Coletar dados adicionais dos membros da equipe se necessario. Re-executar a avaliacao de balanco com foco nos gaps nao identificados.

## Agente Responsavel
belbin-analyst
