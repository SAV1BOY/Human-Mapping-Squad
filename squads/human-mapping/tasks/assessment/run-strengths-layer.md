---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Camada de Forças

## Objetivo

Executar a camada de forças (strengths), identificando os talentos naturais do respondente, competências consolidadas e áreas de excelência potencial, utilizando frameworks como CliftonStrengths e VIA.

## Pré-condições

- Camadas de traços, tipos e motivação concluídas
- Dados de personalidade e motivação disponíveis para cruzamento
- Profundidade da análise definida

## Passos

1. Carregar banco de perguntas de forças de `lib/questions/strengths/`
2. Aplicar perguntas que explorem:
   - Atividades que geram estado de flow
   - Tarefas que parecem naturais e sem esforço
   - Áreas onde recebe elogios consistentes
   - Momentos de alto desempenho na carreira
3. Usar perguntas comportamentais (STAR) para validar forças declaradas:
   - "Descreva uma situação onde você se sentiu completamente no seu elemento"
   - "Qual tarefa você faz melhor que a maioria das pessoas ao seu redor?"
4. Executar `scripts/scoring/strength-scorer.md` para classificar forças
5. Mapear forças para as 34 categorias CliftonStrengths (Top 5-10)
6. Identificar forças de caráter VIA complementares
7. Cruzar com dados anteriores para validação:
   - Alta abertura + maestria como motivador -> provável "Learner" ou "Input"
   - Alta extroversão + pertencimento -> provável "WOO" ou "Communication"
8. Distinguir entre forças naturais (talentos) e forças desenvolvidas (competências)
9. Identificar forças subutilizadas (talento presente, pouca aplicação)
10. Calcular confiança da camada

## Outputs

- `top-strengths`: Top 5-10 forças identificadas
- `strength-categories`: Classificação por domínio (execução, influência, relacionamento, pensamento estratégico)
- `underused-strengths`: Forças subutilizadas
- `strength-confidence`: Confiança por força identificada

## Checklist de Conclusão

- [ ] Perguntas de forças aplicadas
- [ ] Perguntas STAR para validação realizadas
- [ ] Scores calculados pelo strength-scorer
- [ ] Mapeamento CliftonStrengths realizado
- [ ] Cruzamento com camadas anteriores validado
- [ ] Forças subutilizadas identificadas
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-team-role-layer.md` — Rodar camada de papel em equipe

## Subtask Breakdown
1. **Aplicar perguntas de forças** — Agente: `assessment-agent`. Input: banco de forças + depth-mode. Output: respostas incluindo STAR. Gate: perguntas de flow, elogios e alto desempenho cobertas.
2. **Validar com perguntas STAR** — Agente: `assessment-agent`. Input: forças declaradas. Output: evidências comportamentais. Gate: >= 2 respostas STAR com quality >= 60.
3. **Classificar forças** — Agente: `assessment-agent`. Input: respostas via `strength-scorer`. Output: `top-strengths` mapeadas para CliftonStrengths. Gate: Top 5 identificadas.
4. **Distinguir talento vs competência** — Agente: `assessment-agent`. Input: scores + evidências. Output: classificação por força. Gate: cada top strength classificada.
5. **Identificar subutilizadas** — Agente: `assessment-agent`. Input: scores + aplicação reportada. Output: `underused-strengths`. Gate: lista documentada com oportunidades.

## Quality Gate
- [ ] Top 5-10 forças identificadas com scores e domínios
- [ ] Cada força classificada como talento natural ou competência desenvolvida
- Threshold: confiança média das top 5 forças >= 60
- Se FAIL: reduzir para Top 3 com maior confiança

## Rework Trigger
- Nenhuma força com confiança >= 60 → reaplicar com perguntas STAR adicionais
- Contradição forças vs traços → revisar scoring e cruzamento
