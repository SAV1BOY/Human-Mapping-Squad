---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 04-type-style-assessment-flow"
agents: [motivation-chief, enneagram-analyst, sdi-analyst, reiss-analyst, mvpi-analyst]
quality_gates: [motivation-depth-checklist, motivation-type-alignment-checklist]
---

# Workflow: Assessment de Motivacao

## Trigger

Recebe handoff do `04-type-style-assessment-flow.md` apos conclusao dos tipos e estilos.

## Pre-condicoes

- Camadas de tracos e tipos concluidas.
- Dados de MBTI e DISC disponiveis para cruzamento.
- Camada de motivacao incluida em `camadas_ativas[]`.

## Sequencia

### Passo 1: Executar Eneagrama
- **Agente:** enneagram-analyst
- **Acao:** Identifica o tipo central do Eneagrama (1-9) com:
  - Tipo principal e asa dominante.
  - Nivel de saude/desenvolvimento (saudavel, medio, nao-saudavel).
  - Direcoes de integracao (crescimento) e desintegracao (estresse).
  - Instinto dominante: autopreservacao, social ou sexual/transmissao.
  - Tríade de centro: corpo (8,9,1), coracao (2,3,4), cabeca (5,6,7).
- **Decisao:** Se tipo tem confianca < 60%, considerar dois tipos candidatos e investigar com perguntas de desempate.
- **Output:** `enneagram_tipo`, `asa`, `nivel_saude`, `instinto_dominante`, `tricentro`, `confianca_eneagrama`.

### Passo 2: Executar SDI (Strength Deployment Inventory)
- **Agente:** sdi-analyst
- **Acao:** Avalia o sistema motivacional em tres estados:
  - **Quando tudo vai bem:** Motivacao primaria (Azul=Altruista, Vermelho=Assertivo, Verde=Analitico, ou combinacoes).
  - **Em conflito:** Sequencia de conflito (3 estagios de escalada).
  - **Overdone strengths:** Forcas usadas em excesso que se tornam fraquezas.
- **Decisao:** Se sequencia de conflito contradiz tipo Eneagrama sob estresse, marcar para investigacao.
- **Output:** `sdi_motivacao_primaria`, `sdi_sequencia_conflito[]`, `sdi_forcas_excessivas[]`.

### Passo 3: Executar Reiss Motivation Profile
- **Agente:** reiss-analyst
- **Acao:** Avalia os 16 desejos basicos de Reiss, classificando cada um como alto, medio ou baixo:
  - Poder, Independencia, Curiosidade, Aceitacao, Ordem, Economia, Honra, Idealismo, Contato Social, Familia, Status, Vinganca, Romance, Alimentacao, Atividade Fisica, Tranquilidade.
- **Decisao:** Priorizar os 5 desejos mais altos e os 3 mais baixos como definidores do perfil motivacional.
- **Output:** `reiss_16_desejos{}`, `top_5_altos[]`, `top_3_baixos[]`, `perfil_motivacional_reiss`.

### Passo 4: Executar MVPI e 12 Driving Forces
- **Agente:** mvpi-analyst
- **Acao:** Se profundidade = "Padrao" ou "Profundo":
  - **MVPI (Motives, Values, Preferences Inventory):** Avalia 10 escalas de valores: Reconhecimento, Poder, Hedonismo, Altruismo, Afiliacao, Tradicao, Seguranca, Comercio, Estetica, Ciencia.
  - **12 Driving Forces:** Agrupa em 6 dimensoes com polo positivo e negativo: Conhecimento, Utilidade, Ambiente, Outros, Poder, Metodologia.
- **Decisao:** Se profundidade = "Rapido", pular este passo.
- **Output:** `mvpi_valores{}`, `driving_forces_12{}`, `forcas_motrizes_dominantes[]`.

### Passo 5: Integracao Motivacional
- **Agente:** motivation-chief
- **Acao:** Cruza todos os instrumentos motivacionais e gera mapa integrado:
  - Convergencias entre Eneagrama, SDI, Reiss e MVPI/12DF.
  - Motivacao intrinseca vs extrinseca predominante.
  - Cruzamento com tipos (MBTI + DISC) para validacao.
  - Identifica o "motor principal" do respondente: o que realmente o move.
  - Classifica motivadores como: estavel (core), situacional (varia com contexto), ou emergente (em desenvolvimento).
- **Decisao:**
  - Se convergencia alta → alta confianca no mapa motivacional.
  - Se divergencias significativas → registrar para contradiction-audit com contexto de cada instrumento.
- **Output:** `mapa_motivacional_integrado{}`, `motor_principal`, `confianca_camada_motivacao`, `divergencias[]`.

## Quality Gates (checkpoints)

- [ ] Eneagrama identificado com tipo + asa + instinto.
- [ ] SDI com motivacao primaria e sequencia de conflito mapeadas.
- [ ] Reiss com pelo menos top 5 altos e top 3 baixos definidos.
- [ ] MVPI/12DF executados se profundidade >= Padrao.
- [ ] Motor principal identificado com justificativa.
- [ ] Cruzamento com tipos (MBTI/DISC) realizado.
- [ ] Confianca da camada >= 60%.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `enneagram_tipo` + detalhes | JSON | Synthesis, contradiction-auditor |
| `sdi_motivacao_primaria` + conflito | JSON | Synthesis, development-planner |
| `reiss_16_desejos{}` | JSON | Synthesis, career-fit |
| `mvpi_valores{}` + `driving_forces_12{}` | JSON | Synthesis |
| `mapa_motivacional_integrado{}` | JSON | Report-writer, synthesis |
| `motor_principal` | Texto | Report-writer |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Eneagrama ambiguo entre 2 tipos | Usar tricentro e instinto como desempate. Se persistir, registrar ambos. |
| SDI e Eneagrama divergem sobre comportamento sob estresse | Registrar ambas perspectivas. SDI foca em conflito interpessoal, Eneagrama em estresse geral. |
| Respondente tem dificuldade com conceito de "motivacao" | Reformular como: "O que te faz levantar da cama animado?" e "O que te drena energia?" |
| Reiss gera perfil plano (tudo medio) | Investigar desejabilidade social. Aplicar perguntas de forced-choice. |

## Proximo Workflow

`06-strengths-assessment-flow.md`
