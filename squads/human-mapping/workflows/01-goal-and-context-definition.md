---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Sub-workflow chamado pelo 00-start-command-flow quando contexto precisa de aprofundamento"
agents: [intake-orchestrator, context-mapper, chief]
quality_gates: [goal-clarity-checklist, context-depth-checklist]
---

# Workflow: Definicao de Objetivo e Contexto

## Trigger

Chamado como sub-workflow do `00-start-command-flow.md` quando o contexto inicial e insuficiente ou quando a classificacao do context-mapper retorna confianca < 80%.

## Pre-condicoes

- Sessao ja iniciada com `session_id` valido.
- Objetivo primario coletado (mesmo que vago).
- Pelo menos uma tentativa de classificacao de contexto realizada.

## Sequencia

### Passo 1: Revisar Objetivo Declarado
- **Agente:** intake-orchestrator
- **Acao:** Reapresenta o objetivo declarado pelo usuario e faz perguntas de refinamento:
  - "O que voce espera fazer com esse mapeamento?"
  - "Existe uma decisao especifica que este resultado vai informar?"
  - "Ha alguma urgencia ou prazo associado?"
- **Decisao:** Se usuario confirma objetivo sem alteracoes, marcar como `objetivo_validado`. Se altera, registrar nova versao.
- **Output:** `objetivo_refinado`, `decisao_alvo` (opcional), `urgencia`.

### Passo 2: Mapear Contexto Organizacional
- **Agente:** context-mapper
- **Acao:** Coleta informacoes contextuais estruturadas:
  - Setor de atuacao (industria, servicos, tecnologia, etc.).
  - Tamanho da organizacao.
  - Nivel hierarquico do respondente.
  - Cultura organizacional percebida.
  - Desafios atuais no ambiente de trabalho.
- **Decisao:** Se respondente e autonomo (sem organizacao), ajustar framework para contexto individual.
- **Output:** `contexto_organizacional{}`.

### Passo 3: Mapear Contexto Pessoal
- **Agente:** context-mapper
- **Acao:** Coleta informacoes do contexto pessoal relevante:
  - Momento de carreira (inicio, transicao, consolidacao, reinvencao).
  - Experiencia previa com assessments (nenhuma, basica, avancada).
  - Expectativas e receios sobre o processo.
  - Historico de feedbacks recebidos (se houver).
- **Output:** `contexto_pessoal{}`.

### Passo 4: Determinar Profundidade Adequada
- **Agente:** intake-orchestrator
- **Acao:** Cruza objetivo + contexto organizacional + contexto pessoal para recomendar profundidade ideal. Apresenta recomendacao ao usuario com justificativa.
- **Decisao:**
  - Se objetivo e decisao de contratacao urgente → recomendar "Padrao" com foco em `14-hiring`.
  - Se objetivo e autoconhecimento profundo → recomendar "Profundo".
  - Se objetivo e triagem rapida → recomendar "Rapido".
- **Output:** `profundidade_recomendada`, `justificativa`, `profundidade_aceita`.

### Passo 5: Definir Camadas Ativas
- **Agente:** chief
- **Acao:** Com base na profundidade aceita, define quais camadas serao ativadas:
  - **Rapido:** Tracos (Big Five) + Tipos (MBTI) + Motivacao (Eneagrama).
  - **Padrao:** Todas as camadas principais sem facetas detalhadas.
  - **Profundo:** Todas as camadas + facetas + instrumentos complementares.
- **Decisao:** Se usuario solicita camada especifica fora do padrao, adicionar sob demanda.
- **Output:** `camadas_ativas[]`, `instrumentos_por_camada{}`.

### Passo 6: Consolidar e Retornar
- **Agente:** chief
- **Acao:** Empacota todo o contexto refinado no objeto de sessao. Retorna controle para o workflow pai (`00-start-command-flow.md`, Passo 5).
- **Output:** `contexto_completo{}` atualizado na sessao.

## Quality Gates (checkpoints)

- [ ] Objetivo refinado com clareza suficiente para direcionar o mapeamento.
- [ ] Contexto organizacional mapeado (ou marcado como N/A para autonomos).
- [ ] Contexto pessoal mapeado com momento de carreira identificado.
- [ ] Profundidade aceita pelo usuario (nao apenas recomendada).
- [ ] Camadas ativas definidas e consistentes com a profundidade.
- [ ] Nenhuma pergunta critica sem resposta.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `objetivo_refinado` | Texto | Sessao principal |
| `contexto_organizacional{}` | JSON | Todos os workflows de assessment |
| `contexto_pessoal{}` | JSON | Rapport-architect, synthesis |
| `camadas_ativas[]` | Array | Chief para orquestracao |
| `profundidade_aceita` | Enum | Controle de fluxo |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Usuario recusa fornecer contexto organizacional | Prosseguir com contexto pessoal apenas. Registrar limitacao no relatorio final. |
| Objetivo permanece vago apos 3 tentativas | Chief intervem com abordagem exploratoria: iniciar com assessment rapido e refinar depois. |
| Conflito entre objetivo e profundidade | Intake-orchestrator explica trade-offs e solicita decisao final do usuario. |

## Proximo Workflow

Retorna para `00-start-command-flow.md` (Passo 5: Inicializar Sessao).
