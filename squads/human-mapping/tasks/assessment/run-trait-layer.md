---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Camada de Traços

## Objetivo

Executar a camada de traços de personalidade (Big Five / OCEAN), coletando respostas e gerando scores para Abertura, Conscienciosidade, Extroversão, Amabilidade e Neuroticismo.

## Pré-condições

- Calibração completa e baseline de confiança estabelecido
- Session record com parâmetros de profundidade e contexto
- Respondente pronto para o assessment

## Passos

1. Carregar banco de perguntas de traços de `lib/questions/traits/`
2. Selecionar perguntas conforme profundidade definida:
   - `/fast`: 5 perguntas (1 por dimensão)
   - `/start`: 10 perguntas (2 por dimensão)
   - `/deep`: 15 perguntas (3 por dimensão) + perguntas adaptativas
3. Aplicar perguntas em ordem randomizada para evitar viés de sequência
4. Monitorar qualidade das respostas em tempo real via `scripts/session/response-quality-checker.md`
5. Para modo `/deep`, adaptar perguntas seguintes com base nas respostas anteriores
6. Registrar cada resposta com timestamp e metadata
7. Aplicar fator de correção de desejabilidade social nos itens afetados
8. Executar `scripts/scoring/trait-scorer.md` para calcular scores por dimensão
9. Calcular confiança por dimensão via `scripts/scoring/confidence-calculator.md`
10. Gerar sub-facetas quando profundidade permitir (ex: Extroversão -> Assertividade, Sociabilidade, Energia)

## Outputs

- `trait-scores`: Scores por dimensão OCEAN (0-100)
- `trait-facets`: Sub-facetas quando disponíveis
- `trait-confidence`: Nível de confiança por dimensão
- `trait-raw-data`: Dados brutos de respostas

## Checklist de Conclusão

- [ ] Perguntas selecionadas conforme profundidade
- [ ] Todas as perguntas aplicadas e respostas coletadas
- [ ] Qualidade das respostas monitorada
- [ ] Fator de correção aplicado
- [ ] Scores calculados pelo trait-scorer
- [ ] Confiança por dimensão calculada
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-workplace-translation.md` — Traduzir traços para trabalho

## Subtask Breakdown
1. **Selecionar perguntas** — Agente: `assessment-agent`. Input: `depth-mode` + banco de traços. Output: conjunto de perguntas randomizadas. Gate: contagem conforme profundidade (5/10/15).
2. **Aplicar perguntas e monitorar** — Agente: `assessment-agent`. Input: perguntas selecionadas. Output: respostas + quality flags via response-quality-checker. Gate: todas respondidas com quality >= 40.
3. **Aplicar correção de viés** — Agente: `assessment-agent`. Input: respostas + `correction-factor`. Output: respostas corrigidas. Gate: correção aplicada nas dimensões afetadas.
4. **Calcular scores** — Agente: `assessment-agent`. Input: respostas corrigidas via `trait-scorer`. Output: `trait-scores` OCEAN (0-100). Gate: 5 dimensões com score válido.
5. **Calcular confiança** — Agente: `assessment-agent`. Input: scores + qualidade das respostas. Output: `trait-confidence` por dimensão. Gate: confiança >= baseline por dimensão.

## Quality Gate
- [ ] 5 dimensões OCEAN com scores no range 0-100
- [ ] Confiança média das dimensões >= 60
- Threshold: nenhuma dimensão com confiança < 40
- Se FAIL: aplicar perguntas complementares para dimensões com confiança baixa

## Rework Trigger
- Confiança de dimensão < 40 → aplicar 2-3 perguntas adicionais nessa dimensão
- Quality score médio das respostas < 50 → pausar e verificar engajamento
