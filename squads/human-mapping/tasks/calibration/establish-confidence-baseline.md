---
type: task
squad: human-mapping
version: "2.0.0"
agent: calibration-agent
workflow: calibration-workflow
---

# Task: Estabelecer Baseline de Confiança

## Objetivo

Definir o baseline de confiança da sessão, consolidando os dados de calibração e desejabilidade social para estabelecer o nível mínimo de confiança aceitável nos resultados do assessment.

## Pré-condições

- Calibração do respondente concluída (`calibrate-respondent.md`)
- Detecção de desejabilidade social concluída (`detect-social-desirability.md`)
- Scores de consistência e IDS disponíveis

## Passos

1. Consolidar os indicadores de calibração:
   - Score de consistência (0-100)
   - Índice de desejabilidade social (0-100)
   - Padrão de tempo de resposta (estável, variável, acelerado)
   - Estilo de comunicação identificado
2. Calcular o baseline de confiança geral usando a fórmula:
   - `baseline = (consistência * 0.5) + ((100 - IDS) * 0.3) + (estabilidade_tempo * 0.2)`
3. Definir limiares de confiança por camada:
   - Baseline >= 70: Todas as camadas podem prosseguir normalmente
   - Baseline 50-69: Camadas prosseguem com flag de cautela
   - Baseline < 50: Recomendação de recalibrar ou encerrar sessão
4. Configurar o `confidence-calculator` com os parâmetros de baseline
5. Definir o nível mínimo de confiança aceitável para cada output:
   - Snapshot executivo: mínimo 60
   - Relatório completo: mínimo 65
   - Relatório profundo: mínimo 70
   - Plano de desenvolvimento: mínimo 70
6. Registrar baseline no session record
7. Comunicar ao respondente (de forma sutil) o início da fase de assessment
8. Fazer handoff para o assessment-workflow

## Outputs

- `confidence-baseline`: Score numérico de baseline (0-100)
- `layer-thresholds`: Limiares de confiança por camada
- `output-minimums`: Confiança mínima por tipo de output
- `calibration-summary`: Resumo consolidado da calibração

## Checklist de Conclusão

- [ ] Indicadores de calibração consolidados
- [ ] Baseline de confiança calculado
- [ ] Limiares por camada definidos
- [ ] Mínimos por output definidos
- [ ] Confidence calculator configurado
- [ ] Session record atualizado com baseline
- [ ] Handoff para assessment preparado

## Próxima Task

`tasks/assessment/run-trait-layer.md` — Rodar camada de traços
