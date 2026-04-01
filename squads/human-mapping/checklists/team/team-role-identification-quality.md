---
type: checklist
level: layer
layer: team
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Identificacao de Papeis de Equipe

## Proposito
Garantir que os papeis de equipe (Belbin) foram identificados com evidencia comportamental, incluindo papeis preferidos e menos confortaveis.

## Criterios Obrigatorios
- [ ] Papeis de equipe Belbin foram identificados para o individuo — Evidencia: `Belbin Self-Perception Inventory (SPI) preenchido com scores por papel no team-role-map-template`
- [ ] Cada papel identificado possui evidencia comportamental que o sustenta — Evidencia: `Behavioral indicators documentados no campo 'evidencias_comportamentais' do team-role-map-template para cada papel`
- [ ] Papeis preferidos (top 2-3) estao claramente diferenciados — Evidencia: `Ranking dos top 2-3 papeis com score >= 70 no Belbin assessment results, listados na secao 'papeis_preferidos'`
- [ ] Papeis menos confortaveis estao mapeados com justificativa — Evidencia: `Papeis com score <= 30 no Belbin assessment results, com justificativa no campo 'papeis_evitados' do team-role-map-template`
- [ ] Papeis gerenciaveis (intermediarios) foram considerados — Evidencia: `Papeis com score entre 31-69 listados na secao 'papeis_gerenciaveis' do team-role-map-template com contexto de ativacao`
- [ ] Evidencias comportamentais sao especificas, nao genericas — Evidencia: `Cada behavioral indicator inclui situacao concreta, comportamento observado e resultado, documentados no team-role-map-template`
- [ ] Diferenciacao entre papeis naturais e papeis assumidos por demanda foi feita — Evidencia: `Coluna 'tipo_papel' (natural/assumido) preenchida no team-role-map-template com frequencia de manifestacao por contexto`
- [ ] Mapeamento cobre as tres categorias Belbin: acao, social e cerebral — Evidencia: `Secoes 'acao' (Shaper/Implementer/Completer), 'social' (Coordinator/Teamworker/Resource Investigator) e 'cerebral' (Plant/Monitor Evaluator/Specialist) preenchidas no team-role-map-template`

## Criterios Desejaveis
- [ ] Comparacao com auto-percepcao do individuo foi incluida
- [ ] Exemplos situacionais concretos foram citados para cada papel principal
- [ ] Potenciais armadilhas (allowable weaknesses) de cada papel foram descritas
- [ ] Papeis foram correlacionados com tracos de personalidade da camada de tracos
- [ ] Evolucao potencial dos papeis ao longo da carreira foi mencionada

## Decisao
- **PASS**: Todos os 8 criterios obrigatorios atendidos com evidencias comportamentais documentadas no team-role-map-template e Belbin assessment results completos.
- **CONDITIONAL**: 6-7 criterios obrigatorios atendidos. Gaps menores podem ser corrigidos em ate 48h sem re-coleta de dados.
- **FAIL**: Menos de 6 criterios obrigatorios atendidos, ou ausencia de Belbin assessment results, ou team-role-map-template sem evidencias comportamentais.

## Acao se Falhar
Retornar a analise ao belbin-analyst para coleta de evidencias comportamentais adicionais. Se os dados de entrada forem insuficientes, solicitar informacoes complementares ao respondente antes de re-processar.

## Agente Responsavel
belbin-analyst
