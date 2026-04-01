---
type: component
squad: human-mapping
version: "2.0.0"
---

# Framework Comparison Card

## Proposito

O Framework Comparison Card documenta a comparacao entre dois ou mais frameworks aplicados a mesma pessoa, identificando pontos de convergencia, divergencia e reconciliacao. Este card e essencial para o cross-framework alignment e para a construcao de um perfil integrado coerente.

A comparacao entre frameworks e onde a riqueza do mapeamento multi-instrumento se manifesta: cada convergencia aumenta a confianca, cada divergencia revela complexidade.

## Estrutura do Card

O card estrutura a comparacao de forma sistematica, forcando a analise tanto de concordancias quanto de discordancias.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `frameworks_compared` | list | Frameworks sendo comparados (minimo 2) |
| `dimension_compared` | string | Dimensao ou construto sendo comparado (ex: extroversao, motivacao, estilo de lideranca) |
| `agreement_points` | list | Pontos onde os frameworks convergem, com evidencia |
| `disagreement_points` | list | Pontos onde os frameworks divergem, com descricao do conflito |
| `reconciliation` | text | Explicacao integrativa que resolve ou contextualiza as divergencias |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `confidence_impact` | text | Como a comparacao afeta o confidence score geral |
| `preferred_interpretation` | text | Qual framework deve ter mais peso nesta dimensao e por que |
| `follow_up_needed` | boolean | Se a divergencia requer investigacao adicional |
| `related_patterns` | list | Patterns que explicam a divergencia detectada |
| `visual_mapping` | text | Descricao de como os construtos se mapeiam entre frameworks |

## Exemplo Preenchido

```yaml
frameworks_compared:
  - "Big Five (NEO-PI-R)"
  - "DISC"
  - "Birkman"
dimension_compared: "Extroversao / Estilo Social"
agreement_points:
  - "Big Five Extroversao baixa (percentil 28) e Birkman necessidade de solidao alta (percentil 87) convergem: perfil introvertido no nucleo"
  - "DISC natural S alto e Big Five Extroversao baixa convergem: preferencia por estabilidade e reflexao"
disagreement_points:
  - "DISC adaptado I alto (72) contradiz Big Five Extroversao baixa (28) — a pessoa se apresenta como sociavel no trabalho mas nao e naturalmente extrovertida"
  - "Birkman comportamento usual sociavel (percentil 72) contradiz Birkman necessidade de solidao (percentil 87)"
reconciliation: >
  A divergencia se resolve pelo conceito de adaptacao profissional.
  O DISC adaptado captura como a pessoa SE COMPORTA no trabalho,
  enquanto Big Five e DISC natural capturam a DISPOSICAO NATURAL.
  O Birkman confirma: comportamento usual extrovertido e uma adaptacao;
  a necessidade real e de tempo sozinho. Diagnostico: Hidden Introvert
  Pattern com alta confianca. A adaptacao e saudavel e funcional, mas
  tem custo energetico que deve ser gerenciado.
confidence_impact: >
  A convergencia Big Five + DISC natural + Birkman necessidade aumenta
  confidence para 0.85. A divergencia com DISC adaptado e esperada
  e nao reduz confidence — ao contrario, enriquece a analise.
related_patterns:
  - "hidden-introvert-pattern"
```

## Regras de Preenchimento

1. Sempre listar TANTO `agreement_points` quanto `disagreement_points` — nunca omitir um dos lados.
2. A `reconciliation` deve ser uma explicacao integrativa, nao uma escolha de "quem esta certo".
3. Quando a divergencia nao pode ser reconciliada, declarar explicitamente e registrar como contradicao.
4. Referenciar os construtos especificos de cada framework, nao generalizacoes vagas.
5. O `preferred_interpretation` deve ser justificado com base na qualidade dos dados de cada framework.
6. Cada dimensao relevante deve ter seu proprio Framework Comparison Card — nao misturar dimensoes.
7. Usar este card como input direto para o Contradiction Card quando divergencias forem significativas.
8. A `visual_mapping` entre construtos e especialmente util quando frameworks usam nomenclaturas diferentes para medir coisas similares (ex: Extroversao no Big Five vs. I no DISC vs. Yellow no Insights).
