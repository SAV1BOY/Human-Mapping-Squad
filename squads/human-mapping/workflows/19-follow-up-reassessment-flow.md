---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Data de reassessment sugerida atingida ou solicitacao do respondente"
agents: [chief, intake-orchestrator, synthesis-architect, contradiction-auditor, report-writer, development-planner]
quality_gates: [comparison-validity-checklist, change-detection-checklist, plan-update-checklist]
---

# Workflow: Reavaliacao e Follow-up

## Trigger

Ativado em duas situacoes:
1. Data de reassessment sugerida no plano de desenvolvimento (workflow 12) e atingida.
2. Respondente solicita reavaliacao apos periodo de desenvolvimento ou mudanca significativa.

## Pre-condicoes

- Sessao anterior completa com mapa unificado disponivel.
- Intervalo minimo de 3 meses desde o ultimo assessment.
- Respondente disponivel para nova sessao.

## Sequencia

### Passo 1: Recuperar Perfil Anterior
- **Agente:** chief
- **Acao:** Carrega todos os dados da sessao anterior:
  - Mapa unificado anterior.
  - Plano de desenvolvimento (se existente) com metas definidas.
  - Mapa de confianca anterior.
  - Contradicoes e reconciliacoes anteriores.
  - Contexto anterior (organizacional e pessoal).
  - Nota: NAO mostrar perfil anterior ao respondente antes do reassessment (evitar vies de confirmacao).
- **Output:** `perfil_anterior{}` carregado em modo somente-leitura.

### Passo 2: Executar Reassessment
- **Agente:** intake-orchestrator
- **Acao:** Inicia nova sessao de assessment com ajustes:
  - Calibracao (workflow 02) simplificada se rapport ja estabelecido.
  - Mesmas camadas e profundidade da sessao anterior (para comparabilidade).
  - Mesmos instrumentos (para comparabilidade).
  - Adicionar perguntas especificas sobre mudancas percebidas pelo respondente.
  - Executar workflows 03-08 normalmente.
- **Decisao:** Se respondente mudou significativamente de contexto (ex: novo emprego), ajustar contexto antes.
- **Output:** `perfil_novo{}` (mapa unificado da nova sessao).

### Passo 3: Comparar Perfis
- **Agente:** synthesis-architect
- **Acao:** Compara perfil anterior vs novo dimensao por dimensao:
  - **Delta por fator Big Five:** Mudanca em cada fator (ex: Conscienciosidade subiu de 65 para 72).
  - **Mudanca de tipo:** MBTI/DISC mudou? (raro, mas possivel).
  - **Evolucao motivacional:** Eneagrama nivel de saude mudou? Reiss se alterou?
  - **Novas forcas emergentes:** Talentos Clifton que subiram no ranking.
  - **Mudancas em Kolbe/RIASEC:** Modo de acao ou interesses se deslocaram?
  - Calcula significancia de cada mudanca (dentro de margem de erro ou real).
- **Output:** `analise_comparativa{}`, `deltas_por_dimensao{}`, `mudancas_significativas[]`, `mudancas_marginais[]`.

### Passo 4: Detectar Mudancas Significativas
- **Agente:** contradiction-auditor
- **Acao:** Valida se mudancas detectadas sao reais ou artefatos:
  - **Mudanca real:** Evidencia de desenvolvimento genuino. Comportamento observavel mudou.
  - **Efeito de humor:** Respondente estava em estado emocional diferente. Nao e mudanca duradoura.
  - **Aprendizado do teste:** Respondente aprendeu a "responder melhor" sem mudar de fato.
  - **Mudanca de contexto:** Ambiente mudou, nao a pessoa (ex: novo emprego altera DISC adaptado).
  - **Erro de medicao:** Variacao dentro da margem de erro do instrumento.
- **Decisao:** Classificar cada mudanca como: confirmada, provavel, incerta, artefato.
- **Output:** `mudancas_classificadas[]`, cada uma com status e evidencia.

### Passo 5: Avaliar Progresso do Plano de Desenvolvimento
- **Agente:** development-planner
- **Acao:** Se existia plano de desenvolvimento, avalia progresso:
  - Para cada meta SMART: atingida, em progresso, estagnada, abandonada.
  - Correlacao entre metas trabalhadas e mudancas detectadas no perfil.
  - Estrategias que funcionaram vs que nao funcionaram.
  - Novas areas de desenvolvimento identificadas pelo novo perfil.
  - Score geral de progresso no desenvolvimento.
- **Decisao:** Se metas estagnadas, investigar causa: barreira externa, estrategia inadequada, ou meta irrealista.
- **Output:** `avaliacao_progresso{}`, `metas_status[]`, `estrategias_eficazes[]`, `estrategias_ineficazes[]`.

### Passo 6: Atualizar Plano de Desenvolvimento
- **Agente:** development-planner
- **Acao:** Gera versao atualizada do plano:
  - Metas atingidas: celebrar e remover.
  - Metas em progresso: manter com ajustes se necessario.
  - Metas estagnadas: reformular estrategia ou ajustar meta.
  - Novas metas: adicionar baseado em novas descobertas.
  - Novo cronograma e mecanismos de acompanhamento.
  - Nova data sugerida para proxima reavaliacao.
- **Output:** `plano_desenvolvimento_v2{}`, `data_proxima_reavaliacao`.

### Passo 7: Gerar Relatorio de Evolucao
- **Agente:** report-writer
- **Acao:** Redige documento de evolucao:
  - Resumo comparativo: antes vs agora (visual, lado a lado).
  - Mudancas significativas destacadas com interpretacao.
  - Progresso no plano de desenvolvimento.
  - O que permaneceu estavel (core do perfil).
  - Novas descobertas nao previstas.
  - Plano atualizado com proximos passos.
  - Celebracoes: conquistas e crescimento reconhecidos.
- **Output:** `relatorio_evolucao_final`.

## Quality Gates (checkpoints)

- [ ] Perfil anterior carregado sem exposicao ao respondente antes do reassessment.
- [ ] Mesmos instrumentos e profundidade usados para comparabilidade.
- [ ] Comparacao dimensao a dimensao realizada.
- [ ] Mudancas classificadas (real vs artefato).
- [ ] Progresso do plano avaliado meta a meta.
- [ ] Plano atualizado com novas metas e cronograma.
- [ ] Relatorio de evolucao inclui celebracao de conquistas.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_evolucao_final` | Markdown/PDF | Respondente |
| `analise_comparativa{}` | JSON | Arquivo, calibracao |
| `plano_desenvolvimento_v2{}` | JSON | Follow-up |
| `mudancas_classificadas[]` | Array | Calibracao metodologica (workflow 18) |
| `data_proxima_reavaliacao` | Data | Agendamento |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Perfil anterior nao encontrado | Tratar como primeira avaliacao. Registrar para correcao de arquivo. |
| Intervalo < 3 meses | Alertar que mudancas significativas sao improvaveis. Prosseguir se respondente insistir. |
| Todas as mudancas sao artefatos | Comunicar que perfil esta estável. Focar em refinar estrategias de desenvolvimento. |
| Respondente frustrado com falta de progresso | Normalizar. Desenvolvimento comportamental e lento. Revisar estrategias, nao o respondente. |

## Proximo Workflow

- `18-methodology-calibration-flow.md` (alimentar com dados de evolucao)
- Proximo ciclo de reassessment na data sugerida.
