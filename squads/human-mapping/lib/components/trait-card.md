---
type: component
squad: human-mapping
version: "2.0.0"
---

# Trait Card

## Proposito

O Trait Card e o componente fundamental para representar um unico resultado de trait (traco) de personalidade. Ele captura a pontuacao individual de um traco especifico, como Extroversao no Big Five ou Assertividade no Hogan, junto com metadados de confianca e implicacoes praticas para o ambiente de trabalho.

Cada Trait Card deve ser autocontido — ou seja, compreensivel sem precisar consultar outros cards.

## Estrutura do Card

O card segue uma estrutura hierarquica com identificacao do traco, quantificacao, e interpretacao contextualizada para o mundo profissional.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `trait_name` | string | Nome do traco avaliado (ex: "Extroversao", "Prudencia") |
| `score` | number/string | Pontuacao em percentil (0-100) ou nivel (Low/Medium/High) |
| `confidence` | float (0-1.0) | Nivel de confianca estatistica do resultado |
| `behavioral_description` | text | Descricao comportamental observavel no dia a dia |
| `workplace_implication` | text | Como este traco impacta o desempenho e relacionamentos no trabalho |
| `development_note` | text | Orientacao para desenvolvimento baseada neste resultado |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `framework` | string | Framework de origem (ex: "Big Five", "Hogan HPI") |
| `facets` | list | Sub-facetas do traco, se aplicavel |
| `norm_group` | string | Grupo normativo usado para calcular o percentil |
| `raw_score` | number | Pontuacao bruta antes da normalizacao |
| `percentile_band` | string | Faixa interpretativa (ex: "acima da media") |
| `related_traits` | list | Tracos correlacionados ou complementares |
| `assessment_date` | date | Data em que o assessment foi realizado |

## Exemplo Preenchido

```yaml
trait_name: "Conscienciosidade"
score: 82
confidence: 0.88
behavioral_description: >
  Demonstra forte orientacao para organizacao e planejamento.
  Tende a cumprir prazos consistentemente e manter padroes
  elevados de qualidade em suas entregas.
workplace_implication: >
  Excelente para funcoes que exigem atencao a detalhes e
  gestao de processos. Pode apresentar dificuldade em ambientes
  muito ambiguos ou com mudancas frequentes de prioridade.
development_note: >
  Considerar desenvolvimento de flexibilidade cognitiva para
  lidar melhor com mudancas inesperadas. Praticar o conceito
  de "bom o suficiente" em tarefas de menor impacto.
framework: "Big Five (NEO-PI-R)"
norm_group: "Profissionais brasileiros, nivel gerencial"
```

## Regras de Preenchimento

1. O `trait_name` deve usar a nomenclatura oficial do framework de origem.
2. O `score` deve indicar claramente a escala utilizada (percentil vs. nivel categorico).
3. A `confidence` nunca deve ser 1.0 — nenhum assessment tem confianca perfeita.
4. A `behavioral_description` deve descrever comportamentos observaveis, nao rotulos abstratos.
5. A `workplace_implication` deve ser especifica e acionavel, nao generica.
6. O `development_note` deve sugerir acoes concretas, nao apenas apontar deficiencias.
7. Quando o score for extremo (abaixo de 15 ou acima de 85), incluir nota sobre possivel response bias.
8. Cada Trait Card deve referenciar apenas UM traco — combinacoes vao no Profile Layer.
9. Se o framework fornecer facets, listar ao menos as 3 mais relevantes.
10. Evitar linguagem patologizante — tracos sao tendencias, nao diagnosticos.
