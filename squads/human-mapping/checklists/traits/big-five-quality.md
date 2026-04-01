---
type: checklist
level: layer
layer: traits
squad: human-mapping
version: "3.0.0"
gate: mandatory
---

# Checklist: Qualidade da Medicao Big Five

## Proposito
Garantir que os cinco fatores foram medidos com indicadores comportamentais suficientes (>= 8 por dimensao), confidence adequada (>= 0.50), e resultados validados contra dados qualitativos.

## Thresholds de Referencia

| Dimensao | Indicadores Minimos | Confidence Minima | Score Extremo |
|----------|--------------------|--------------------|---------------|
| Abertura a Experiencia | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Conscienciosidade | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Extroversao | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Amabilidade | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |
| Neuroticismo | >= 8 | >= 0.50 | >= 0.85 ou <= 0.15 |

## Criterios Obrigatorios

### Cobertura por Dimensao
- [ ] Abertura medida com >= 8 indicadores comportamentais — Evidencia: lista de indicadores com contagem; cada indicador referencia comportamento observado ou resposta especifica
- [ ] Conscienciosidade medida com >= 8 indicadores comportamentais — Evidencia: lista de indicadores com contagem
- [ ] Extroversao medida com >= 8 indicadores comportamentais — Evidencia: lista de indicadores com contagem
- [ ] Amabilidade medida com >= 8 indicadores comportamentais — Evidencia: lista de indicadores com contagem
- [ ] Neuroticismo medido com >= 8 indicadores comportamentais — Evidencia: lista de indicadores com contagem

### Confidence por Dimensao
- [ ] Confidence de Abertura >= 0.50 — Evidencia: valor numerico documentado; se < 0.50, dimensao marcada como "confianca insuficiente"
- [ ] Confidence de Conscienciosidade >= 0.50 — Evidencia: valor numerico documentado
- [ ] Confidence de Extroversao >= 0.50 — Evidencia: valor numerico documentado
- [ ] Confidence de Amabilidade >= 0.50 — Evidencia: valor numerico documentado
- [ ] Confidence de Neuroticismo >= 0.50 — Evidencia: valor numerico documentado

### Validacao e Consistencia
- [ ] Scores normalizados para populacao de referencia — Evidencia: metodo de normalizacao documentado (ex: percentil, z-score); populacao de referencia identificada
- [ ] Correlacoes entre dimensoes sao plausiveis — Evidencia: nenhuma correlacao teoricamente impossivel (ex: Conscienciosidade 0.95 com Abertura 0.95 requer justificativa especial); matriz verificada
- [ ] Resultados cruzados com dados qualitativos — Evidencia: >= 1 ponto de validacao qualitativa por dimensao (ex: "Extroversao 0.75 confirmada por comportamento observado X")
- [ ] Distribuicao dos scores e plausivel no contexto — Evidencia: perfil nao apresenta todas as dimensoes no mesmo extremo sem justificativa; analise de plausibilidade registrada

### Tratamento de Extremos e Insuficiencias
- [ ] Dimensoes com score extremo (>= 0.85 ou <= 0.15) validadas — Evidencia: cada dimensao extrema tem >= 2 perguntas adicionais de validacao aplicadas e documentadas
- [ ] Dimensoes com confidence < 0.50 tratadas — Evidencia: itens adicionais aplicados OU dimensao reportada como "inconclusiva" no perfil final; nunca inferir score sem confidence adequada
- [ ] Perfil Big Five gerado no formato padronizado — Evidencia: documento com as 5 dimensoes, score numerico, confidence, e classificacao (baixo/medio/alto) para cada

## Criterios Desejaveis
- [ ] Facetas (sub-dimensoes) avaliadas para dimensoes com >= 10 indicadores
- [ ] Comparacao com normas especificas de industria/funcao quando disponiveis
- [ ] Intervalo de confianca estimado para cada score (+/- margem)
- [ ] Visualizacao grafica do perfil Big Five gerada

## Resultado
- **PASSA**: Todas as 5 dimensoes com >= 8 indicadores E confidence >= 0.50
- **PASSA PARCIAL**: >= 3 dimensoes passam; dimensoes insuficientes marcadas como "inconclusiva"
- **FALHA**: < 3 dimensoes com dados suficientes

## Acao se Falhar
1. Aplicar indicadores adicionais para dimensoes com < 8 indicadores
2. Se confidence permanece < 0.50 apos reforco: reportar dimensao como "inconclusiva"
3. Nunca inferir score sem confidence adequada — melhor reportar lacuna do que inventar dado
4. Se >= 3 dimensoes inconclusivas: considerar re-avaliacao completa
**Bloqueio**: Perfil Big Five com < 3 dimensoes conclusivas nao avanca para sintese.

## Agente Responsavel
traits-agent
