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

## Subtask Breakdown
1. **Aplicar perguntas de calibração** — Agente: `calibration-agent`. Input: banco de calibração (5-8 itens). Output: respostas + timestamps. Gate: todas as perguntas respondidas.
2. **Medir consistência** — Agente: `calibration-agent`. Input: respostas espelhadas. Output: score de consistência (0-100). Gate: ao menos 2 pares espelhados avaliados.
3. **Analisar padrões temporais** — Agente: `calibration-agent`. Input: timestamps por resposta. Output: `response-pattern`. Gate: desvio-padrão de tempos calculado.
4. **Calcular score de calibração** — Agente: `calibration-agent`. Input: consistência + padrão temporal. Output: `calibration-score` via confidence-calculator. Gate: score no range 0-100.
5. **Ajustar estratégia** — Agente: `calibration-agent`. Input: estilo de comunicação + score. Output: `question-strategy`. Gate: estratégia documentada no session record.

## Quality Gate
- [ ] Score de consistência calculado
- [ ] Estilo de comunicação identificado (direto/reflexivo/narrativo)
- Threshold: consistência >= 50% para prosseguir sem recalibração
- Se FAIL: aplicar rodada adicional de 3 perguntas de calibração

## Rework Trigger
- Consistência < 50% → repetir calibração com perguntas alternativas
- Respondente não engajado (respostas < 3s cada) → pausar e reavaliar
