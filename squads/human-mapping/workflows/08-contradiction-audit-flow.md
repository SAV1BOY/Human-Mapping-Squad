---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "OBRIGATORIO - Executado apos conclusao de todas as camadas de assessment (03-07)"
agents: [contradiction-auditor, readiness-gatekeeper]
quality_gates: [contradiction-resolution-checklist, confidence-recalculation-checklist]
---

# Workflow: Auditoria de Contradicoes

## Trigger

Executado OBRIGATORIAMENTE apos a conclusao de todas as camadas de assessment. Nao pode ser pulado independentemente da profundidade selecionada.

## Pre-condicoes

- Pelo menos camadas de tracos (03) e tipos (04) concluidas.
- Todas as divergencias registradas durante os assessments disponiveis.
- Baseline de confianca do respondente disponivel (do workflow 02).

## Sequencia

### Passo 1: Cruzar Todas as Camadas
- **Agente:** contradiction-auditor
- **Acao:** Coleta todos os outputs de todas as camadas e executa cruzamento sistematico:
  - Tracos (Big Five/HEXACO) vs Tipos (MBTI/DISC/Insights/PI).
  - Tipos vs Motivacao (Eneagrama/SDI/Reiss/MVPI).
  - Motivacao vs Forcas (Clifton/VIA/Belbin).
  - Forcas vs Carreira/Acao (RIASEC/Strong/Kolbe).
  - Tracos vs Motivacao (validacao direta).
  - Tipos vs Forcas (validacao direta).
  - Total: minimo 15 cruzamentos entre pares de instrumentos.
- **Output:** `matriz_cruzamento{}`, `total_cruzamentos`, `cruzamentos_realizados`.

### Passo 2: Detectar Conflitos
- **Agente:** contradiction-auditor
- **Acao:** Para cada cruzamento, aplica regras de deteccao:
  - **Contradicao direta:** Dois instrumentos dizem coisas opostas (ex: Big Five alta Extroversao + MBTI Introvertido).
  - **Inconsistencia parcial:** Instrumentos concordam na direcao mas divergem na intensidade.
  - **Lacuna:** Um instrumento sugere algo que outros nao captaram.
  - **Redundancia contraditoria:** Mesmo constructo medido de formas diferentes gera resultados diferentes.
- **Output:** `conflitos_detectados[]`, cada um com: `instrumentos_envolvidos`, `natureza`, `descricao`, `dados_brutos`.

### Passo 3: Classificar Severidade
- **Agente:** contradiction-auditor
- **Acao:** Classifica cada conflito detectado:
  - **Critica (vermelha):** Contradicao que invalida uma conclusao central do mapeamento. Deve ser resolvida.
  - **Alta (laranja):** Contradicao significativa que afeta confianca. Deve ser investigada.
  - **Media (amarela):** Inconsistencia parcial que pode ter explicacao contextual. Documentar.
  - **Baixa (verde):** Divergencia menor, provavelmente ruido ou diferenca de escopo entre instrumentos.
- **Decisao:** Se existem 3+ contradicoes criticas, interromper fluxo e escalar para o chief.
- **Output:** `conflitos_classificados[]`, `distribuicao_severidade{}`, `alerta_critico` (boolean).

### Passo 4: Investigar Causa
- **Agente:** contradiction-auditor
- **Acao:** Para cada conflito de severidade critica ou alta, investiga causas possiveis:
  - **Desejabilidade social:** Respondente deu respostas diferentes conforme a formulacao.
  - **Contexto diferente:** Um instrumento capturou o "eu no trabalho", outro o "eu real".
  - **Crescimento/transicao:** Pessoa esta mudando e instrumentos capturaram fases diferentes.
  - **Limitacao do instrumento:** Framework inadequado para este perfil especifico.
  - **Erro de interpretacao:** Analista interpretou dados de forma incorreta.
  - **Complexidade genuina:** Pessoa realmente tem aspectos contraditorios (normal em seres humanos).
- **Output:** `causas_investigadas[]`, cada uma com: `conflito_ref`, `causa_provavel`, `evidencia`, `confianca_causa`.

### Passo 5: Reconciliar
- **Agente:** contradiction-auditor
- **Acao:** Para cada conflito investigado, aplica estrategia de reconciliacao:
  - **Priorizar instrumento mais confiavel** para aquele constructo especifico.
  - **Contextualizar:** Manter ambos resultados, cada um valido em seu contexto.
  - **Reformular:** Criar narrativa que integra ambas perspectivas sem invalida-las.
  - **Descartar:** Se causa e erro claro, remover dado impreciso.
  - **Investigar mais:** Se inconclusivo, marcar para perguntas adicionais ao respondente.
- **Output:** `reconciliacoes[]`, `dados_descartados[]`, `perguntas_adicionais[]`.

### Passo 6: Atualizar Confianca
- **Agente:** contradiction-auditor
- **Acao:** Recalcula score de confianca de cada camada e geral:
  - Confianca original - penalidade por contradicoes nao resolvidas.
  - Confianca original + bonus por contradicoes resolvidas com evidencia.
  - Gera `mapa_confianca_atualizado{}` com score por camada e geral.
- **Output:** `mapa_confianca_atualizado{}`, `confianca_geral_pos_auditoria`.

### Passo 7: GATE - Aprovar para Sintese
- **Agente:** readiness-gatekeeper
- **Acao:** Avalia se o perfil esta pronto para sintese:
  - **APROVAR:** Confianca geral >= 65% e nenhuma contradicao critica aberta.
  - **APROVAR COM RESSALVAS:** Confianca 50-64% ou contradicoes altas nao resolvidas.
  - **REPROVAR:** Confianca < 50% ou contradicoes criticas abertas.
- **Decisao:**
  - APROVAR → handoff para `09-synthesis-and-integration-flow.md`.
  - APROVAR COM RESSALVAS → handoff com lista de ressalvas.
  - REPROVAR → escalar para chief. Opcoes: perguntas adicionais, reassessment parcial, ou aceitar limitacoes.
- **Output:** `decisao_gate_auditoria`, `ressalvas[]`, `proximo_passo`.

## Quality Gates (checkpoints)

- [ ] Todos os cruzamentos entre camadas realizados (minimo 15).
- [ ] Todos os conflitos detectados e classificados por severidade.
- [ ] Conflitos criticos e altos investigados com causa provavel.
- [ ] Estrategia de reconciliacao aplicada para cada conflito investigado.
- [ ] Confianca recalculada por camada e geral.
- [ ] Decisao do gate documentada com justificativa.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `matriz_cruzamento{}` | JSON | Synthesis, arquivo |
| `conflitos_classificados[]` | Array | Report-writer, synthesis |
| `reconciliacoes[]` | Array | Synthesis |
| `mapa_confianca_atualizado{}` | JSON | Todos os workflows subsequentes |
| `decisao_gate_auditoria` | Enum | Chief, synthesis |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Mais de 5 contradicoes criticas | Possivel problema sistemico. Revisar baseline do respondente. Considerar recalibracao. |
| Causa inconclusiva para contradicao critica | Chief decide: aceitar incerteza ou investir tempo em investigacao adicional. |
| Confianca geral cai abaixo de 30% | Sessao comprometida. Discutir com usuario se deseja continuar com limitacoes explicitas. |
| Readiness-gatekeeper e contradiction-auditor discordam | Chief faz arbitragem final. |

## Proximo Workflow

- **APROVAR / APROVAR COM RESSALVAS:** `09-synthesis-and-integration-flow.md`
- **REPROVAR:** Retorno a camadas especificas ou encerramento com relatorio parcial.
