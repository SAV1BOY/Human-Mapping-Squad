---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Camada de Papel em Equipe (Belbin)

## Objetivo

Identificar os papéis preferenciais do respondente em equipe utilizando o framework Belbin, determinando contribuições naturais, papéis secundários e papéis a evitar.

## Pré-condições

- Camadas anteriores concluídas (traços, tipos, motivação, forças)
- Dados suficientes para inferência de papéis
- Contexto de equipe relevante (especialmente se objetivo é composição de equipe)

## Passos

1. Carregar banco de perguntas de papéis de equipe de `lib/questions/team-roles/`
2. Apresentar cenários de trabalho em equipe e capturar preferências:
   - "Em um projeto novo, você tende a..." (gerar ideias / organizar tarefas / conectar pessoas)
   - "Quando o time enfrenta um problema, você..." (analisa dados / busca consenso / age rápido)
3. Avaliar afinidade com os 9 papéis Belbin:
   - **Ação**: Shaper, Implementer, Completer-Finisher
   - **Social**: Coordinator, Teamworker, Resource Investigator
   - **Cerebral**: Plant, Monitor-Evaluator, Specialist
4. Executar scoring cruzando respostas diretas com inferências das camadas anteriores:
   - Alta extroversão + alta ambição Hogan -> provável Shaper ou Resource Investigator
   - Alta conscienciosidade + baixa abertura -> provável Implementer ou Completer-Finisher
   - Alta abertura + alta inquisitividade -> provável Plant
5. Gerar ranking dos 9 papéis de mais forte a mais fraco
6. Identificar papel primário (top 1), papéis secundários (top 2-3) e papéis a evitar (bottom 2)
7. Para contexto de equipe, analisar complementaridade com a composição atual
8. Calcular confiança da camada
9. Gerar recomendações de posicionamento em equipe

## Outputs

- `belbin-ranking`: Ranking completo dos 9 papéis
- `primary-role`: Papel primário identificado
- `secondary-roles`: Papéis secundários (2-3)
- `avoid-roles`: Papéis a evitar
- `team-fit-analysis`: Análise de complementaridade (se contexto de equipe)

## Checklist de Conclusão

- [ ] Cenários de equipe aplicados
- [ ] Afinidade com 9 papéis avaliada
- [ ] Scoring cruzado com camadas anteriores
- [ ] Ranking gerado
- [ ] Complementaridade analisada (se aplicável)
- [ ] Confiança calculada
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-career-fit-layer.md` — Rodar fit de carreira

## Subtask Breakdown
1. **Aplicar cenários de equipe** — Agente: `assessment-agent`. Input: banco de team-roles + depth-mode. Output: preferências em cenários. Gate: >= 3 cenários aplicados.
2. **Avaliar afinidade Belbin** — Agente: `assessment-agent`. Input: respostas + inferências de camadas anteriores. Output: scores nos 9 papéis. Gate: todos os 9 avaliados.
3. **Gerar ranking** — Agente: `assessment-agent`. Input: scores cruzados. Output: `belbin-ranking` ordenado. Gate: ranking sem empates nos top 3.
4. **Analisar complementaridade** — Agente: `assessment-agent`. Input: ranking + composição da equipe (se disponível). Output: `team-fit-analysis`. Gate: análise realizada (ou N/A se sem dados de equipe).
5. **Calcular confiança** — Agente: `assessment-agent`. Input: qualidade dos dados + cruzamentos. Output: `confidence` por papel. Gate: confiança do papel primário >= 60.

## Quality Gate
- [ ] 9 papéis Belbin rankeados com scores
- [ ] Papel primário e secundários identificados
- Threshold: confiança do papel primário >= 60
- Se FAIL: marcar papel primário como "provável" e incluir alternativa

## Rework Trigger
- Empate entre 2+ papéis primários → aplicar cenários de desempate
- Papel primário contradiz perfil de traços → investigar via cruzamento adicional
