---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Camada de Tipos e Estilos

## Objetivo

Executar a camada de tipos e estilos cognitivos, identificando preferências tipológicas (MBTI/Jung), estilo de aprendizagem e padrões de tomada de decisão do respondente.

## Pré-condições

- Camada de traços e tradução workplace concluídas
- Scores OCEAN e Hogan disponíveis
- Respondente engajado e calibrado

## Passos

1. Carregar banco de perguntas tipológicas de `lib/questions/types/`
2. Aplicar perguntas para identificar preferências nos 4 eixos:
   - Extroversão (E) vs Introversão (I) — fonte de energia
   - Sensação (S) vs Intuição (N) — coleta de informação
   - Pensamento (T) vs Sentimento (F) — tomada de decisão
   - Julgamento (J) vs Percepção (P) — estilo de vida
3. Executar `scripts/scoring/type-inference-engine.md` para inferir tipo
4. Calcular clareza de preferência por eixo (quão forte é a preferência)
5. Cruzar tipo inferido com dados de traços para validação:
   - Ex: INTJ deve ter alta Abertura e alta Conscienciosidade
   - Sinalizar inconsistências como pontos de investigação
6. Identificar função cognitiva dominante e auxiliar
7. Para modo `/deep`, explorar stack completo de funções cognitivas
8. Mapear estilo de aprendizagem derivado do tipo
9. Registrar tipo com grau de confiança por eixo
10. Adicionar notas sobre consistência com camadas anteriores

## Outputs

- `type-result`: Tipo inferido (ex: INTJ, ENFP)
- `preference-clarity`: Clareza de preferência por eixo (0-100)
- `cognitive-functions`: Funções cognitivas identificadas
- `learning-style`: Estilo de aprendizagem derivado
- `type-trait-consistency`: Análise de consistência com traços

## Checklist de Conclusão

- [ ] Perguntas tipológicas aplicadas
- [ ] Tipo inferido pelo engine
- [ ] Clareza de preferência calculada por eixo
- [ ] Cruzamento com traços validado
- [ ] Funções cognitivas identificadas
- [ ] Estilo de aprendizagem mapeado
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-motivation-layer.md` — Rodar camada de motivação

## Subtask Breakdown
1. **Aplicar perguntas tipológicas** — Agente: `assessment-agent`. Input: banco de tipos + depth-mode. Output: respostas nos 4 eixos. Gate: todos os 4 eixos com >= 2 respostas.
2. **Inferir tipo** — Agente: `assessment-agent`. Input: respostas via `type-inference-engine`. Output: `type-result` + `preference-clarity`. Gate: tipo de 4 letras gerado.
3. **Validar com traços** — Agente: `assessment-agent`. Input: tipo inferido + `trait-scores`. Output: `type-trait-consistency`. Gate: inconsistências sinalizadas.
4. **Identificar funções cognitivas** — Agente: `assessment-agent`. Input: tipo inferido. Output: `cognitive-functions` stack. Gate: dominante e auxiliar identificadas.
5. **Mapear estilo de aprendizagem** — Agente: `assessment-agent`. Input: tipo + funções. Output: `learning-style`. Gate: estilo vinculado a evidências.

## Quality Gate
- [ ] Tipo inferido com clareza de preferência em todos os 4 eixos
- [ ] Consistência com traços documentada
- Threshold: clareza de preferência >= 15 em ao menos 3 dos 4 eixos
- Se FAIL: marcar eixos marginais (clareza < 15) como "indeterminado"

## Rework Trigger
- Clareza < 15 em 2+ eixos → aplicar perguntas adicionais nos eixos fracos
- Contradição severa tipo vs traços → revisar respostas e considerar tipo alternativo
