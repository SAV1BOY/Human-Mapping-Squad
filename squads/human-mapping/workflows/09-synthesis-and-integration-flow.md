---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Gate aprovado no 08-contradiction-audit-flow"
agents: [synthesis-architect, chief]
quality_gates: [integration-completeness-checklist, weighting-validity-checklist]
---

# Workflow: Sintese e Integracao

## Trigger

Recebe handoff do `08-contradiction-audit-flow.md` com decisao APROVAR ou APROVAR COM RESSALVAS.

## Pre-condicoes

- Todas as camadas de assessment concluidas (03-07).
- Auditoria de contradicoes finalizada com reconciliacoes aplicadas.
- Mapa de confianca atualizado disponivel.
- Ressalvas documentadas (se houver).

## Sequencia

### Passo 1: Coletar Todos os Outputs
- **Agente:** synthesis-architect
- **Acao:** Reune todos os outputs finais de cada camada:
  - Tracos: Big Five, HEXACO, facetas, traducao workplace.
  - Tipos: MBTI, DISC, Insights, PI, complementares.
  - Motivacao: Eneagrama, SDI, Reiss, MVPI/12DF.
  - Forcas: Clifton, VIA, Belbin.
  - Carreira/Acao: RIASEC, Strong, Kolbe.
  - Auditoria: reconciliacoes, mapa de confianca.
  - Contexto: objetivo, organizacional, pessoal, profundidade.
- **Output:** `pacote_completo_dados{}` consolidado.

### Passo 2: Definir Pesos por Camada
- **Agente:** synthesis-architect
- **Acao:** Atribui pesos a cada camada e instrumento baseado em:
  - Confianca pos-auditoria de cada camada.
  - Relevancia para o objetivo do mapeamento.
  - Numero de instrumentos convergentes por camada.
  - Qualidade das respostas do respondente em cada camada.
  - Contexto: se objetivo e lideranca, pesar mais tipos e motivacao; se carreira, pesar mais RIASEC e forcas.
- **Decisao:** Se uma camada tem confianca < 40%, reduzir peso a quase zero e documentar exclusao.
- **Output:** `matriz_pesos{}`, `justificativa_pesos{}`.

### Passo 3: Construir Narrativa Central
- **Agente:** synthesis-architect
- **Acao:** Cria a narrativa unificada do perfil respondendo:
  - **Quem e essa pessoa?** (essencia = tracos + tipos)
  - **O que a move?** (motor = motivacao)
  - **No que ela e excelente?** (genialidade = forcas)
  - **Como ela age?** (modo = Kolbe + DISC)
  - **Onde ela prospera?** (ambiente = RIASEC + Strong + contexto)
  - **Quais sao seus pontos cegos?** (riscos = zonas de risco + sombras)
  - **Como ela se comporta sob pressao?** (estresse = Eneagrama desintegracao + SDI conflito + DISC gap)
- **Decisao:** Se alguma pergunta nao pode ser respondida com confianca, marcar como "dados insuficientes".
- **Output:** `narrativa_central{}` com 7 dimensoes respondidas.

### Passo 4: Gerar Mapa Unificado
- **Agente:** synthesis-architect
- **Acao:** Produz o mapa comportamental unificado com estrutura:
  - **Camada 1 - Fundacao:** Tracos estaveis (Big Five/HEXACO ponderado).
  - **Camada 2 - Preferencias:** Tipos e estilos (MBTI/DISC/Insights ponderado).
  - **Camada 3 - Combustivel:** Motivacoes e valores (Eneagrama/SDI/Reiss ponderado).
  - **Camada 4 - Capacidades:** Forcas e talentos (Clifton/VIA/Belbin ponderado).
  - **Camada 5 - Direcao:** Interesses e modo de acao (RIASEC/Kolbe ponderado).
  - **Meta-camada:** Confianca, ressalvas, contradicoes residuais.
- **Output:** `mapa_unificado{}` com todas as camadas integradas e ponderadas.

### Passo 5: Validacao Cruzada Final
- **Agente:** chief
- **Acao:** Revisa o mapa unificado verificando:
  - Coerencia interna da narrativa (faz sentido como pessoa inteira?).
  - Pesos aplicados corretamente e justificados.
  - Ressalvas da auditoria refletidas no mapa.
  - Nenhuma camada sub-representada sem justificativa.
  - Mapa responde ao objetivo original do usuario.
- **Decisao:**
  - Aprovado → seguir para geracao de relatorios.
  - Ajustes necessarios → retornar ao synthesis-architect com feedback especifico.
- **Output:** `validacao_chief` (aprovado | ajustar), `feedback_ajustes[]`.

### Passo 6: Finalizar e Distribuir
- **Agente:** synthesis-architect
- **Acao:** Aplica ajustes do chief (se houver). Empacota mapa final e distribui para workflows de geracao de relatorios conforme objetivo:
  - Sempre: `10-executive-report` + `11-deep-report`.
  - Se desenvolvimento: + `12-development-plan`.
  - Se lideranca: + `13-leadership-profile`.
  - Se contratacao: + `14-hiring-assessment`.
  - Se equipe: + `15-team-composition`.
  - Se carreira: + `16-career-guidance`.
- **Output:** `mapa_final{}`, `workflows_relatorio_ativados[]`.

## Quality Gates (checkpoints)

- [ ] Todos os outputs de todas as camadas coletados e referenciados.
- [ ] Pesos definidos com justificativa para cada camada e instrumento.
- [ ] Narrativa central responde as 7 dimensoes (ou marca como insuficiente).
- [ ] Mapa unificado com 5 camadas + meta-camada completo.
- [ ] Validacao do chief realizada.
- [ ] Destino dos relatorios definido conforme objetivo.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `mapa_unificado{}` | JSON | Report-writer, development-planner, todos os workflows 10-16 |
| `narrativa_central{}` | JSON | Report-writer |
| `matriz_pesos{}` | JSON | Arquivo, calibracao |
| `workflows_relatorio_ativados[]` | Array | Chief para orquestracao |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Narrativa nao faz sentido como pessoa inteira | Synthesis-architect revisa pesos e reconciliacoes. Pode indicar auditoria incompleta. |
| Chief reprova mapa 2+ vezes | Escalar: reunir synthesis-architect + contradiction-auditor para revisao conjunta. |
| Camada inteira excluida por baixa confianca | Documentar claramente no relatorio. Sugerir reassessment futuro para aquela camada. |
| Objetivo original nao respondido pelo mapa | Revisitar definicao de objetivo (workflow 01). Pode exigir camadas adicionais. |

## Proximo Workflow

- `10-executive-report-generation.md` (sempre)
- `11-deep-report-generation.md` (sempre)
- Workflows especializados conforme objetivo (12-16)
