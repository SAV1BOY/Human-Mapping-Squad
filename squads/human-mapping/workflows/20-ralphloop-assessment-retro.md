---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "A cada 10 sessoes concluidas ou mensalmente (o que vier primeiro)"
agents: [chief, synthesis-architect, contradiction-auditor, respondent-quality-auditor]
quality_gates: [retro-completeness-checklist, improvement-actionability-checklist]
---

# Workflow: Retrospectiva e Aprendizado (RalphLoop)

## Trigger

Ativado automaticamente apos 10 sessoes concluidas ou a cada 30 dias (o que ocorrer primeiro). Tambem pode ser acionado manualmente pelo chief quando necessario.

## Pre-condicoes

- Minimo 3 sessoes concluidas desde a ultima retro (se menos, adiar).
- Logs de todas as sessoes acessiveis.
- Feedback de respondentes disponivel (quando coletado).

## Sequencia

### Passo 1: Coletar Dados das Ultimas 10 Sessoes
- **Agente:** chief
- **Acao:** Compila metricas e dados das sessoes recentes:
  - **Metricas quantitativas:**
    - Tempo medio por sessao (total e por camada).
    - Score medio de confianca geral.
    - Numero de contradicoes criticas por sessao.
    - Taxa de resolucao de contradicoes.
    - Score medio de feedback do respondente.
    - Taxa de conclusao (sessoes finalizadas vs abandonadas).
    - Distribuicao de objetivos (desenvolvimento, lideranca, contratacao, etc.).
  - **Metricas qualitativas:**
    - Reclamacoes ou elogios recorrentes.
    - Momentos onde o fluxo travou ou ficou confuso.
    - Decisoes de gate que geraram duvida.
- **Output:** `metricas_periodo{}`, `sessoes_analisadas[]`, `periodo_analise`.

### Passo 2: Identificar Padroes
- **Agente:** contradiction-auditor
- **Acao:** Analisa dados em busca de padroes positivos e negativos:
  - **Padroes positivos (manter):**
    - Instrumentos com alta acuracia consistente.
    - Etapas do fluxo que funcionam bem (baixo tempo, alta confianca).
    - Combinacoes de instrumentos que geram mais insight.
    - Tipos de respondente onde o processo funciona melhor.
  - **Padroes negativos (melhorar):**
    - Etapas que consistentemente demoram mais que o esperado.
    - Instrumentos com baixa acuracia recorrente.
    - Tipos de contradição que nunca sao bem resolvidos.
    - Perfis de respondente onde o processo falha mais.
    - Pontos de abandono frequentes.
  - **Padroes emergentes (investigar):**
    - Tendencias novas nao previstas pela metodologia.
    - Solicitacoes recorrentes nao atendidas pelo fluxo atual.
- **Output:** `padroes_positivos[]`, `padroes_negativos[]`, `padroes_emergentes[]`.

### Passo 3: Avaliar Performance dos Agentes
- **Agente:** chief
- **Acao:** Revisa desempenho de cada agente do squad:
  - **Tempo de resposta:** Agente esta dentro do SLA esperado?
  - **Qualidade do output:** Outputs sao consistentes e completos?
  - **Taxa de retrabalho:** Quantas vezes o output precisou ser refeito?
  - **Colaboracao:** Handoffs entre agentes sao fluidos?
  - **Especializacao:** Agente esta operando dentro de sua competencia?
  - Gera scorecard por agente (nao punitivo, foco em melhoria).
- **Output:** `scorecard_agentes{}`, `agentes_destaque[]`, `agentes_necessitando_ajuste[]`.

### Passo 4: Gerar Insights de Melhoria
- **Agente:** synthesis-architect
- **Acao:** Transforma padroes em insights acionaveis:
  - Para cada padrao negativo: hipotese de causa raiz + proposta de melhoria.
  - Para cada padrao positivo: como amplificar e replicar.
  - Para cada padrao emergente: como incorporar ou investigar mais.
  - Prioriza insights por impacto potencial x esforco de implementacao.
  - Classifica em: quick win, projeto medio, transformacao grande.
- **Output:** `insights_melhoria[]`, cada um com: descricao, impacto, esforco, prioridade, acao proposta.

### Passo 5: Atualizar Protocolo e Documentacao
- **Agente:** chief
- **Acao:** Implementa melhorias aprovadas:
  - **Quick wins (implementar agora):**
    - Ajustar tempos estimados nos workflows.
    - Corrigir formulacoes de perguntas problematicas.
    - Atualizar checklists de quality gates.
  - **Projetos medios (planejar para proximo ciclo):**
    - Adicionar novo instrumento ou remover ineficaz.
    - Reestruturar sequencia de passos em um workflow.
    - Criar novas regras de deteccao de vieses.
  - **Transformacoes grandes (roadmap):**
    - Redesenho de workflow completo.
    - Novo tipo de relatorio ou output.
    - Integracao com novos squads.
- **Decisao:** Quick wins implementados imediatamente. Medios e grandes adicionados ao backlog.
- **Output:** `melhorias_implementadas[]`, `backlog_melhorias[]`, `roadmap_atualizado`.

### Passo 6: Registrar Aprendizados
- **Agente:** respondent-quality-auditor
- **Acao:** Documenta aprendizados em base de conhecimento do squad:
  - **Lessons learned:** O que aprendemos neste ciclo.
  - **Anti-patterns:** O que nao fazer (com exemplos reais anonimizados).
  - **Best practices atualizadas:** Praticas que comprovadamente funcionam.
  - **Benchmark atualizado:** Metricas de referencia para o proximo ciclo.
  - **Perguntas abertas:** O que ainda nao sabemos e queremos investigar.
- **Output:** `base_conhecimento_atualizada`, `lessons_learned[]`, `anti_patterns[]`.

### Passo 7: Comunicar e Alinhar
- **Agente:** chief
- **Acao:** Distribui resultados da retro para todo o squad:
  - Resumo executivo da retro (1 pagina).
  - Destaques positivos (celebrar conquistas).
  - Melhorias implementadas e planejadas.
  - Novas expectativas e benchmarks.
  - Data da proxima retro.
  - Convite para feedback adicional.
- **Output:** `comunicado_retro`, `proxima_retro_data`.

## Quality Gates (checkpoints)

- [ ] Minimo 3 sessoes analisadas com metricas completas.
- [ ] Padroes identificados com evidencia (nao opiniao).
- [ ] Scorecard de agentes gerado com foco construtivo.
- [ ] Insights priorizados por impacto x esforco.
- [ ] Quick wins implementados imediatamente.
- [ ] Base de conhecimento atualizada com lessons learned.
- [ ] Comunicado distribuido para todo o squad.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `metricas_periodo{}` | JSON | Dashboard do squad |
| `padroes_positivos[]` + `negativos[]` + `emergentes[]` | Array | Base de conhecimento |
| `scorecard_agentes{}` | JSON | Chief, agentes individuais |
| `insights_melhoria[]` | Array | Backlog de melhoria |
| `melhorias_implementadas[]` | Array | Changelog |
| `base_conhecimento_atualizada` | Texto | Todos os agentes |
| `comunicado_retro` | Texto | Squad inteiro |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Menos de 3 sessoes no periodo | Adiar retro para o proximo ciclo. Registrar motivo (baixo volume vs problemas). |
| Nenhum feedback de respondente disponivel | Prosseguir com metricas quantitativas. Priorizar melhoria na coleta de feedback. |
| Equipe resiste a mudancas propostas | Chief explica evidencia e impacto. Se resistencia persiste, implementar como piloto em 2-3 sessoes. |
| Muitas melhorias identificadas (>10) | Forcar priorizacao: top 3 quick wins + top 2 projetos medios. Resto vai para backlog. |

## Proximo Workflow

- `18-methodology-calibration-flow.md` (calibracao tecnica complementa a retro processual).
- Proxima retro agendada conforme gatilho (10 sessoes ou 30 dias).
