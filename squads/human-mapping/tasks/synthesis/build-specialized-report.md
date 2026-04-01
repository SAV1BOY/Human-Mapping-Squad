---
type: task
squad: human-mapping
version: "2.0.0"
agent: synthesis-agent
workflow: synthesis-workflow
---

# Task: Construir Relatório Especializado

## Objetivo

Construir relatório especializado adaptado ao contexto específico da análise (contratação, equipe, liderança ou transição de carreira), com foco nas dimensões mais relevantes para a tomada de decisão.

## Pré-condições

- Perfil integrado sintetizado
- Contexto da análise requer relatório especializado (contratação, equipe, liderança, transição)
- Dados suficientes com confiança adequada para o tipo de relatório

## Passos

1. Identificar o tipo de relatório especializado necessário conforme contexto:
   - **Contratação**: Fit com vaga, riscos, recomendação hire/no-hire
   - **Equipe**: Complementaridade, gaps, recomendação de posicionamento
   - **Liderança**: Estilo de liderança, potencial, descarriladores, plano de desenvolvimento
   - **Transição de carreira**: Áreas de fit, gaps a desenvolver, plano de transição
2. Para relatório de **Contratação**:
   - Avaliar fit entre perfil e competências requeridas da vaga
   - Calcular score de compatibilidade (0-100)
   - Listar forças alinhadas à vaga e gaps relevantes
   - Identificar riscos comportamentais para a função
   - Gerar recomendação fundamentada (contratar/não contratar/contratar com ressalvas)
3. Para relatório de **Equipe**:
   - Analisar composição atual da equipe (se dados disponíveis)
   - Mapear contribuições únicas do respondente para o time
   - Identificar sobreposições e gaps de papéis
   - Sugerir posicionamento ideal na equipe
4. Para relatório de **Liderança**:
   - Classificar estilo de liderança predominante
   - Avaliar maturidade de liderança
   - Mapear descarriladores sob pressão
   - Definir plano de desenvolvimento de liderança
5. Para relatório de **Transição de Carreira**:
   - Comparar perfil com requisitos da nova área
   - Identificar competências transferíveis
   - Mapear gaps críticos a desenvolver
   - Estimar tempo e esforço para transição
6. Formatar conforme template especializado do squad

## Outputs

- `specialized-report`: Relatório especializado completo
- `decision-recommendation`: Recomendação para tomada de decisão
- `fit-score`: Score de compatibilidade (quando aplicável)
- `action-plan`: Plano de ação específico ao contexto

## Checklist de Conclusão

- [ ] Tipo de relatório especializado identificado
- [ ] Análise específica ao contexto realizada
- [ ] Recomendação fundamentada gerada
- [ ] Score de compatibilidade calculado (se aplicável)
- [ ] Plano de ação definido
- [ ] Formatação conforme template especializado
- [ ] Session record atualizado

## Próxima Task

`tasks/review/review-profile-accuracy.md` — Revisar acurácia do perfil

## Subtask Breakdown
1. **Identificar tipo de relatório** — Agente: `synthesis-agent`. Input: contexto da análise. Output: tipo selecionado (Contratação/Equipe/Liderança/Transição). Gate: tipo válido.
2. **Executar análise específica** — Agente: `synthesis-agent`. Input: perfil integrado + dados do contexto. Output: análise especializada. Gate: análise cobre todas as dimensões relevantes.
3. **Calcular fit score** — Agente: `synthesis-agent`. Input: perfil vs requisitos. Output: `fit-score` (0-100). Gate: score calculado (quando aplicável).
4. **Gerar recomendação** — Agente: `synthesis-agent`. Input: análise + fit score. Output: `decision-recommendation` fundamentada. Gate: recomendação com >= 3 evidências.
5. **Formatar relatório** — Agente: `synthesis-agent`. Input: análise completa. Output: `specialized-report`. Gate: template especializado aplicado.

## Quality Gate
- [ ] Relatório especializado completo e formatado
- [ ] Recomendação fundamentada com evidências
- Threshold: fit score com confiança >= 60
- Se FAIL: incluir disclaimer sobre confiança limitada na recomendação

## Rework Trigger
- Dados insuficientes para o contexto → solicitar informações complementares
- Fit score contradiz perfil qualitativo → reconciliar antes de emitir recomendação
