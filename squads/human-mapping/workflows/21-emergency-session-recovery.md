---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Sessao interrompida por falha tecnica, ausencia do respondente ou erro critico no pipeline"
agents: [chief, synthesis-architect, respondent-quality-auditor]
quality_gates: [data-integrity-check, confidence-recalibration]
---

# Workflow: Recuperacao de Sessao de Emergencia

## Trigger

Ativado quando uma sessao de mapeamento e interrompida de forma nao planejada. Exemplos:
- Falha tecnica (perda de conexao, crash de sistema, perda de dados)
- Respondente precisa interromper abruptamente (emergencia pessoal, conflito de agenda)
- Erro critico detectado no pipeline que invalida dados coletados
- Sessao excede o tempo disponivel e precisa ser pausada

## Objetivo

Retomar a sessao do ponto de interrupcao com minima perda de dados e maxima integridade do mapeamento. Ajustar confidence scores para refletir o gap causado pela interrupcao.

## Etapas de Recuperacao

### Etapa 1: Avaliar a Situacao (Imediato — 0 a 15 min apos interrupcao)

**Responsavel:** Chief ou agente que detectou a interrupcao

1. **Identificar o tipo de interrupcao:**
   - [ ] Tecnica (dados podem estar corrompidos)
   - [ ] Logistica (respondente indisponivel, dados intactos)
   - [ ] Qualidade (dados coletados sao invalidos)
   - [ ] Temporal (sessao nao concluida por falta de tempo)

2. **Inventariar o que foi preservado:**
   - [ ] Listar todas as camadas completadas ate o momento da interrupcao
   - [ ] Verificar integridade dos dados salvos (Layer Summary Cards, session logs)
   - [ ] Identificar a ultima etapa completada com sucesso no pipeline
   - [ ] Verificar se o memory update mais recente esta acessivel

3. **Classificar a severidade:**
   - **Baixa:** Dados intactos, apenas tempo insuficiente. Reagendar e continuar.
   - **Media:** Alguns dados podem ter sido perdidos. Necessario verificar e possivelmente re-coletar parcialmente.
   - **Alta:** Dados corrompidos ou invalidados. Necessario re-coletar camadas inteiras.
   - **Critica:** Toda a sessao comprometida. Avaliar se reinicio completo e necessario.

### Etapa 2: Preservar Dados Existentes (15 a 30 min)

**Responsavel:** Synthesis Architect

1. **Salvar estado atual:**
   ```yaml
   emergency_snapshot:
     session_id: ___
     interruption_time: ___
     interruption_type: ___
     last_completed_stage: ___
     data_integrity: "(Intacta / Parcial / Comprometida)"
     layers_completed: [___]
     layers_in_progress: [___]
     layers_not_started: [___]
   ```

2. **Verificar integridade dos dados:**
   - Para cada Layer Summary Card existente: dados completos e coerentes?
   - Para cada Contradiction Card: informacoes suficientes para retomada?
   - Session log: ultimo registro consistente?

3. **Isolar dados suspeitos:**
   - Se houver indicacao de corrupcao, mover dados suspeitos para area de quarentena
   - NAO deletar — preservar para analise posterior

### Etapa 3: Comunicar com o Respondente (Assim que possivel)

**Responsavel:** Chief

1. Se a interrupcao foi tecnica:
   - Informar o respondente sobre o ocorrido
   - Assegurar que os dados ja coletados estao preservados
   - Reagendar a continuacao com prazo maximo de 7 dias (para minimizar efeito de contexto)

2. Se a interrupcao foi do respondente:
   - Demonstrar compreensao e flexibilidade
   - Verificar disponibilidade para retomada
   - Avaliar se o estado emocional do respondente pode afetar dados futuros

3. Se a interrupcao foi por qualidade:
   - Comunicar de forma transparente sem culpabilizar
   - Explicar o que sera necessario re-fazer e por que

### Etapa 4: Planejar Retomada (Antes da sessao de retomada)

**Responsavel:** Chief + Synthesis Architect

1. **Definir ponto de retomada:**
   - Identificar a ultima etapa completada com dados validos
   - Definir se alguma etapa precisa ser re-executada

2. **Ajustar pipeline:**
   ```yaml
   recovery_plan:
     resume_from_stage: ___
     stages_to_redo: [___]
     stages_to_skip: []
     estimated_additional_time: ___
     confidence_adjustments:
       - layer: ___
         adjustment: -0.XX
         reason: "Gap temporal / dados parciais / re-coleta"
   ```

3. **Preparar contexto para retomada:**
   - Carregar memory update mais recente
   - Preparar resumo para o respondente do que ja foi coberto
   - Ter em maos os achados-chave para evitar perguntas redundantes

### Etapa 5: Executar Retomada

**Responsavel:** Agente designado para a camada de retomada

1. **Inicio da sessao de retomada:**
   - Resumir brevemente para o respondente o que foi coberto (2-3 minutos)
   - Confirmar: "Os insights que compartilhamos na sessao anterior ainda fazem sentido para voce?"
   - Se sim: prosseguir do ponto de parada
   - Se nao: investigar o que mudou e ajustar antes de prosseguir

2. **Durante a retomada:**
   - Monitorar engagement do respondente (pode estar frustrado ou menos engajado)
   - Evitar repetir perguntas ja respondidas (consultar session log)
   - Se necessario re-coletar dados, explicar o motivo de forma transparente

3. **Ao concluir a retomada:**
   - Executar memory update completo (Fase 11 do full-persona-mapping)
   - Documentar o gap e seu impacto no relatorio final

### Etapa 6: Recalibrar Confidence

**Responsavel:** Respondent Quality Auditor

Aplicar ajustes de confidence conforme o tipo de interrupcao:

| Tipo de Interrupcao | Ajuste de Confidence | Condicao para Remocao do Ajuste |
|---------------------|---------------------|-------------------------------|
| Temporal (dados intactos, retomada < 7 dias) | -0.03 | Retomada confirmou consistencia |
| Temporal (retomada > 7 dias) | -0.08 | Reassessment parcial da camada em progresso |
| Dados parcialmente perdidos | -0.10 a -0.15 | Re-coleta bem sucedida |
| Dados corrompidos | -0.20 | Re-coleta completa da camada |
| Engagement do respondente comprometido | -0.10 | Validacao explicita na devolutiva |

## Documentacao Obrigatoria

Toda sessao com interrupcao deve ter registro no session log:

```yaml
interruption_record:
  session_id: ___
  interruption_time: ___
  type: ___
  severity: ___
  data_preserved: ___
  recovery_date: ___
  recovery_plan: ___
  confidence_adjustments: ___
  lessons_learned: ___
```

## Prevencao

Para minimizar interrupcoes futuras:
- Salvar estado a cada etapa completada (autosave)
- Confirmar disponibilidade de tempo do respondente ANTES de iniciar camadas longas
- Manter backup de dados em progresso
- Ter template de retomada rapida pre-preparado
