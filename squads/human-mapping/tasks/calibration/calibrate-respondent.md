---
type: task
squad: human-mapping
version: "2.0.0"
agent: calibration-agent
workflow: calibration-workflow
---

# Task: Calibrar Respondente

## Objetivo

Calibrar o respondente antes do assessment principal, avaliando consistência nas respostas, nível de honestidade e padrão de comunicação para ajustar a interpretação dos dados coletados.

## Pré-condições

- Intake completo (`map-context.md` concluída)
- Session record com contexto e objetivo definidos
- Respondente pronto para a fase de calibração

## Passos

1. Aplicar sequência de 5-8 perguntas de calibração (não contam para o assessment)
2. Incluir pelo menos 2 perguntas espelhadas (mesma dimensão, formulação diferente) para medir consistência
3. Incluir 1-2 perguntas com resposta socialmente desejável óbvia para detectar viés
4. Medir tempo de resposta por pergunta para identificar padrões de reflexão vs impulso
5. Analisar consistência entre perguntas espelhadas:
   - Consistência alta (>80%): respondente confiável
   - Consistência média (50-80%): respondente moderado, aplicar margem de erro
   - Consistência baixa (<50%): alertar e considerar recalibração
6. Calcular score de calibração inicial usando `scripts/scoring/confidence-calculator.md`
7. Determinar estilo de comunicação do respondente (direto, reflexivo, narrativo)
8. Ajustar estratégia de perguntas para as próximas camadas
9. Registrar resultados de calibração no session record

## Outputs

- `calibration-score`: Score de consistência do respondente (0-100)
- `communication-style`: Estilo identificado de comunicação
- `response-pattern`: Padrão de tempo e profundidade de respostas
- `question-strategy`: Estratégia ajustada para o assessment

## Checklist de Conclusão

- [ ] Perguntas de calibração aplicadas
- [ ] Consistência medida e classificada
- [ ] Tempo de resposta analisado
- [ ] Score de calibração calculado
- [ ] Estilo de comunicação identificado
- [ ] Estratégia de perguntas ajustada
- [ ] Resultados registrados no session record

## Próxima Task

`tasks/calibration/detect-social-desirability.md` — Detectar viés de desejabilidade social
