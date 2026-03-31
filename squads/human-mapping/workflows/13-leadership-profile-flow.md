---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Objetivo de mapeamento classificado como lideranca"
agents: [synthesis-architect, chief, report-writer, development-planner]
quality_gates: [leadership-lens-checklist, leadership-evidence-checklist]
---

# Workflow: Perfil de Lideranca

## Trigger

Ativado quando o objetivo do mapeamento e avaliar capacidade, estilo ou potencial de lideranca. Utiliza dados dos workflows 03-09 com lente especifica de lideranca.

## Pre-condicoes

- Workflows 03 a 09 concluidos (assessment completo + auditoria).
- Mapa unificado disponivel do workflow 09.
- Contexto organizacional mapeado (nivel hierarquico, cultura, desafios).

## Sequencia

### Passo 1: Extrair Dados Relevantes para Lideranca
- **Agente:** synthesis-architect
- **Acao:** Filtra mapa unificado para dimensoes criticas de lideranca:
  - **Tracos:** Conscienciosidade, Extroversao, Amabilidade, Abertura (Big Five). Honestidade-Humildade (HEXACO).
  - **Tipo de lideranca:** MBTI funcoes cognitivas → estilo de tomada de decisao. DISC → estilo de influencia.
  - **Motivacao para liderar:** Eneagrama tipo + nivel de saude. Reiss (Poder, Status, Independencia). MVPI.
  - **Forcas de lideranca:** Clifton dominio de Influencia e Pensamento Estrategico. Belbin (Coordinator, Shaper, Plant).
  - **Modo de acao na lideranca:** Kolbe → como toma decisoes e executa.
  - **Gestao de conflito:** SDI sequencia de conflito. FIRO-B (controle).
- **Output:** `dados_lideranca_extraidos{}`.

### Passo 2: Mapear Estilo de Lideranca
- **Agente:** synthesis-architect
- **Acao:** Cruza dados extraidos para identificar estilo de lideranca predominante:
  - **Diretivo:** Alta D (DISC), Shaper (Belbin), alto Poder (Reiss), tipo 8 ou 3 (Eneagrama).
  - **Inspirador:** Alta I (DISC), Comunicacao (Clifton), alto Idealismo (Reiss), tipo 7 ou 2 (Eneagrama).
  - **Participativo:** Alta S (DISC), Teamworker (Belbin), alto Contato Social (Reiss), tipo 9 ou 6 (Eneagrama).
  - **Analitico:** Alta C (DISC), Monitor Evaluator (Belbin), alta Ordem (Reiss), tipo 1 ou 5 (Eneagrama).
  - **Transformacional:** Alta Abertura (Big Five), Plant (Belbin), Futurista (Clifton), tipo 4 ou 7 (Eneagrama).
  - **Servant Leader:** Alta Amabilidade (Big Five), alta Honestidade-Humildade (HEXACO), tipo 2 ou 9.
- **Decisao:** Estilo raramente e puro. Identificar primario e secundario. Se ambiguo, documentar.
- **Output:** `estilo_lideranca_primario`, `estilo_lideranca_secundario`, `evidencia_por_estilo{}`.

### Passo 3: Avaliar Competencias de Lideranca
- **Agente:** synthesis-architect
- **Acao:** Avalia competencias classicas de lideranca contra o perfil:
  - **Visao estrategica:** Futurista + Estrategico (Clifton) + alta Abertura + Investigativo (RIASEC).
  - **Tomada de decisao:** Kolbe Fact Finder + MBTI Thinking/Judging + DISC D/C.
  - **Comunicacao e influencia:** DISC I + MBTI Extraversao + Clifton Comunicacao.
  - **Desenvolvimento de pessoas:** Clifton Desenvolvedor + Belbin Coordinator + Eneagrama integracao.
  - **Gestao de mudanca:** Kolbe Quick Start + DISC gap adaptacao + resiliencia sob estresse.
  - **Integridade e confianca:** HEXACO Honestidade-Humildade + VIA Honestidade + Eneagrama nivel saude.
  - Score de 1-10 por competencia, baseado em convergencia de instrumentos.
- **Output:** `competencias_lideranca{}` (6 competencias com score e evidencia).

### Passo 4: Identificar Riscos de Lideranca
- **Agente:** synthesis-architect
- **Acao:** Mapeia riscos especificos do perfil em posicao de lideranca:
  - **Descarrilhadores:** Tracos que sob pressao se tornam toxicos (ex: alta D + baixa Amabilidade → autoritarismo).
  - **Pontos cegos:** Areas que o lider nao percebe como problematicas.
  - **Burnout triggers:** Desalinhamento entre motivacao e demandas do papel.
  - **Conflito de equipe:** Como o estilo pode colidir com perfis complementares.
  - **Shadow do Eneagrama:** Comportamento na direcao de desintegracao.
- **Output:** `riscos_lideranca[]`, cada um com: descricao, gatilho, impacto potencial, mitigacao sugerida.

### Passo 5: Gerar Perfil de Lideranca
- **Agente:** report-writer
- **Acao:** Redige documento especifico de perfil de lideranca:
  - Estilo de lideranca predominante com nuances.
  - Competencias com scores visuais (radar chart).
  - Situacoes onde este lider brilha.
  - Situacoes onde este lider pode falhar.
  - Tipo de equipe ideal para este lider.
  - Tipo de cultura organizacional onde prospera.
  - Riscos com plano de mitigacao.
  - Comparacao com o contexto organizacional atual.
- **Output:** `perfil_lideranca_documento`.

### Passo 6: Gerar Plano de Desenvolvimento de Lideranca
- **Agente:** development-planner
- **Acao:** Cria plano especifico para crescimento como lider:
  - Foco nas 2-3 competencias com maior gap.
  - Estrategias de desenvolvimento alinhadas ao estilo natural (nao contra ele).
  - Sugestao de mentoria, coaching, ou experiencias de desenvolvimento.
  - Leituras e recursos recomendados conforme perfil.
  - Metricas de progresso na lideranca.
- **Output:** `plano_dev_lideranca`.

## Quality Gates (checkpoints)

- [ ] Estilo de lideranca identificado com evidencia de pelo menos 3 instrumentos.
- [ ] 6 competencias de lideranca avaliadas com score e evidencia.
- [ ] Riscos mapeados com descarrilhadores identificados.
- [ ] Perfil inclui cenarios positivos e negativos.
- [ ] Plano de desenvolvimento focado e acionavel.
- [ ] Contexto organizacional considerado na analise.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `perfil_lideranca_documento` | Markdown/PDF | Usuario, stakeholders |
| `competencias_lideranca{}` | JSON | Arquivo, reavaliacao |
| `riscos_lideranca[]` | Array | Development-planner |
| `plano_dev_lideranca` | Markdown/PDF | Usuario |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Perfil nao apresenta tracos claros de lideranca | Documentar honestamente. Pode ser lider emergente. Focar em potencial e desenvolvimento. |
| Contexto organizacional desconhecido | Gerar perfil generico com nota sobre necessidade de contextualizar. |
| Riscos detectados sao severos | Comunicar com sensibilidade. Reframing: "areas de desenvolvimento prioritario" nao "falhas". |
| Estilo incompativel com cultura organizacional | Destacar como insight valioso. Sugerir adaptacao ou busca de ambiente mais alinhado. |

## Proximo Workflow

- `12-development-plan-generation.md` (complementar ao plano de lideranca)
- `17-cross-squad-handoff-flow.md` (se necessario)
