---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Traduzir Traços para Contexto de Trabalho (Hogan)

## Objetivo

Traduzir os traços de personalidade (Big Five) para o contexto de trabalho utilizando o framework Hogan, mapeando como os traços se manifestam no dia a dia profissional, sob pressão e em termos de valores.

## Pré-condições

- Camada de traços concluída (`run-trait-layer.md`)
- Scores OCEAN disponíveis com confiança adequada
- Contexto profissional mapeado no intake

## Passos

1. Mapear scores OCEAN para as três escalas Hogan:
   - **HPI (Bright Side)**: Como a pessoa se apresenta no seu melhor — reputação profissional
   - **HDS (Dark Side)**: Comportamentos de risco sob estresse — descarriladores potenciais
   - **MVPI (Inside)**: Valores, motivadores e preferências de cultura
2. Para o HPI, derivar scores nas 7 escalas:
   - Ajuste, Ambição, Sociabilidade, Sensibilidade Interpessoal, Prudência, Inquisitividade, Orientação para Aprendizado
3. Para o HDS, identificar descarriladores potenciais com base em extremos dos traços:
   - Ex: Alta extroversão + baixa amabilidade -> risco de "Bold" (arrogância sob pressão)
   - Ex: Alto neuroticismo + alta conscienciosidade -> risco de "Diligent" (perfeccionismo tóxico)
4. Para o MVPI, inferir valores predominantes com base no perfil de traços e contexto
5. Aplicar perguntas complementares específicas de workplace se profundidade permitir
6. Calcular confiança da tradução (tipicamente menor que a camada original em 10-15%)
7. Registrar traduções com explicações claras da lógica de mapeamento
8. Sinalizar áreas onde a tradução tem baixa confiança e precisa de mais dados

## Outputs

- `hpi-scores`: Scores das 7 escalas HPI (bright side)
- `hds-risks`: Descarriladores identificados com severidade
- `mvpi-values`: Valores e motivadores inferidos
- `translation-confidence`: Confiança da tradução por escala
- `translation-logic`: Lógica de mapeamento documentada

## Checklist de Conclusão

- [ ] Mapeamento OCEAN -> HPI realizado
- [ ] Descarriladores HDS identificados
- [ ] Valores MVPI inferidos
- [ ] Perguntas complementares aplicadas (se /deep)
- [ ] Confiança da tradução calculada
- [ ] Lógica de mapeamento documentada
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-type-style-layer.md` — Rodar camada de tipos e estilos

## Subtask Breakdown
1. **Mapear OCEAN para HPI** — Agente: `assessment-agent`. Input: `trait-scores`. Output: scores nas 7 escalas HPI. Gate: 7 escalas com valores válidos.
2. **Identificar descarriladores HDS** — Agente: `assessment-agent`. Input: extremos de traços. Output: `hds-risks` com severidade. Gate: ao menos os top 3 riscos documentados.
3. **Inferir valores MVPI** — Agente: `assessment-agent`. Input: traços + contexto. Output: `mvpi-values`. Gate: valores inferidos com lógica documentada.
4. **Aplicar perguntas complementares** — Agente: `assessment-agent`. Input: gaps de confiança (se /deep). Output: respostas adicionais. Gate: confiança da tradução >= 50.
5. **Documentar lógica de mapeamento** — Agente: `assessment-agent`. Input: todos os mapeamentos. Output: `translation-logic`. Gate: cada tradução com justificativa registrada.

## Quality Gate
- [ ] 7 escalas HPI, descarriladores HDS e valores MVPI gerados
- [ ] Confiança da tradução >= 50 para cada escala
- Threshold: confiança da tradução não mais que 15% abaixo da camada de traços
- Se FAIL: marcar escalas de baixa confiança como "hipótese" no relatório

## Rework Trigger
- Confiança da tradução < 40 em escala crítica → aplicar perguntas complementares
- Mapeamento gera contradição óbvia com traços → revisar lógica de mapeamento
