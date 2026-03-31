---
type: component
squad: human-mapping
version: "2.0.0"
---

# Career Fit Card

## Proposito

O Career Fit Card sintetiza informacoes de multiplos assessments para indicar areas de carreira com maior probabilidade de fit — alinhamento entre o perfil da pessoa e as demandas do ambiente profissional. Utiliza frameworks como RIASEC (Holland Codes), Strong Interest Inventory e dados derivados de tracos, motivacoes e forcas para construir uma visao integrada de direcionamento de carreira.

Este card nao determina "a carreira certa" — apresenta probabilidades de satisfacao e desempenho em diferentes contextos.

## Estrutura do Card

O card organiza informacoes em torno de codigos de interesse, ambientes ideais e caminhos de desenvolvimento, combinando dados quantitativos e qualitativos.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `interest_code` | string | Codigo RIASEC ou equivalente (ex: "IAS", "RCE") |
| `fit_occupations` | list | Ocupacoes com maior probabilidade de fit baseado no perfil |
| `ideal_environment` | text | Caracteristicas do ambiente de trabalho ideal para esta pessoa |
| `avoid_environments` | text | Ambientes que provavelmente gerarao insatisfacao ou baixo desempenho |
| `development_paths` | list | Caminhos de desenvolvimento recomendados com base no perfil |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `source_frameworks` | list | Frameworks que informaram este card |
| `current_fit_score` | float | Score de fit com a posicao atual (0-1.0) |
| `transition_risk` | string | Nivel de risco em uma transicao de carreira (Low/Medium/High) |
| `skill_gaps` | list | Lacunas de competencia identificadas para os caminhos recomendados |
| `industry_preference` | list | Industrias com maior alinhamento de valores e interesses |
| `work_style_preference` | text | Preferencias de formato de trabalho (remoto, hibrido, presencial) |
| `entrepreneurial_fit` | float | Score de fit para empreendedorismo (0-1.0) |
| `lateral_moves` | list | Movimentacoes laterais que ampliariam o perfil |

## Exemplo Preenchido

```yaml
interest_code: "IAS"
fit_occupations:
  - "Cientista de Dados — combina investigacao com impacto pratico"
  - "Pesquisador UX — integra analise com empatia pelo usuario"
  - "Consultor de Estrategia — usa pensamento analitico em contextos variados"
  - "Arquiteto de Sistemas — projeta solucoes complexas com autonomia"
ideal_environment: >
  Ambiente que valorize profundidade intelectual e autonomia.
  Equipes pequenas com alto nivel tecnico. Cultura que permita
  tempo de reflexao e nao penalize introversao. Metricas
  baseadas em resultado, nao em presenca.
avoid_environments: >
  Ambientes com alta rotatividade de prioridades sem justificativa.
  Culturas que priorizem politica sobre competencia. Funcoes
  com alta demanda de networking superficial ou vendas
  transacionais. Open offices sem espacos de concentracao.
development_paths:
  - "Especializacao tecnica profunda com eventual papel de tech lead"
  - "Transicao para consultoria estrategica apos 2-3 anos de experiencia aplicada"
  - "Desenvolvimento de habilidades de comunicacao para ampliar impacto"
source_frameworks: ["RIASEC", "Big Five", "CliftonStrengths", "Kolbe"]
current_fit_score: 0.72
```

## Regras de Preenchimento

1. O `interest_code` deve seguir a notacao padrao RIASEC (6 tipos: Realistic, Investigative, Artistic, Social, Enterprising, Conventional).
2. As `fit_occupations` devem incluir breve justificativa de por que cada uma foi selecionada.
3. O `ideal_environment` deve ser especifico o suficiente para orientar decisoes reais.
4. O `avoid_environments` nao e sobre preferencias superficiais — e sobre mismatches estruturais.
5. Os `development_paths` devem ser realisticamente alcancaveis, com indicacao de timeline.
6. Nunca apresentar career fit como determinismo — e probabilidade, nao destino.
7. Considerar o contexto do mercado de trabalho brasileiro quando aplicavel.
8. Quando o `current_fit_score` for abaixo de 0.5, incluir recomendacao explicita de revisao de carreira.
9. Cruzar com Motivation Card para verificar alinhamento entre fit ocupacional e drivers motivacionais.
10. Atualizar este card periodicamente — interesses e prioridades mudam com o tempo e experiencia.
