---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Handoff do 02-respondent-calibration ou 00-start-command-flow (modo rapido)"
agents: [trait-chief, big-five-analyst, hexaco-analyst, facet-analyst, workplace-trait-translator]
quality_gates: [trait-confidence-checklist, cross-instrument-consistency-checklist]
---

# Workflow: Assessment de Tracos de Personalidade

## Trigger

Recebe handoff do workflow de calibracao (ou diretamente do start no modo rapido) com `sessao_completa{}`, `baseline_confianca{}` e `fator_de_ajuste`.

## Pre-condicoes

- Calibracao do respondente concluida (ou pulada no modo rapido).
- Fator de ajuste disponivel para correcao de vieses.
- Camada de tracos incluida em `camadas_ativas[]`.

## Sequencia

### Passo 1: Executar Big Five (OCEAN)
- **Agente:** big-five-analyst
- **Acao:** Aplica framework Big Five avaliando os cinco grandes fatores:
  - Abertura a Experiencia (Openness)
  - Conscienciosidade (Conscientiousness)
  - Extroversao (Extraversion)
  - Amabilidade (Agreeableness)
  - Neuroticismo (Neuroticism)
- **Decisao:** Aplicar `fator_de_ajuste` nos scores brutos. Se qualquer fator tem confianca < 60%, marcar para investigacao adicional.
- **Output:** `big_five_scores{}`, `confianca_por_fator{}`, `fatores_incertos[]`.

### Passo 2: Executar HEXACO
- **Agente:** hexaco-analyst
- **Acao:** Aplica framework HEXACO adicionando a sexta dimensao (Honestidade-Humildade) e refinando os fatores compartilhados com Big Five. Compara resultados com o Passo 1.
- **Decisao:**
  - Se HEXACO confirma Big Five (correlacao > 0.7) → confianca aumenta.
  - Se divergencia significativa → marcar para reconciliacao no `08-contradiction-audit`.
- **Output:** `hexaco_scores{}`, `honestidade_humildade_score`, `divergencias_big_five[]`.

### Passo 3: Decidir Necessidade de Facetas
- **Agente:** trait-chief
- **Acao:** Avalia se facetas detalhadas sao necessarias com base em:
  - Profundidade selecionada (Profundo = sempre; Padrao = se divergencias; Rapido = nunca).
  - Numero de fatores com confianca < 70%.
  - Presenca de divergencias Big Five vs HEXACO.
- **Decisao:**
  - Facetas necessarias → Passo 4.
  - Facetas desnecessarias → Passo 5.
- **Output:** `facetas_necessarias` (boolean), `justificativa`.

### Passo 4: Executar Analise de Facetas
- **Agente:** facet-analyst
- **Acao:** Aprofunda cada fator em suas facetas especificas. Exemplo para Conscienciosidade: auto-eficacia, organizacao, senso de dever, esforco por realizacao, autodisciplina, cautela. Maximo de 6 facetas por fator, apenas para fatores priorizados.
- **Decisao:** Se faceta contradiz o fator pai, registrar para auditoria de contradicoes.
- **Output:** `facetas_detalhadas{}`, `contradicoes_faceta_fator[]`.

### Passo 5: Traduzir para Contexto de Trabalho
- **Agente:** workplace-trait-translator
- **Acao:** Converte scores de tracos em implicacoes praticas para o ambiente de trabalho:
  - Estilo de comunicacao derivado dos tracos.
  - Preferencias de ambiente de trabalho.
  - Riscos comportamentais sob pressao.
  - Pontos cegos potenciais.
  - Compatibilidade com culturas organizacionais tipicas.
- **Output:** `perfil_tracos_workplace{}`, `implicacoes_praticas[]`.

### Passo 6: GATE - Confianca nos Tracos
- **Agente:** trait-chief
- **Acao:** Consolida todos os resultados e avalia confianca geral da camada de tracos:
  - Confianca media dos fatores >= 70%.
  - Divergencias Big Five vs HEXACO reconciliadas ou documentadas.
  - Facetas consistentes com fatores.
  - Traducao workplace coerente com scores.
- **Decisao:**
  - Confianca >= 70% → aprovar e seguir.
  - Confianca 50-69% → aprovar com ressalvas documentadas.
  - Confianca < 50% → solicitar perguntas adicionais ao respondente.
- **Output:** `confianca_camada_tracos`, `status_gate` (aprovado | aprovado_com_ressalvas | reprovar), `ressalvas[]`.

## Quality Gates (checkpoints)

- [ ] Big Five completo com scores para todos os 5 fatores.
- [ ] HEXACO completo com score de Honestidade-Humildade.
- [ ] Divergencias entre instrumentos documentadas.
- [ ] Facetas executadas se necessario (ou justificativa para pular).
- [ ] Traducao workplace realizada com pelo menos 3 implicacoes praticas.
- [ ] Confianca geral da camada >= 50% (minimo para prosseguir).

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `big_five_scores{}` | JSON | Synthesis, contradiction-auditor |
| `hexaco_scores{}` | JSON | Synthesis, contradiction-auditor |
| `facetas_detalhadas{}` | JSON | Synthesis (se aplicavel) |
| `perfil_tracos_workplace{}` | JSON | Report-writer, development-planner |
| `confianca_camada_tracos` | Float | Chief, synthesis |
| `divergencias[]` | Array | Contradiction-auditor |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Score Big Five inconsistente | HEXACO serve como validacao cruzada. Se ambos inconsistentes, solicitar mais dados. |
| Respondente nao entende terminologia de tracos | Workplace-trait-translator reformula em linguagem cotidiana. |
| Confianca abaixo de 50% apos retry | Prosseguir com flag de baixa confianca. Relatorio final indicara limitacao. |
| Facet-analyst detecta contradicao grave | Registrar para `08-contradiction-audit-flow.md` com prioridade alta. |

## Proximo Workflow

`04-type-style-assessment-flow.md`
