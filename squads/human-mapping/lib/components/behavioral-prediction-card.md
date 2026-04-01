---
type: component
squad: human-mapping
version: "2.0.0"
---

# Behavioral Prediction Card

## Proposito

O Behavioral Prediction Card registra previsoes comportamentais para contextos especificos, fundamentadas nos dados do mapeamento. Cada card prediz como o respondente provavelmente se comportara em uma situacao definida — sob pressao, em equipe, com autonomia, em conflito, etc. — e documenta as fontes de evidencia e o nivel de confianca da previsao.

Previsoes comportamentais sao o produto de maior valor pratico do mapeamento: transformam dados abstratos em orientacoes accionaveis.

## Estrutura do Card

O card conecta um contexto especifico a um comportamento previsto, sempre com rastreabilidade de evidencias.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `context` | string | Contexto especifico da previsao (ex: sob pressao, em equipe nova, com autonomia total) |
| `predicted_behavior` | text | Descricao detalhada do comportamento esperado neste contexto |
| `evidence_sources` | list | Frameworks e dados que fundamentam a previsao |
| `confidence` | float | Nivel de confianca da previsao (0.1 a 0.95) |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `behavioral_range` | text | Variacao esperada — melhor caso e pior caso |
| `trigger_conditions` | list | Condicoes especificas que ativam este comportamento |
| `mitigation_strategies` | list | Estrategias para mitigar comportamentos de risco |
| `development_opportunity` | text | Como este contexto pode ser usado para desenvolvimento |
| `observable_indicators` | list | Sinais observaveis que confirmam ou refutam a previsao |
| `time_horizon` | string | Prazo de validade da previsao (curto, medio, longo prazo) |

## Exemplo Preenchido

```yaml
context: "Sob pressao de prazo apertado com alta visibilidade"
predicted_behavior: >
  Tende a assumir controle da situacao (DISC D alto adaptado),
  reduzir comunicacao social para focar em entrega (Big Five
  Extroversao baixa natural emerge), e aumentar autocritica
  interna (Neuroticismo faceta ansiedade percentil 68). Entrega
  sera de alta qualidade (Conscienciosidade 88) mas a um custo
  energetico elevado. Pode negligenciar atualizacoes ao time.
evidence_sources:
  - "Big Five: Conscienciosidade 88 + Neuroticismo ansiedade 68"
  - "DISC: D adaptado alto — assume controle sob pressao"
  - "Kolbe: Follow Thru 7 — sistematiza para entregar"
  - "SDI: Conflict sequence stage 1 — foco em resultados, reduz empatia"
  - "Birkman: estresse aparece como retraimento social"
confidence: 0.79
behavioral_range: >
  Melhor caso: assume lideranca, organiza equipe eficientemente,
  entrega no prazo com qualidade. Pior caso: isola-se, faz tudo
  sozinho, nao comunica progresso, entrega mas com burnout.
trigger_conditions:
  - "Prazo menor que 2 semanas para entrega complexa"
  - "Multiplos stakeholders observando o resultado"
  - "Equipe percebida como menos competente que o respondente"
mitigation_strategies:
  - "Gestor deve pedir updates estruturados (diarios, por escrito) para compensar a tendencia de isolar"
  - "Parear com alguem de confianca para dividir carga — reduz a tendencia de fazer sozinho"
  - "Validar a entrega final antes da exaustao — o perfeccionismo pode gerar overwork"
observable_indicators:
  - "Cancela reunioes nao essenciais"
  - "Respostas a mensagens ficam mais curtas e diretas"
  - "Horarios de trabalho se estendem silenciosamente"
```

## Regras de Preenchimento

1. O `context` deve ser especifico e observavel — evitar contextos vagos como "no trabalho".
2. A `predicted_behavior` deve descrever ACOES observaveis, nao apenas estados internos.
3. Toda previsao deve ter no minimo 2 `evidence_sources` de frameworks diferentes.
4. O `confidence` deve ser menor quando a previsao depende de dados de um unico framework.
5. Incluir `behavioral_range` quando o contexto pode gerar tanto comportamento positivo quanto negativo.
6. As `mitigation_strategies` devem ser praticas e enderecadas a pessoas especificas (gestor, coach, o proprio respondente).
7. Os `observable_indicators` permitem validacao futura da previsao — incluir sempre que possivel.
8. Previsoes com confidence abaixo de 0.5 devem ser marcadas como "hipotese" e nao incluidas em relatorios executivos.
