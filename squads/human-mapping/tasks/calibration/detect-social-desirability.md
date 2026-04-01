---
type: task
squad: human-mapping
version: "2.0.0"
agent: calibration-agent
workflow: calibration-workflow
---

# Task: Detectar Viés de Desejabilidade Social

## Objetivo

Identificar e quantificar o grau de desejabilidade social nas respostas do respondente, ajustando os scores finais para refletir uma avaliação mais precisa do perfil real.

## Pré-condições

- Calibração inicial concluída (`calibrate-respondent.md`)
- Dados de calibração disponíveis no session record
- Score de consistência calculado

## Passos

1. Analisar as respostas às perguntas-armadilha da calibração (itens com resposta socialmente desejável evidente)
2. Calcular o índice de desejabilidade social (IDS) com base em:
   - Frequência de respostas no polo "ideal" das escalas
   - Ausência de admissão de fraquezas comuns
   - Padrão de respostas extremas positivas
3. Classificar o nível de viés:
   - **Baixo** (IDS < 30): Respondente autêntico, sem ajuste necessário
   - **Moderado** (IDS 30-60): Aplicar fator de correção de 10-15% nos scores positivos
   - **Alto** (IDS > 60): Aplicar fator de correção de 20-30% e sinalizar no relatório
4. Identificar dimensões específicas mais afetadas pelo viés (geralmente: amabilidade, conscienciosidade, estabilidade emocional)
5. Cruzar com o contexto da análise — contratação tende a amplificar desejabilidade social
6. Registrar o fator de correção no session record para uso nos scorers
7. Se IDS > 75, considerar inserir perguntas de verificação adicionais durante o assessment
8. Documentar evidências do viés para transparência no relatório final

## Outputs

- `social-desirability-index`: Índice numérico de desejabilidade social (0-100)
- `correction-factor`: Fator de correção a ser aplicado nos scores
- `affected-dimensions`: Dimensões mais impactadas pelo viés
- `bias-evidence`: Evidências documentadas do viés

## Checklist de Conclusão

- [ ] Respostas-armadilha analisadas
- [ ] Índice de desejabilidade social calculado
- [ ] Nível de viés classificado
- [ ] Fator de correção definido
- [ ] Dimensões afetadas identificadas
- [ ] Session record atualizado com dados de viés
- [ ] Estratégia de verificação adicional definida (se necessário)

## Próxima Task

`tasks/calibration/establish-confidence-baseline.md` — Estabelecer baseline de confiança

## Subtask Breakdown
1. **Analisar respostas-armadilha** — Agente: `calibration-agent`. Input: respostas a itens de desejabilidade. Output: contagem de respostas "ideais". Gate: >= 1 item armadilha avaliado.
2. **Calcular IDS** — Agente: `calibration-agent`. Input: frequência de respostas ideais + ausência de fraquezas. Output: `social-desirability-index` (0-100). Gate: IDS calculado.
3. **Classificar nível de viés** — Agente: `calibration-agent`. Input: IDS. Output: classificação (Baixo/Moderado/Alto). Gate: fator de correção definido.
4. **Identificar dimensões afetadas** — Agente: `calibration-agent`. Input: IDS + respostas por dimensão. Output: `affected-dimensions`. Gate: lista documentada.
5. **Registrar e decidir ações** — Agente: `calibration-agent`. Input: IDS + contexto. Output: fator de correção no session record. Gate: se IDS > 75, perguntas adicionais planejadas.

## Quality Gate
- [ ] IDS calculado e registrado no session record
- [ ] Fator de correção definido e documentado
- Threshold: IDS <= 75 para prosseguir sem perguntas adicionais
- Se FAIL: inserir 3-5 perguntas de verificação no assessment

## Rework Trigger
- IDS > 90 → considerar invalidar sessão e reiniciar com orientação ao respondente
- Dimensões afetadas > 3 → retornar ao `calibrate-respondent` para recalibração
