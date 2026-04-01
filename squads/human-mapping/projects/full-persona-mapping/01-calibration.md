# Fase 01 — Calibração

## Objetivo
Selecionar e calibrar os frameworks e instrumentos mais adequados para o perfil
do cliente, considerando contexto, objetivos e dados já disponíveis.

## Inputs
- Ficha de intake completa (Fase 00)
- Avaliações prévias disponíveis
- Objetivos declarados do cliente
- Framework-registry e methodology-registry

## Processo
1. Analisar o perfil do cliente e objetivos do mapeamento
2. Consultar o framework-selection-guide para escolha de instrumentos
3. Definir quais frameworks serão aplicados vs inferidos por proxy
4. Calibrar o nível de confiança esperado para cada dimensão
5. Identificar possíveis lacunas de dados e planejar mitigações
6. Documentar decisões de calibração e justificativas

## Outputs
- Plano de avaliação detalhado (frameworks selecionados)
- Mapa de cobertura: quais dimensões serão avaliadas e como
- Níveis de confiança alvo por dimensão
- Documento de calibração registrado

## Checklist
- [ ] Frameworks selecionados e justificados
- [ ] Cobertura de dimensões verificada (traços, tipos, motivações, forças)
- [ ] Método de avaliação definido para cada framework (direto vs proxy)
- [ ] Níveis de confiança alvo documentados
- [ ] Plano de avaliação aprovado
- [ ] Lacunas identificadas e mitigações planejadas

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] Consistência do respondente (response consistency) ≥ 0.5
- [ ] Frameworks selecionados e cobertura de dimensões verificada
- [ ] Plano de avaliação documentado e aprovado

### NO-GO (não avançar)
- Consistência < 0.5 → Ação: aplicar técnicas de recalibração ou reavaliar viabilidade
- Desejabilidade social elevada detectada → Ação: aplicar correções e documentar limitações

### Entregáveis Obrigatórios
- `reliability-sheet` — preenchido e validado
- `quality-flag-sheet` — preenchido e validado

### Arquivos Relacionados
- `templates/calibration/reliability-sheet.md`
- `templates/calibration/quality-flag-sheet.md`
- `checklists/calibration-quality.md`
- `workflows/02-respondent-calibration.md`

## Próxima Fase
`02-traits.md` — Avaliação de traços de personalidade
