---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Development Plan Builder

## Proposito

Construir o plano de desenvolvimento acionavel a partir do perfil mapeado, priorizando areas de crescimento com base na matriz Impacto x Esforco e transformando insights em acoes concretas.

## Input

1. **Saida do synthesis (synthesis output)**: Perfil sintetizado com camadas integradas
2. **Mapa de contradicoes (contradiction map)**: Areas de tensao e oportunidade
3. **Mapa de confianca (confidence map)**: Niveis de confianca para calibrar recomendacoes
4. **Framework de priorizacao (development-prioritization)**: Criterios e rubrica de classificacao

## Processo

### Passo 1: Identificar Areas de Desenvolvimento

A partir do perfil sintetizado, identificar areas potenciais:
- Gaps entre competencias atuais e demandas do contexto
- Padroes limitantes ou pontos cegos recorrentes
- Areas de tensao reveladas pelo mapa de contradicoes
- Oportunidades de alavancagem de forcas existentes
- Riscos comportamentais que requerem mitigacao ativa

### Passo 2: Aplicar Rubrica de Priorizacao

Aplicar `development-priority-rubric` com a matriz Impacto x Esforco:
- **Impacto**: Potencial de transformacao (alto/medio/baixo)
- **Esforco**: Dificuldade e recursos necessarios (alto/medio/baixo)
- Classificar cada area no quadrante correspondente
- Priorizar alto impacto + baixo esforco primeiro (quick wins estrategicos)
- Considerar interdependencias entre areas

### Passo 3: Selecionar Top 3-5 Areas

- Garantir diversidade entre dimensoes (nao concentrar em uma unica)
- Validar confianca suficiente e equilibrar quick wins com longo prazo

### Passo 4: Detalhar Cada Area Selecionada

Para cada area priorizada, elaborar:
- **Estado atual**: Onde a pessoa esta hoje, baseado nas evidencias
- **Estado desejado**: Alvo de desenvolvimento, realista e mensuravel
- **Quick Wins**: 2-3 acoes imediatas (proximos 30 dias)
- **Acoes de Longo Prazo**: 2-3 acoes estruturais (3-12 meses)
- **Recursos necessarios**: Ferramentas, apoio profissional, materiais
- **Cronograma sugerido**: Timeline com marcos intermediarios de progresso

### Passo 5: Aplicar Template

Aplicar `development-plan-template`: estrutura padronizada por area, visualizacao da matriz de priorizacao, formato acionavel com secoes de acompanhamento.

## Output

**Plano de desenvolvimento priorizado e acionavel**:
- Matriz Impacto x Esforco com todas as areas mapeadas
- Detalhamento das 3-5 areas prioritarias (estado atual, desejado, acoes)
- Recursos e cronograma por area
- Formatacao conforme development-plan-template

## Uso

```
Sequencia:
  1. Receber synthesis output + contradiction map + confidence map
  2. Carregar development-prioritization framework
  3. Executar development-plan-builder
  4. Encaminhar output para report-writer para revisao final
Dependencias:
  - synthesis-architect (output)
  - contradiction-map, confidence-map (inputs)
  - development-prioritization, development-priority-rubric
  - development-plan-template
```

## Especificacao de I/O

### Input
- Formato: YAML/Markdown
- Campos obrigatorios: synthesis output, contradiction-map, confidence-map, development-prioritization framework
- Exemplo: `{synthesis: {strengths: [...], attention_areas: [...]}, confidence: {overall: 70}, prioritization: "impact-effort"}`

### Output
- Formato: Markdown formatado
- Campos: matriz impacto x esforco, top 3-5 areas prioritarias (estado atual, desejado, quick wins, acoes longo prazo, recursos, cronograma)

### Thresholds
- min_priority_areas: 3
- max_priority_areas: 5
- quick_win_timeline: 30 dias
- long_term_timeline: 3-12 meses
- min_confidence_for_recommendation: 55

### Tratamento de Erros
- Input invalido: retornar erro `MISSING_SYNTHESIS_DATA`
- Dados insuficientes: gerar plano com areas de maior confianca e flag `limited-scope`
