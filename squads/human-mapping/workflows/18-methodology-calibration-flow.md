---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Periodico (mensal) ou quando feedback de acuracia indica necessidade"
agents: [chief, synthesis-architect, contradiction-auditor, respondent-quality-auditor]
quality_gates: [calibration-evidence-checklist, weight-adjustment-checklist, rubric-update-checklist]
---

# Workflow: Calibracao de Metodologia

## Trigger

Executado em duas situacoes:
1. **Periodicamente:** A cada 30 dias como manutencao preventiva.
2. **Sob demanda:** Quando feedback de acuracia de sessoes recentes indica desvios sistematicos.

## Pre-condicoes

- Minimo 5 sessoes concluidas desde a ultima calibracao.
- Feedback de acuracia disponivel (auto-avaliacao do respondente, feedback de stakeholders, ou resultados observados).
- Acesso ao historico de sessoes e decisoes de auditoria.

## Sequencia

### Passo 1: Coletar Feedback de Acuracia
- **Agente:** chief
- **Acao:** Reune todas as fontes de feedback desde a ultima calibracao:
  - **Auto-avaliacao do respondente:** "O relatorio te descreveu com precisao?" (escala 1-10).
  - **Feedback de stakeholders:** Se contratacao ou equipe, resultado observado vs previsto.
  - **Follow-ups:** Reavaliacao que mostrou mudanca inesperada.
  - **Reclamacoes ou questionamentos:** Pontos especificos contestados.
  - **Auditoria interna:** Contradicoes que nao foram bem resolvidas.
- **Output:** `feedback_coletado[]`, `media_acuracia_percebida`, `sessoes_analisadas`.

### Passo 2: Analisar Padroes de Erro
- **Agente:** contradiction-auditor
- **Acao:** Examina o feedback em busca de padroes sistematicos:
  - **Instrumento consistentemente impreciso?** Ex: DISC sempre diverge dos resultados observados.
  - **Camada com baixa confianca cronica?** Ex: motivacao sempre com score < 60%.
  - **Tipo de contradicao recorrente?** Ex: MBTI vs Big Five sempre conflita em Extroversao.
  - **Perfil de respondente com mais erros?** Ex: respondentes com alta desejabilidade social geram mais imprecisao.
  - **Vies sistematico?** Ex: squad tende a superestimar Conscienciosidade.
- **Output:** `padroes_erro[]`, cada um com: descricao, frequencia, impacto, hipotese de causa.

### Passo 3: Revisar Pesos dos Instrumentos
- **Agente:** synthesis-architect
- **Acao:** Reavalia a matriz de pesos usada na sintese (workflow 09):
  - Instrumentos com alta acuracia comprovada recebem peso maior.
  - Instrumentos com baixa acuracia recebem peso reduzido.
  - Instrumentos novos ou nao validados mantem peso conservador.
  - Ajuste e gradual: maximo +/- 10% por ciclo de calibracao para evitar overcorrection.
  - Documenta justificativa para cada ajuste.
- **Decisao:** Se um instrumento precisa de reducao > 30%, considerar remocao temporaria do assessment.
- **Output:** `matriz_pesos_anterior{}`, `matriz_pesos_atualizada{}`, `ajustes_realizados[]`.

### Passo 4: Atualizar Rubricas de Avaliacao
- **Agente:** respondent-quality-auditor
- **Acao:** Revisa as rubricas usadas para interpretar respostas:
  - **Calibracao de escalas:** Os pontos de corte para "alto", "medio", "baixo" estao adequados?
  - **Regras de classificacao:** As regras para identificar tipos/estilos estao gerando resultados precisos?
  - **Deteccao de vieses:** Os algoritmos de deteccao de desejabilidade social estao funcionando?
  - **Perguntas-piloto:** As perguntas de calibracao (workflow 02) estao discriminando bem?
  - Atualiza rubricas com base nos padroes de erro identificados.
- **Output:** `rubricas_anteriores{}`, `rubricas_atualizadas{}`, `mudancas_rubrica[]`.

### Passo 5: Testar Ajustes Retroativamente
- **Agente:** synthesis-architect
- **Acao:** Aplica novos pesos e rubricas retroativamente a 3-5 sessoes anteriores:
  - Os resultados teriam sido mais precisos com os novos pesos?
  - As contradicoes teriam sido melhor resolvidas?
  - O feedback do respondente teria sido melhor?
  - Calcula delta de acuracia: nova acuracia estimada vs anterior.
- **Decisao:**
  - Se delta positivo → confirmar ajustes.
  - Se delta neutro → manter ajustes como precaucao.
  - Se delta negativo → reverter ajustes e investigar mais.
- **Output:** `teste_retroativo_resultados{}`, `delta_acuracia`, `decisao_ajustes`.

### Passo 6: Documentar e Distribuir
- **Agente:** chief
- **Acao:** Finaliza calibracao:
  - Documenta todas as mudancas em changelog do squad.
  - Notifica todos os agentes sobre novos pesos e rubricas.
  - Atualiza versao da metodologia (minor version bump).
  - Agenda proxima calibracao periodica.
  - Registra metricas: acuracia media antes vs esperada apos ajuste.
- **Output:** `changelog_calibracao`, `versao_metodologia_atualizada`, `proxima_calibracao_data`.

## Quality Gates (checkpoints)

- [ ] Minimo 5 sessoes analisadas com feedback coletado.
- [ ] Padroes de erro identificados com evidencia (nao especulacao).
- [ ] Ajustes de peso limitados a +/- 10% por ciclo.
- [ ] Rubricas atualizadas com justificativa.
- [ ] Teste retroativo realizado em pelo menos 3 sessoes.
- [ ] Delta de acuracia positivo ou neutro (nunca negativo sem revisao).
- [ ] Changelog documentado e distribuido.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `matriz_pesos_atualizada{}` | JSON | Todos os workflows de assessment |
| `rubricas_atualizadas{}` | JSON | Todos os analistas |
| `changelog_calibracao` | Texto | Arquivo do squad |
| `padroes_erro[]` | Array | Treinamento, melhoria continua |
| `versao_metodologia_atualizada` | String | Metadata de todas as sessoes futuras |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Feedback insuficiente (<5 sessoes) | Adiar calibracao. Intensificar coleta de feedback nas proximas sessoes. |
| Nenhum padrao claro identificado | Normal em amostras pequenas. Registrar e acumular para proxima calibracao. |
| Teste retroativo mostra piora | Reverter ajustes imediatamente. Investigar se feedback original era enviesado. |
| Instrumento precisa ser removido | Nao remover sem substituto. Reduzir peso ao minimo e planejar substituicao. |

## Proximo Workflow

- Nenhum direto. Calibracao alimenta todos os workflows 03-09 na proxima sessao.
- `20-ralphloop-assessment-retro.md` pode complementar esta calibracao.
