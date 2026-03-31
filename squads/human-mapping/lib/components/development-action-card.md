---
type: component
squad: human-mapping
version: "2.0.0"
---

# Development Action Card

## Proposito

O Development Action Card traduz insights do mapeamento humano em acoes concretas de desenvolvimento. E a ponte entre "quem voce e" e "o que voce pode fazer com essa informacao". Cada card representa uma unica acao de desenvolvimento, priorizada e conectada aos dados do perfil que a fundamentam.

Sem este card, o mapeamento permanece descritivo. Com ele, torna-se prescritivo e acionavel.

## Estrutura do Card

O card segue uma logica de acao orientada por evidencia: qual a acao, por que esta acao (baseada em quais dados), qual o impacto esperado e o que e necessario para executa-la.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `action` | text | Descricao clara e especifica da acao de desenvolvimento |
| `priority` | string | Tipo de prioridade: Quick Win, Strategic, Foundation, Experimental |
| `based_on` | list | Insights do perfil que fundamentam esta recomendacao |
| `expected_impact` | text | Impacto esperado se a acao for executada com sucesso |
| `timeline` | string | Prazo estimado para execucao e primeiros resultados |
| `resources_needed` | list | Recursos necessarios (tempo, dinheiro, apoio, ferramentas) |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `difficulty` | string | Nivel de dificuldade (Low, Medium, High) |
| `accountability` | string | Quem e responsavel por acompanhar (coach, gestor, propria pessoa) |
| `success_metrics` | list | Como medir se a acao esta funcionando |
| `prerequisites` | list | Acoes ou condicoes que precisam existir antes |
| `risks` | text | Riscos ou efeitos colaterais possiveis da acao |
| `alternative_actions` | list | Alternativas caso esta acao nao seja viavel |
| `status` | string | Status atual: Not Started, In Progress, Completed, Abandoned |
| `review_date` | date | Data programada para revisao de progresso |

## Exemplo Preenchido

```yaml
action: >
  Praticar delegacao estruturada: escolher 2 tarefas por
  semana que normalmente faria sozinho e delegar com briefing
  claro, prazo e checkpoint intermediario.
priority: "Strategic"
based_on:
  - "Conscienciosidade no percentil 88 — tendencia a centralizar para garantir qualidade"
  - "CliftonStrengths: Responsabilidade no Top 5 — dificuldade em soltar controle"
  - "Feedback 360: equipe reporta pouco espaco para autonomia"
  - "Risco de burnout identificado no pattern High Achiever"
expected_impact: >
  Reduzir carga de trabalho em 15-20%, aumentar autonomia da
  equipe e desenvolver confianca em outros. A medio prazo,
  libera tempo para atividades estrategicas alinhadas com
  as forcas de Pensamento Estrategico.
timeline: "3-6 meses para habito consistente, resultados parciais em 4 semanas"
resources_needed:
  - "30 minutos semanais para planejar delegacao"
  - "Apoio do gestor direto para proteger espaco de aprendizado"
  - "Template de briefing de delegacao (disponivel no toolkit)"
difficulty: "High"
success_metrics:
  - "Numero de tarefas delegadas por semana (meta: 2)"
  - "Satisfacao da equipe com autonomia (pesquisa trimestral)"
  - "Horas semanais gastas em execucao operacional (meta: reduzir 20%)"
risks: >
  Possivel ansiedade inicial ao soltar controle. Qualidade
  pode cair temporariamente enquanto a equipe se ajusta.
  Importante gerenciar expectativas proprias e da lideranca.
status: "Not Started"
review_date: "2026-06-30"
```

## Regras de Preenchimento

1. A `action` deve ser especifica e mensuravel — "melhorar comunicacao" nao e uma acao, e um desejo.
2. A `priority` segue a matriz: Quick Win (alto impacto, baixo esforco), Strategic (alto impacto, alto esforco), Foundation (pre-requisito para outras acoes), Experimental (testar hipotese).
3. O `based_on` deve referenciar dados reais do perfil — nunca inventar fundamentacao.
4. O `expected_impact` deve ser realista e conectado a resultados observaveis.
5. O `timeline` deve distinguir entre tempo de execucao e tempo para resultados visiveis.
6. Os `resources_needed` devem ser honestos — se precisa de coaching pago, dizer.
7. Limitar a 5-7 acoes ativas simultaneamente — mais que isso dilui foco e energia.
8. Quick Wins devem ser agendados primeiro para gerar momentum e confianca no processo.
9. Cada acao deve ter um `review_date` — acoes sem revisao sao abandonadas silenciosamente.
10. Conectar acoes entre si quando possivel — criar uma narrativa de desenvolvimento coerente.
