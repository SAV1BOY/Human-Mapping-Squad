---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 03-trait-assessment-flow com gate aprovado"
agents: [type-style-chief, mbti-analyst, disc-analyst, insights-analyst, pi-analyst, complementary-style-analyst]
quality_gates: [type-trait-separation-checklist, style-convergence-checklist]
---

# Workflow: Assessment de Tipos e Estilos

## Trigger

Recebe handoff do `03-trait-assessment-flow.md` com todos os outputs de tracos disponíveis.

## Pre-condicoes

- Camada de tracos concluida (Big Five + HEXACO no minimo).
- Respondente ainda engajado na sessao.
- Camada de tipos incluida em `camadas_ativas[]`.

## Sequencia

### Passo 1: Estabelecer Separacao Tipo vs Traco
- **Agente:** type-style-chief
- **Acao:** Briefing interno para todos os analistas de tipo/estilo. Reforcar a distincao fundamental:
  - **Tracos** = dimensoes continuas, graus de intensidade (ex: Big Five).
  - **Tipos** = categorias qualitativas, preferencias naturais (ex: MBTI).
  - Tipos NAO sao simplificacoes de tracos. Sao lentes complementares.
- **Output:** `framework_separacao_ativo`, confirmacao de todos os analistas.

### Passo 2: Executar MBTI (Funcoes Cognitivas)
- **Agente:** mbti-analyst
- **Acao:** Avalia as 4 dicotomias (E/I, S/N, T/F, J/P) e as 8 funcoes cognitivas. Prioriza funcoes cognitivas sobre letras isoladas. Identifica funcao dominante, auxiliar, terciaria e inferior.
- **Decisao:** Se tipo MBTI parece contradizer Big Five (ex: INTJ com alta Extroversao), registrar como ponto de investigacao, NAO como erro.
- **Output:** `mbti_tipo`, `funcoes_cognitivas_stack[]`, `confianca_tipo`, `pontos_investigacao[]`.

### Passo 3: Executar DISC
- **Agente:** disc-analyst
- **Acao:** Avalia os 4 fatores DISC: Dominancia, Influencia, Estabilidade, Conformidade. Identifica perfil natural (quem a pessoa e) vs perfil adaptado (como age no trabalho). Calcula diferenca entre ambos.
- **Decisao:** Se diferenca natural vs adaptado > 30%, sinalizar possivel estresse ou desalinhamento cultural.
- **Output:** `disc_natural{}`, `disc_adaptado{}`, `gap_adaptacao`, `alerta_estresse` (boolean).

### Passo 4: Executar Insights Discovery
- **Agente:** insights-analyst
- **Acao:** Mapeia as 4 energias de cor (Azul Frio, Verde Terra, Amarelo Sol, Vermelho Fogo) e suas combinacoes. Gera perfil de persona consciente vs persona menos consciente.
- **Output:** `insights_perfil{}`, `energia_dominante`, `energia_sombra`, `persona_consciente`, `persona_menos_consciente`.

### Passo 5: Executar Predictive Index (PI)
- **Agente:** pi-analyst
- **Acao:** Avalia os 4 fatores PI: Dominancia, Extroversao, Paciencia, Formalidade. Gera Reference Profile mais proximo entre os 17 perfis de referencia.
- **Decisao:** Se Reference Profile diverge significativamente do DISC/Insights, marcar para reconciliacao.
- **Output:** `pi_fatores{}`, `reference_profile`, `divergencias_com_disc[]`.

### Passo 6: Executar Instrumentos Complementares (FIRO/PCM/Birkman)
- **Agente:** complementary-style-analyst
- **Acao:** Apenas se profundidade = "Profundo". Avalia:
  - **FIRO-B:** Necessidades interpessoais (inclusao, controle, afeto) — expressa vs desejada.
  - **PCM (Process Communication Model):** Tipo de base e fase atual.
  - **Birkman:** Interesses, estilo usual, necessidades subjacentes, comportamento sob estresse.
- **Decisao:** Se profundidade != "Profundo", pular este passo.
- **Output:** `firo_b_perfil{}`, `pcm_tipo_base`, `pcm_fase`, `birkman_perfil{}`.

### Passo 7: Convergencia e Validacao
- **Agente:** type-style-chief
- **Acao:** Cruza todos os instrumentos de tipo/estilo e avalia convergencia:
  - Mapear correspondencias entre MBTI, DISC, Insights e PI.
  - Identificar areas de forte convergencia (alta confianca).
  - Identificar areas de divergencia (requer investigacao).
  - Garantir que nenhum tipo foi confundido com traco.
- **Output:** `mapa_convergencia_tipos{}`, `confianca_camada_tipos`, `divergencias_para_auditoria[]`.

## Quality Gates (checkpoints)

- [ ] Separacao tipo vs traco documentada e respeitada em todos os instrumentos.
- [ ] MBTI inclui analise de funcoes cognitivas (nao apenas 4 letras).
- [ ] DISC diferencia perfil natural de adaptado.
- [ ] Pelo menos 3 instrumentos de tipo/estilo executados.
- [ ] Mapa de convergencia gerado com areas de acordo e divergencia.
- [ ] Confianca da camada >= 60%.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `mbti_tipo` + `funcoes_cognitivas_stack[]` | JSON | Synthesis, contradiction-auditor |
| `disc_natural{}` + `disc_adaptado{}` | JSON | Synthesis, report-writer |
| `insights_perfil{}` | JSON | Synthesis |
| `pi_fatores{}` + `reference_profile` | JSON | Synthesis |
| `firo_b_perfil{}`, `pcm_*`, `birkman_perfil{}` | JSON | Synthesis (se profundo) |
| `mapa_convergencia_tipos{}` | JSON | Contradiction-auditor |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| MBTI ambiguo entre dois tipos | Registrar ambos como candidatos com probabilidades. Funcoes cognitivas como desempate. |
| DISC natural e adaptado identicos | Verificar se respondente entendeu a diferenca. Pode indicar alto alinhamento ou incompreensao. |
| PI diverge de todos os outros instrumentos | Marcar PI com confianca reduzida. Investigar no contradiction-audit. |
| Respondente cansado apos muitos instrumentos | Pausar, oferecer intervalo, retomar com instrumentos restantes depois. |

## Proximo Workflow

`05-motivation-assessment-flow.md`
