---
type: task
squad: human-mapping
version: "2.0.0"
agent: review-agent
workflow: review-workflow
---

# Task: Calibrar Scoring

## Objetivo

Calibrar os algoritmos de scoring utilizados nas camadas de assessment, ajustando pesos, limiares e fórmulas com base nos dados de acurácia acumulados para melhorar a precisão dos resultados.

## Pré-condições

- Revisão metodológica concluída ou em andamento (`update-methodology.md`)
- Dados de acurácia e feedback de múltiplas sessões disponíveis
- Acesso aos scripts de scoring em `scripts/scoring/`

## Passos

1. Identificar quais scorers precisam de calibração com base nos dados de acurácia:
   - `trait-scorer.md` — desvio médio entre score e feedback
   - `type-inference-engine.md` — taxa de acerto do tipo inferido
   - `motivation-scorer.md` — correlação entre ranking inferido e declarado
   - `strength-scorer.md` — taxa de reconhecimento das forças pelo respondente
   - `confidence-calculator.md` — calibração da confiança vs acurácia real
2. Para cada scorer que precisa de ajuste:
   a. Coletar conjunto de dados de calibração (respostas + feedback de acurácia)
   b. Analisar viés sistemático (tendência a scores altos ou baixos)
   c. Calcular ajuste necessário nos pesos e limiares
   d. Aplicar ajuste e testar com dados históricos
   e. Validar que o ajuste melhora a acurácia sem piorar outras dimensões
3. Calibrar especificamente o confidence-calculator:
   - Verificar se confiança alta correlaciona com acurácia alta
   - Ajustar fórmula se confiança está sistematicamente otimista ou pessimista
4. Recalibrar fatores de correção de desejabilidade social:
   - Verificar se a correção está adequada por contexto
   - Ajustar se necessário
5. Documentar todos os ajustes realizados com before/after
6. Atualizar versão dos scripts modificados
7. Testar regressão com pelo menos 5 sessões históricas

## Outputs

- `calibration-report`: Relatório de calibração com ajustes realizados
- `updated-scorers`: Lista de scorers atualizados com changelog
- `regression-results`: Resultados dos testes de regressão
- `accuracy-improvement`: Melhoria estimada na acurácia

## Checklist de Conclusão

- [ ] Scorers que precisam de calibração identificados
- [ ] Dados de calibração coletados
- [ ] Ajustes calculados e aplicados
- [ ] Confidence calculator recalibrado
- [ ] Fatores de desejabilidade social recalibrados
- [ ] Documentação de ajustes atualizada
- [ ] Testes de regressão executados e aprovados
- [ ] Versões dos scripts incrementadas

## Próxima Task

`tasks/operations/update-registries.md` — Atualizar registries (se necessário)
