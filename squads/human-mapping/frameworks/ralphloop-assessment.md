---
framework: ralphloop-assessment
category: operational
squad: human-mapping
version: "2.0.0"
---

# RalphLoop Assessment

## Propósito

O RalphLoop Assessment é o ciclo de melhoria contínua do Human Mapping Squad. O nome homenageia o princípio de que todo sistema de assessment deve avaliar a si mesmo. Sem um mecanismo formal de revisão, o squad corre o risco de repetir erros, perpetuar vieses e estagnar metodologicamente. O RalphLoop garante que o squad evolui constantemente — seus frameworks, processos, interpretações e entregáveis melhoram a cada ciclo.

O loop opera em 5 fases: Retrospectiva → Identificação de Gaps → Calibração de Metodologia → Implementação de Melhorias → Verificação de Resultados. O ciclo roda após cada 10 sessões de assessment OU mensalmente (o que vier primeiro).

## Quando Usar

- Após cada 10 sessões de assessment completadas
- Mensalmente, independente do número de sessões
- Após qualquer incidente de qualidade (conclusão errada, reclamação de cliente, etc.)
- Quando um novo membro entra no squad (para calibração)
- Quando novos instrumentos ou frameworks são incorporados
- No planejamento trimestral do squad

## Modelo / Estrutura

### As 5 Fases do RalphLoop

```
    ┌──────────────────┐
    │  FASE 1:          │
    │  RETROSPECTIVA    │ ← "O que funcionou? O que falhou?"
    │                   │
    └────────┬──────────┘
             │
             ▼
    ┌──────────────────┐
    │  FASE 2:          │
    │  IDENTIFICAÇÃO    │ ← "Onde estão os gaps?"
    │  DE GAPS          │
    └────────┬──────────┘
             │
             ▼
    ┌──────────────────┐
    │  FASE 3:          │
    │  CALIBRAÇÃO DE    │ ← "O que precisamos ajustar?"
    │  METODOLOGIA      │
    └────────┬──────────┘
             │
             ▼
    ┌──────────────────┐
    │  FASE 4:          │
    │  IMPLEMENTAÇÃO    │ ← "Colocar em prática"
    │  DE MELHORIAS     │
    └────────┬──────────┘
             │
             ▼
    ┌──────────────────┐
    │  FASE 5:          │
    │  VERIFICAÇÃO DE   │ ← "Funcionou?"
    │  RESULTADOS       │
    └────────┬──────────┘
             │
             └──────────────→ Volta para FASE 1
```

### Fase 1: Retrospectiva

**Objetivo**: Avaliar honestamente o que funcionou e o que falhou nas últimas 10 sessões ou no último mês.

**Perguntas-guia**:
- Quais assessments tiveram os confidence scores mais altos? E os mais baixos? Por quê?
- O solicitante ficou satisfeito com o entregável? Houve feedback negativo?
- Alguma conclusão foi posteriormente contradita por evidência real?
- Quanto tempo cada assessment levou vs estimativa original?
- Houve casos onde o Social Desirability Screen falhou em detectar distorção?
- Algum framework se mostrou mais ou menos útil do que esperado?

**Output**: Lista de observações categorizadas como Sucesso, Melhoria Necessária, ou Problema.

### Fase 2: Identificação de Gaps

**Objetivo**: Identificar gaps sistemáticos no processo, metodologia ou competência do squad.

**Áreas de investigação**:

| Área | Perguntas de Gap |
|------|-----------------|
| **Instrumentos** | Estamos usando os frameworks mais válidos? Algum novo instrumento deveria ser incorporado? |
| **Interpretação** | Estamos interpretando corretamente? Há vieses recorrentes na análise? |
| **Reconciliação** | Os conflitos entre frameworks estão sendo bem resolvidos? Há padrões de conflito não tratados? |
| **Confiança** | Os scores de confiança estão calibrados? Estamos inflando ou deflando? |
| **Entregáveis** | O formato de entrega atende o solicitante? O brief é claro? O relatório é útil? |
| **Processo** | O pipeline está eficiente? Há gargalos? Etapas desnecessárias? |
| **Competência** | O squad tem expertise suficiente em todos os frameworks? Há lacunas de conhecimento? |

**Output**: Lista priorizada de gaps com severidade (Crítico, Importante, Menor).

### Fase 3: Calibração de Metodologia

**Objetivo**: Definir ajustes concretos nos frameworks operacionais, instrumentos e processos.

**Atividades**:
- Revisar e atualizar baselines (Contradiction Baseline, Social Desirability thresholds)
- Ajustar pesos no Confidence Scoring Model se necessário
- Atualizar a Context Priority Matrix com aprendizados
- Revisar templates (Executive Brief, Persona Synthesis)
- Incorporar novos frameworks ou instrumentos identificados na Fase 2
- Remover ou deprecar práticas que não estão funcionando

**Protocolo de calibração inter-avaliador**:
- Selecionar 2 assessments recentes
- Dois membros do squad analisam independentemente
- Comparar interpretações e confidence scores
- Se divergência > 0.10 no score: discutir e alinhar critérios
- Documentar decisões de calibração

**Output**: Lista de mudanças a implementar, com responsável e prazo.

### Fase 4: Implementação de Melhorias

**Objetivo**: Colocar as mudanças em prática de forma controlada.

**Protocolo de implementação**:
- Mudanças pequenas: implementar imediatamente no próximo assessment
- Mudanças médias: implementar com flag de "piloto" — monitorar por 5 sessões
- Mudanças grandes: implementar em paralelo com o processo atual por 1 ciclo

**Documentação**:
- Registrar cada mudança com data, justificativa e resultado esperado
- Versionamento: atualizar a versão dos frameworks modificados
- Comunicar mudanças a todo o squad

**Output**: Mudanças implementadas e documentadas.

### Fase 5: Verificação de Resultados

**Objetivo**: Verificar se as mudanças implementadas geraram o resultado esperado.

**Métricas de verificação**:

| Métrica | Como Medir | Meta |
|---------|-----------|------|
| Confiança média | Média de confidence scores dos assessments do período | Tendência de alta |
| Satisfação do solicitante | Feedback qualitativo + NPS | ≥ 8/10 |
| Tempo por assessment | Horas totais da sessão | Dentro da estimativa ±20% |
| Taxa de re-test | % de assessments que precisaram re-aplicação | < 10% |
| Concordância inter-avaliador | Correlação entre avaliadores em assessments duplos | > 0.85 |
| Taxa de contradição invalidante | % de assessments com contradição invalidante | < 5% |
| Completude de entrega | % de entregáveis entregues no prazo e formato | > 95% |

**Output**: Dashboard de métricas + decisão de continuar, ajustar ou reverter mudanças.

## Como Aplicar (step by step)

### Step 1: Agendar o RalphLoop
- Definir data fixa no calendário do squad
- Frequência: após cada 10 sessões OU mensalmente (o que vier primeiro)
- Duração: 2-3 horas por ciclo
- Participantes: todo o squad

### Step 2: Preparar Dados
- Compilar resultados dos últimos 10 assessments (ou do último mês)
- Calcular métricas de verificação
- Coletar feedback de solicitantes
- Identificar assessments problemáticos ou excepcionais

### Step 3: Executar Fase 1 (Retrospectiva) — 45 min
- Cada membro apresenta observações dos seus assessments
- Categorizar como Sucesso / Melhoria / Problema
- Priorizar os 3-5 itens mais relevantes

### Step 4: Executar Fase 2 (Gaps) — 30 min
- Investigar as áreas listadas no template
- Classificar gaps por severidade
- Selecionar os top 3 gaps para endereçar neste ciclo

### Step 5: Executar Fase 3 (Calibração) — 45 min
- Definir mudanças concretas para cada gap
- Realizar exercício de calibração inter-avaliador
- Documentar mudanças e atribuir responsáveis

### Step 6: Executar Fase 4 (Implementação) — Contínuo
- Implementar mudanças ao longo das próximas sessões
- Monitorar pilotos

### Step 7: Executar Fase 5 (Verificação) — No próximo RalphLoop
- Verificar métricas no próximo ciclo
- Decidir se mudanças foram efetivas

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Regularidade | O RalphLoop acontece no prazo definido, sem adiamentos |
| Honestidade | Erros são reconhecidos sem defensividade |
| Ação concreta | Cada ciclo gera pelo menos 1 mudança implementada |
| Dados-driven | Decisões baseadas em métricas, não em impressões |
| Participação | Todo o squad participa ativamente |
| Documentação | Cada ciclo é documentado para referência futura |

### Anti-patterns
- Pular o RalphLoop por "falta de tempo" → débito de qualidade se acumula
- Retrospectiva só positiva ("tudo ótimo") → squad não evolui
- Identificar gaps mas não implementar → frustração acumulada
- Mudar tudo de uma vez → impossível avaliar o que funcionou
- Não verificar resultados → mudanças baseadas em fé, não em dados

## Integração com Pipeline

### Input
- Dados de todos os assessments do período
- Feedback de solicitantes e respondentes
- Métricas de qualidade do squad
- Observações dos facilitadores

### Output
- Atualizações em TODOS os frameworks operacionais (este framework é meta)
- Novas versões de templates e processos
- Plano de desenvolvimento de competência do squad
- Decisões de incorporar/deprecar instrumentos

### Posição no Pipeline
```
[Todos os Assessments do Período]
         ↓
[RalphLoop: Retrospectiva → Gaps → Calibração → Implementação → Verificação]
         ↓
[Frameworks Operacionais Atualizados]
         ↓
[Próximo Ciclo de Assessments (melhor)]
```

## Exemplos

### Exemplo: RalphLoop Ciclo #7

**Período**: 10 assessments entre Jan-Fev 2026

**Fase 1 — Retrospectiva**:
- Sucesso: Confidence scores médios subiram de 0.72 para 0.78
- Melhoria: Executive Briefs estão levando 3h para redigir (meta: 1.5h)
- Problema: 2 assessments tiveram contradição invalidante por Social Desirability não detectada a tempo

**Fase 2 — Gaps**:
- Gap Crítico: Social Desirability Screen precisa de indicadores mais sensíveis em contexto de contratação
- Gap Importante: Template do Executive Brief precisa de seção "Quick Summary" para decisores ultra-rápidos
- Gap Menor: Context Priority Matrix não tem guidance para contexto "startup early stage"

**Fase 3 — Calibração**:
- Adicionar Indicador 5 ao Social Desirability Screen: velocidade de resposta (respostas muito rápidas = flag)
- Adicionar "Quick Summary" de 3 linhas no topo do Executive Brief
- Adicionar coluna "Startup" na Context Priority Matrix
- Exercício de calibração: 2 facilitadores analisaram mesmo assessment, concordância: 0.88 (OK)

**Fase 4 — Implementação**:
- Social Desirability: implementado como piloto nos próximos 5 assessments
- Executive Brief: implementado imediatamente
- Context Priority Matrix: implementado imediatamente

**Fase 5 — Verificação (próximo ciclo)**:
- Social Desirability: flaggeou 1 caso adicional que teria passado → efetivo
- Executive Brief: tempo de redação reduziu para 2h → melhoria, mas não atingiu meta
- Context Priority Matrix: 1 assessment de startup usou nova coluna → feedback positivo
