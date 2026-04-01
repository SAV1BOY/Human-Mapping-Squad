# Fase 02 — Traços de Personalidade

## Objetivo
Mapear os traços de personalidade do cliente utilizando modelos baseados em traços
(preferencialmente Big Five/OCEAN), estabelecendo a base dimensional do perfil.

## Inputs
- Plano de avaliação (Fase 01)
- Resultados de instrumentos Big Five (NEO-PI-R, IPIP, BFI)
- Resultados Hogan HPI (se disponível)
- Dados de proxy-inference (se aplicável)

## Processo
1. Aplicar ou coletar resultados do instrumento Big Five selecionado
2. Mapear as cinco dimensões principais e subfacetas
3. Comparar com normas populacionais relevantes
4. Se usando proxy-inference, documentar método e limitações
5. Calcular nível de confiança para cada traço
6. Identificar padrões notáveis e traços extremos

## Outputs
- Perfil Big Five completo com pontuações e percentis
- Análise de subfacetas (quando disponível)
- Nível de confiança por dimensão
- Notas sobre padrões e extremos identificados

## Checklist
- [ ] Instrumento Big Five aplicado ou resultados coletados
- [ ] Cinco dimensões mapeadas com pontuações
- [ ] Subfacetas analisadas (se dados disponíveis)
- [ ] Comparação com normas realizada
- [ ] Nível de confiança calculado e registrado
- [ ] Padrões notáveis documentados

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] Big Five: confiança ≥ 0.5 em todas as 5 dimensões
- [ ] Subfacetas analisadas (quando dados disponíveis)
- [ ] Padrões notáveis e extremos documentados

### NO-GO (não avançar)
- Confiança < 0.5 em qualquer dimensão Big Five → Ação: coletar dados adicionais ou aplicar proxy-inference
- Dados insuficientes para mapeamento mínimo → Ação: retornar à Fase 01 para ajustar plano

### Entregáveis Obrigatórios
- `trait-map-template` — preenchido e validado

### Arquivos Relacionados
- `templates/layers/trait-map-template.md`
- `checklists/trait-assessment-quality.md`
- `checklists/traits/big-five-quality.md`
- `workflows/03-trait-assessment-flow.md`

## Próxima Fase
`03-types.md` — Avaliação tipológica
