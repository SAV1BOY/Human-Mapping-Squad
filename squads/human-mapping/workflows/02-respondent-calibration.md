---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Handoff do 00-start-command-flow apos inicializacao da sessao"
agents: [rapport-architect, respondent-quality-auditor, readiness-gatekeeper]
quality_gates: [rapport-established-checklist, response-quality-checklist, readiness-gate]
---

# Workflow: Calibracao do Respondente

## Trigger

Recebe handoff do `00-start-command-flow.md` com `sessao_completa{}`. Executado antes de qualquer interpretacao de dados comportamentais.

## Pre-condicoes

- Sessao inicializada com objetivo, contexto e profundidade definidos.
- Usuario disponivel para interacao em tempo real.
- Nenhum assessment anterior iniciado nesta sessao.

## Sequencia

### Passo 1: Construir Rapport
- **Agente:** rapport-architect
- **Acao:** Inicia conversa informal e acolhedora com o usuario. Objetivos:
  - Estabelecer tom de confianca e seguranca psicologica.
  - Explicar o processo de mapeamento de forma acessivel.
  - Esclarecer que nao existem respostas certas ou erradas.
  - Ajustar linguagem ao perfil do usuario (formal, informal, tecnico).
  - Confirmar consentimento informado para o processo.
- **Decisao:** Se usuario demonstra resistencia ou desconfianca, estender fase de rapport antes de prosseguir.
- **Output:** `rapport_status` (estabelecido | parcial | nao_estabelecido), `tom_ajustado`, `consentimento`.

### Passo 2: Avaliar Qualidade de Resposta
- **Agente:** respondent-quality-auditor
- **Acao:** Aplica perguntas-piloto (3 a 5 perguntas de calibracao) para avaliar:
  - **Consistencia:** Respostas coerentes entre si.
  - **Profundidade:** Respostas com elaboracao suficiente vs. monossilabicas.
  - **Desejabilidade social:** Deteccao de respostas "politicamente corretas" vs. autenticas.
  - **Compreensao:** Usuario entende as perguntas conforme formuladas.
  - **Velocidade:** Tempo de resposta indica reflexao ou impulsividade.
- **Decisao:**
  - Qualidade alta (score >= 8/10) → prosseguir normalmente.
  - Qualidade media (score 5-7) → ajustar formulacao das perguntas.
  - Qualidade baixa (score < 5) → escalar para readiness-gatekeeper.
- **Output:** `qualidade_resposta_score`, `indicadores_detalhados{}`, `ajustes_recomendados[]`.

### Passo 3: Estabelecer Baseline de Confianca
- **Agente:** respondent-quality-auditor
- **Acao:** Define o baseline de confianca para esta sessao especifica:
  - Nivel de autoconsciencia do respondente (baixo, medio, alto).
  - Tendencia a aquiescencia (concordar com tudo).
  - Tendencia a extremismo (sempre escolher extremos nas escalas).
  - Vieses culturais identificados.
  - Calcula `fator_de_ajuste` para corrigir vieses nas interpretacoes.
- **Output:** `baseline_confianca{}`, `fator_de_ajuste`, `vieses_detectados[]`.

### Passo 4: GATE - Prosseguir ou Pausar
- **Agente:** readiness-gatekeeper
- **Acao:** Avalia todos os outputs anteriores e decide:
  - **PROSSEGUIR:** Rapport estabelecido + qualidade >= media + baseline definido.
  - **AJUSTAR:** Rapport parcial ou qualidade media. Recomenda ajustes especificos e retorna ao Passo 1 ou 2.
  - **PAUSAR:** Rapport nao estabelecido ou qualidade baixa. Sugere reagendar sessao ou mudar abordagem.
  - **ESCALAR:** Sinais de que o respondente nao esta apto (estresse extremo, resistencia ativa). Notifica chief.
- **Decisao:**
  - PROSSEGUIR → handoff para `03-trait-assessment-flow.md`.
  - AJUSTAR → loop interno (maximo 2 iteracoes).
  - PAUSAR → salvar estado, notificar usuario, agendar retorno.
  - ESCALAR → chief assume decisao final.
- **Output:** `decisao_gate` (prosseguir | ajustar | pausar | escalar), `justificativa`, `proximo_passo`.

## Quality Gates (checkpoints)

- [ ] Rapport estabelecido com status "estabelecido" ou "parcial" (nunca iniciar assessment com "nao_estabelecido").
- [ ] Score de qualidade de resposta >= 5/10.
- [ ] Baseline de confianca calculado com pelo menos 3 indicadores.
- [ ] Consentimento informado registrado.
- [ ] Decisao do gate documentada com justificativa.
- [ ] Fator de ajuste definido e pronto para uso nos assessments.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `rapport_status` | Enum | Log da sessao |
| `qualidade_resposta_score` | Numerico (0-10) | Todos os assessments |
| `baseline_confianca{}` | JSON | Contradiction-auditor, synthesis |
| `fator_de_ajuste` | Float | Todos os analistas |
| `vieses_detectados[]` | Array | Respondent-quality-auditor |
| `decisao_gate` | Enum | Chief, proximo workflow |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Rapport falha apos 2 tentativas | Rapport-architect muda abordagem (ex: de formal para informal). Se falhar novamente, pausar. |
| Desejabilidade social extrema detectada | Auditor inclui perguntas de validacao cruzada nos assessments subsequentes. Registrar alerta. |
| Usuario desiste durante calibracao | Salvar tudo coletado, enviar mensagem de acolhimento, oferecer retorno quando quiser. |
| Gatekeeper indeciso | Chief faz override com justificativa documentada. |

## Proximo Workflow

- **Decisao PROSSEGUIR:** `03-trait-assessment-flow.md`
- **Decisao PAUSAR:** Sessao suspensa, retorno ao `00-start-command-flow.md` quando reativada.
