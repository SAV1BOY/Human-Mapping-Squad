---
type: component
squad: human-mapping
version: "2.0.0"
---

# Strength Card

## Proposito

O Strength Card documenta uma forca individual identificada atraves de assessments como CliftonStrengths (Gallup), VIA Character Strengths ou derivada da convergencia de multiplos frameworks. Cada card representa uma forca especifica, incluindo como ela se manifesta naturalmente, os riscos de uso excessivo e como aplica-la para desenvolvimento e contribuicao em equipe.

Forcas nao sao simplesmente "coisas que a pessoa faz bem" — sao padroes naturais de pensamento, sentimento e comportamento que produzem resultados consistentes quando aplicados produtivamente.

## Estrutura do Card

O card equilibra a celebracao da forca com a consciencia de seus riscos, seguindo o principio de que toda forca exagerada se torna fraqueza.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `strength_name` | string | Nome da forca (ex: "Estrategico", "Empatia", "Realizador") |
| `domain` | string | Dominio da forca (Execucao, Influencia, Relacionamento, Pensamento Estrategico) |
| `natural_expression` | text | Como esta forca se manifesta naturalmente no dia a dia |
| `overdone_risk` | text | O que acontece quando esta forca e usada em excesso |
| `development_application` | text | Como aplicar esta forca intencionalmente para crescimento |
| `team_contribution` | text | Contribuicao unica que esta forca traz para a equipe |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `rank` | number | Posicao no ranking de forcas da pessoa (ex: Top 5) |
| `source_framework` | string | Framework de origem (ex: "CliftonStrengths", "VIA") |
| `complementary_strengths` | list | Forcas que combinam bem com esta |
| `conflicting_strengths` | list | Forcas que podem gerar tensao interna com esta |
| `maturity_level` | string | Nivel de maturidade no uso da forca (nascente, emergente, madura) |
| `blind_spot` | text | Ponto cego associado a esta forca |
| `cultural_expression` | text | Como a cultura organizacional afeta a expressao desta forca |

## Exemplo Preenchido

```yaml
strength_name: "Estrategico"
domain: "Pensamento Estrategico"
natural_expression: >
  Enxerga padroes onde outros veem complexidade. Rapidamente
  identifica caminhos alternativos e avalia cenarios antes de
  agir. Pergunta "e se?" naturalmente em qualquer situacao.
overdone_risk: >
  Pode ser percebido como alguem que complica demais decisoes
  simples. Tendencia a analisar excessivamente quando a acao
  rapida e necessaria. Pode frustrar colegas mais orientados
  a execucao.
development_application: >
  Canalizar para momentos de planejamento estrategico formal.
  Praticar o uso consciente em reunioes de brainstorming.
  Desenvolver a habilidade de simplificar a comunicacao de
  cenarios complexos para audiencias nao-estrategicas.
team_contribution: >
  Oferece a equipe a capacidade de antecipar obstaculos e
  identificar rotas alternativas. Valioso em momentos de
  crise ou mudanca de direcao. Complementa executores que
  precisam de clareza sobre prioridades.
rank: 2
source_framework: "CliftonStrengths"
complementary_strengths: ["Futurista", "Ideacao", "Analitico"]
blind_spot: >
  Pode subestimar o valor da execucao consistente e repetitiva,
  considerando-a "pouco interessante".
```

## Regras de Preenchimento

1. O `strength_name` deve usar a nomenclatura oficial do framework de origem.
2. O `domain` segue a classificacao do framework (para CliftonStrengths: Execucao, Influencia, Relacionamento, Pensamento Estrategico).
3. A `natural_expression` deve descrever comportamentos observaveis, nao potenciais abstratos.
4. O `overdone_risk` e obrigatorio — toda forca tem sombra. Omiti-lo gera perfis irrealistas.
5. O `development_application` deve sugerir acoes concretas e contextualizadas.
6. A `team_contribution` deve ser escrita de forma que um gestor possa usar para alocacao de papeis.
7. Listar no maximo 10 forcas por pessoa — priorizacao e mais util que exaustividade.
8. Quando duas forcas parecem contraditorias (ex: Harmonia + Comando), investigar e documentar como coexistem.
9. Forcas de dominio diferente que se combinam criam "duplas poderosas" — registrar em `complementary_strengths`.
10. Nunca apresentar forca como substituto para competencia tecnica — sao dimensoes diferentes.
