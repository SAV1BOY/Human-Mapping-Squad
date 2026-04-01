# Fase 07 — Análise de Contradições

## Objetivo
Identificar, classificar e resolver contradições aparentes entre resultados de
diferentes frameworks, transformando inconsistências em insights sobre a
complexidade do perfil do cliente.

## Inputs
- Perfil completo acumulado (Fases 02-06)
- Contradições sinalizadas nas fases anteriores
- Contradiction-registry para referência de padrões conhecidos

## Processo
1. Listar todas as contradições identificadas nas fases anteriores
2. Classificar cada contradição por tipo:
   - Contextual (comportamento varia por contexto)
   - Desenvolvimental (mudança ao longo do tempo)
   - Metodológica (limitação do instrumento)
   - Genuína (complexidade real da pessoa)
3. Investigar causas prováveis de cada contradição
4. Aplicar técnicas de resolução do contradiction-resolution-guide
5. Recalcular níveis de confiança afetados
6. Documentar contradições não resolvidas com transparência

## Outputs
- Inventário completo de contradições classificadas
- Resolução documentada para cada contradição tratável
- Contradições não resolvidas sinalizadas com nível de confiança ajustado
- Insights adicionais gerados pela análise de contradições

## Checklist
- [ ] Todas as contradições sinalizadas foram listadas
- [ ] Classificação por tipo realizada
- [ ] Causas investigadas para cada contradição
- [ ] Técnicas de resolução aplicadas
- [ ] Níveis de confiança recalculados
- [ ] Contradições não resolvidas documentadas com transparência

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] Todas as contradições de severidade S3 (High) e S4 (Critical) resolvidas ou documentadas com justificativa
- [ ] Níveis de confiança recalculados após resolução
- [ ] Contradições não resolvidas transparentes e classificadas

### NO-GO (não avançar)
- Contradição S4 (Critical) sem resolução nem justificativa → Ação: investigar com dados adicionais
- Contradições não classificadas por tipo → Ação: completar classificação antes de avançar

### Entregáveis Obrigatórios
- `contradiction-map-template` — preenchido e validado

### Arquivos Relacionados
- `templates/audit/contradiction-map-template.md`
- `checklists/contradiction-audit-quality.md`
- `checklists/contradiction/cross-framework-alignment.md`
- `workflows/08-contradiction-audit-flow.md`

## Próxima Fase
`08-synthesis.md` — Síntese do perfil integrado
