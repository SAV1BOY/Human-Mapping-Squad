---
type: component
squad: human-mapping
version: "2.0.0"
---

# Confidence Card

## Proposito

O Confidence Card registra o nivel de confianca de cada camada (layer) do perfil de mapeamento humano. Ele funciona como um indicador de qualidade que permite ao consumidor do perfil — coach, gestor, ou a propria pessoa — calibrar quanto peso dar a cada informacao. Sem este card, todos os dados parecem igualmente confiaveis, o que e perigoso.

A confianca nao e binaria. Um perfil pode ter alta confianca na camada de tracos e baixa confianca na camada de motivacoes, e isso precisa ser explicito.

## Estrutura do Card

O card quantifica e qualifica a confianca por camada, incluindo evidencias que sustentam (ou enfraquecem) cada score.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `layer` | string | Camada do perfil avaliada (ex: "Tracos", "Tipo", "Motivacao", "Forcas") |
| `score` | float (0-1.0) | Score de confianca da camada, onde 1.0 = maxima confianca |
| `evidence_count` | integer | Numero de fontes de dados independentes que informam esta camada |
| `convergence_level` | string | Nivel de convergencia entre fontes (High, Moderate, Low, Divergent) |
| `flags` | list | Alertas ou preocupacoes que afetam a confianca |
| `recommendation` | text | Recomendacao para o consumidor do perfil sobre como usar estes dados |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `frameworks_used` | list | Frameworks que contribuiram para esta camada |
| `data_freshness` | string | Quao recentes sao os dados (ex: "menos de 6 meses") |
| `retest_recommended` | boolean | Se recomenda-se refazer algum assessment |
| `quality_issues` | list | Problemas de qualidade identificados nos dados |
| `confidence_trend` | string | Se a confianca esta aumentando ou diminuindo ao longo do tempo |
| `minimum_threshold` | float | Limiar minimo de confianca para uso em decisoes |
| `assessor_notes` | text | Notas do avaliador sobre fatores que afetam a confianca |

## Exemplo Preenchido

```yaml
layer: "Tracos de Personalidade"
score: 0.85
evidence_count: 3
convergence_level: "High"
flags:
  - "Escala de Desejabilidade Social acima do percentil 75 no NEO-PI-R"
  - "Autoconsistencia interna do Big Five dentro de limites aceitaveis"
frameworks_used:
  - "Big Five (NEO-PI-R)"
  - "Hogan HPI"
  - "Birkman (componentes de personalidade)"
recommendation: >
  Alta confianca para uso em coaching e desenvolvimento.
  Atentar para possivel inflacao nas escalas de Amabilidade
  e Conscienciosidade devido a desejabilidade social elevada.
  Validar estes dois tracos com dados comportamentais ou 360.
data_freshness: "Menos de 12 meses"
retest_recommended: false
quality_issues:
  - "Desejabilidade social elevada pode inflar Amabilidade em 5-10 percentis"
```

## Regras de Preenchimento

1. O `score` deve ser calculado, nao estimado subjetivamente. Usar a formula definida no Quality Auditor.
2. O `evidence_count` conta fontes independentes — dois subtestes do mesmo instrumento contam como 1.
3. A `convergence_level` deve ser baseada em comparacao direta entre resultados de frameworks diferentes.
4. Os `flags` devem ser acionaveis — cada flag deve informar uma decisao ou precaucao especifica.
5. A `recommendation` deve ser escrita para um publico nao-tecnico que vai consumir o perfil.
6. Scores abaixo de 0.5 devem vir com recomendacao explicita de coleta adicional de dados.
7. A `data_freshness` importa: assessments com mais de 2 anos devem ter flag automatico.
8. Nunca arredondar o `score` para 1.0 — nenhuma camada tem confianca perfeita.
9. Quando o `convergence_level` for "Divergent", gerar automaticamente um Contradiction Card.
10. Revisar este card sempre que novos dados forem adicionados ao perfil — a confianca e dinamica.
