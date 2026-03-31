---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Comando /start recebido pelo usuario"
agents: [chief, intake-orchestrator, context-mapper]
quality_gates: [intake-completeness-checklist, context-classification-checklist]
---

# Workflow: Start Command Flow

## Trigger

Usuario digita `/start` no canal de interacao com o squad.

## Pre-condicoes

- Nenhuma sessao ativa para o mesmo usuario no momento.
- Canal de comunicacao validado e permissoes confirmadas.
- Agentes chief, intake-orchestrator e context-mapper disponiveis.

## Sequencia

### Passo 1: Receber Comando /start
- **Agente:** chief
- **Acao:** Intercepta o comando `/start`, registra timestamp e identificador do usuario. Cria um novo `session_id` unico.
- **Decisao:** Se ja existe sessao ativa para o usuario, perguntar se deseja encerrar a anterior ou retomar.
- **Output:** `session_id`, registro de inicio, status `INITIATED`.

### Passo 2: Coletar Objetivo
- **Agente:** intake-orchestrator
- **Acao:** Apresenta perguntas estruturadas ao usuario para capturar o objetivo principal do mapeamento. Exemplos: desenvolvimento pessoal, contratacao, composicao de equipe, lideranca, orientacao de carreira.
- **Decisao:** Se o objetivo nao se encaixa nas categorias conhecidas, escalar para o chief com flag `OBJETIVO_ATIPICO`.
- **Output:** `objetivo_primario`, `objetivo_secundario` (opcional), `contexto_inicial`.

### Passo 3: Classificar Contexto
- **Agente:** context-mapper
- **Acao:** Analisa o objetivo coletado e mapeia para um ou mais workflows especializados (13-leadership, 14-hiring, 15-team, 16-career). Identifica variaveis contextuais: setor, nivel hierarquico, urgencia, historico previo.
- **Decisao:**
  - Se contexto claro → segue para selecao de profundidade.
  - Se contexto ambiguo → solicita mais informacoes ao usuario via intake-orchestrator.
- **Output:** `contexto_classificado`, `workflows_sugeridos[]`, `variaveis_contextuais{}`.

### Passo 4: Selecionar Profundidade
- **Agente:** intake-orchestrator
- **Acao:** Com base no contexto classificado, apresenta opcoes de profundidade ao usuario:
  - **Rapido:** Big Five + MBTI + Eneagrama (estimativa 30min).
  - **Padrao:** Todas as camadas principais (estimativa 60min).
  - **Profundo:** Todas as camadas + facetas + reconciliacao completa (estimativa 90-120min).
- **Decisao:** Usuario escolhe. Se nao responder em 5 minutos, assumir "Padrao".
- **Output:** `profundidade_selecionada`, `camadas_ativas[]`, `tempo_estimado`.

### Passo 5: Inicializar Sessao
- **Agente:** chief
- **Acao:** Consolida todas as informacoes coletadas em um objeto de sessao. Registra no log do squad. Notifica todos os agentes que serao ativados conforme `camadas_ativas[]`.
- **Output:** `sessao_completa{}` contendo: session_id, usuario, objetivo, contexto, profundidade, camadas, timestamp.

### Passo 6: Handoff para Calibracao
- **Agente:** chief
- **Acao:** Transfere controle para o workflow `02-respondent-calibration.md`. Envia `sessao_completa{}` como payload.
- **Decisao:** Se profundidade = "Rapido", pular calibracao e ir direto para `03-trait-assessment-flow.md`.
- **Output:** Handoff confirmado, proximo workflow ativado.

## Quality Gates (checkpoints)

- [ ] Objetivo primario registrado e validado.
- [ ] Contexto classificado com confianca >= 80%.
- [ ] Profundidade selecionada pelo usuario (nao assumida por padrao).
- [ ] Sessao inicializada com todos os campos obrigatorios preenchidos.
- [ ] Handoff para proximo workflow confirmado com ACK.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `sessao_completa{}` | JSON | Todos os workflows subsequentes |
| `log_inicio_sessao` | Texto estruturado | Registro interno do squad |
| `workflows_sugeridos[]` | Array | Chief para orquestracao |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Usuario nao responde em 10 minutos | Salvar estado parcial, enviar lembrete, aguardar mais 10 min. Apos isso, pausar sessao. |
| Objetivo incompreensivel | Intake-orchestrator reformula perguntas com exemplos concretos. Maximo 3 tentativas. |
| Context-mapper falha na classificacao | Chief assume classificacao manual e registra incidente para calibracao futura. |
| Conflito de sessao ativa | Apresentar opcoes: encerrar anterior, retomar anterior, ou cancelar nova. |

## Proximo Workflow

- **Padrao/Profundo:** `02-respondent-calibration.md`
- **Rapido:** `03-trait-assessment-flow.md`
- **Sub-workflow de detalhamento:** `01-goal-and-context-definition.md`
