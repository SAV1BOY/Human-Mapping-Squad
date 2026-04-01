---
type: component
squad: human-mapping
version: "2.0.0"
---

# Layer Summary Card

## Proposito

O Layer Summary Card consolida os resultados de uma camada completa do mapeamento em um formato conciso e padronizado. Cada camada (Traits, Types, Motivation, Strengths, etc.) gera um card que serve como referencia rapida e ponto de handoff entre agentes do pipeline.

O card prioriza comunicabilidade: deve ser compreensivel isoladamente, sem necessidade de consultar dados brutos.

## Estrutura do Card

O card resume uma camada inteira em campos essenciais, facilitando tanto a leitura humana quanto a integracao entre agentes do pipeline.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `layer_name` | string | Nome da camada (ex: Traits, Types, Motivation, Strengths, Conation) |
| `frameworks_used` | list | Frameworks efetivamente utilizados nesta camada |
| `key_findings` | list | 3-5 achados principais, em ordem de relevancia |
| `confidence_score` | float | Score de confianca geral da camada (0.1 a 0.95) |
| `flags` | list | Alertas, contradicoes ou pontos de atencao identificados |
| `handoff_notes` | text | Notas para o proximo agente no pipeline sobre o que investigar ou validar |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `data_sources` | list | Fontes especificas dos dados (assessment oficial, proxy, entrevista) |
| `patterns_detected` | list | Patterns da biblioteca que foram identificados nesta camada |
| `contradictions_found` | list | Referencias a Contradiction Cards gerados |
| `respondent_engagement` | string | Nivel de engajamento do respondente nesta camada (Low, Medium, High) |
| `missing_data` | list | Dados que seriam uteis mas nao estavam disponiveis |
| `analyst_notes` | text | Observacoes subjetivas do analista sobre a camada |

## Exemplo Preenchido

```yaml
layer_name: "Traits"
frameworks_used:
  - "Big Five (NEO-PI-R) — assessment oficial"
  - "Big Five (proxy via DISC + entrevista)"
  - "Birkman — assessment oficial"
key_findings:
  - "Extroversao baixa (percentil 28) com adaptacao social alta — Hidden Introvert Pattern detectado"
  - "Conscienciosidade muito alta (percentil 88) — motor de desempenho e fator de risco para burnout"
  - "Neuroticismo moderado (percentil 52) — estavel em geral, com picos sob pressao social"
  - "Abertura alta (percentil 79) — curiosidade intelectual forte, receptivo a mudanca"
confidence_score: 0.78
flags:
  - "Gap Extroversao x DISC adaptado requer validacao em devolutiva"
  - "Birkman necessidade de aprovacao percentil 85 — explorar em camada Motivation"
handoff_notes: >
  A camada Traits sugere Hidden Introvert Pattern com alta confianca.
  O proximo agente (Types) deve verificar se o MBTI confirma I ou E.
  A necessidade de aprovacao detectada no Birkman deve ser aprofundada
  na camada Motivation com SDI e Enneagram.
data_sources:
  - "NEO-PI-R aplicado em 2025-11-15, resultado oficial"
  - "Birkman aplicado em 2025-11-20, resultado oficial"
  - "Entrevista semiestruturada de 45min em 2025-11-22"
patterns_detected:
  - "hidden-introvert-pattern (confianca: 0.82)"
missing_data:
  - "Feedback 360 nao disponivel — reduziu confidence em 0.05"
```

## Regras de Preenchimento

1. Os `key_findings` devem ser especificos e quantificados quando possivel — evitar generalidades.
2. O `confidence_score` deve seguir a rubrica padrao de confidence scoring do squad.
3. Os `flags` devem ser accionaveis — cada flag implica uma acao no pipeline.
4. O `handoff_notes` e o campo mais importante para continuidade: ser explicito sobre o que investigar a seguir.
5. Nunca omitir `missing_data` — a transparencia sobre lacunas e tao valiosa quanto os achados.
6. Cada camada deve gerar exatamente um Layer Summary Card, mesmo que a camada tenha dados limitados.
7. O card deve ser autocontido: um leitor que so ve o card deve entender os achados principais.
8. Listar `patterns_detected` com referencia ao arquivo na biblioteca e ao confidence do match.
