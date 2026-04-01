# Arquitetura do Human-Mapping Squad

> Assessment OS — Sistema Operacional de Assessment Humano Multi-Camada

---

## 1. Visão Geral

O Human-Mapping Squad é um **sistema de evidência cruzada** que mapeia pessoas em múltiplas camadas usando 34 agentes de IA, 26+ frameworks de assessment e detecção obrigatória de contradições entre frameworks.

**Não é um teste de personalidade.** É um sistema operacional que:

- Calibra o respondente ANTES de interpretar
- Mede traços ANTES de tipos (evita contaminação)
- Separa traço, adaptação, fase, contexto e persona social
- Cruza múltiplos frameworks e detecta contradições
- Atribui score de confiança por conclusão
- Entrega perfil + plano de desenvolvimento acionável

---

## 2. Princípios Fundamentais

```
1. evidence_over_impression     — Evidência sobre impressão
2. confidence_per_conclusion    — Score de confiança por conclusão
3. traits_before_types          — Traços antes de tipos
4. motivation_after_style       — Motivação depois de estilo
5. contradiction_is_signal      — Contradição é sinal, não erro
6. no_single_framework_rules    — Nenhum framework domina sozinho
7. synthesis_over_labeling      — Síntese sobre rotulagem
8. actionability_over_vanity    — Acionabilidade sobre vaidade
```

---

## 3. Pipeline Completo

```
┌─────────────────────────────────────────────────────────────────────┐
│                    ASSESSMENT OS PIPELINE                           │
│                                                                     │
│  /start                                                             │
│    │                                                                │
│    ▼                                                                │
│  ┌──────────┐   ┌─────────────┐   ┌──────────────┐                │
│  │  INTAKE   │──▶│ CALIBRAÇÃO  │──▶│   TRAÇOS     │                │
│  │           │   │             │   │  (Big Five,   │                │
│  │ objetivo  │   │ consistência│   │   HEXACO,     │                │
│  │ contexto  │   │ honestidade │   │   NEO, 16PF,  │                │
│  │ profundid.│   │ fadiga      │   │   Hogan HPI)  │                │
│  └──────────┘   └─────────────┘   └──────┬───────┘                │
│                                           │                         │
│                                           ▼                         │
│  ┌──────────────┐   ┌──────────────┐   ┌──────────────┐           │
│  │ TIPOS/ESTILOS│──▶│  MOTIVAÇÕES  │──▶│   FORÇAS     │           │
│  │ (MBTI, DISC, │   │ (Eneagrama,  │   │ (Clifton,    │           │
│  │  Insights,   │   │  SDI, Reiss, │   │  VIA, Belbin)│           │
│  │  PI, FIRO,   │   │  MVPI, 12DF) │   │              │           │
│  │  PCM,Birkman)│   │              │   │              │           │
│  └──────────────┘   └──────────────┘   └──────┬───────┘           │
│                                                │                    │
│                                                ▼                    │
│  ┌──────────────┐   ┌──────────────┐   ┌──────────────┐           │
│  │  CARREIRA    │──▶│  CONTRADIÇÕES│──▶│   SÍNTESE    │           │
│  │ (RIASEC,     │   │ (cross-frame │   │  (integração │           │
│  │  Strong,     │   │  auditoria,  │   │   multi-     │           │
│  │  Kolbe)      │   │  reconcilia- │   │   camada)    │           │
│  │              │   │  ção)        │   │              │           │
│  └──────────────┘   └──────────────┘   └──────┬───────┘           │
│                                                │                    │
│                                                ▼                    │
│                                         ┌──────────────┐           │
│                                         │  RELATÓRIO   │           │
│                                         │ (executivo,  │           │
│                                         │  profundo,   │           │
│                                         │  desenvolv.) │──▶ /report│
│                                         └──────────────┘           │
└─────────────────────────────────────────────────────────────────────┘
```

### 3.1 Detalhamento por Etapa

| Etapa | Agentes | Frameworks | Quality Gates |
|-------|---------|------------|---------------|
| Intake | intake-orchestrator, context-mapper | assessment-intake-canvas, context-priority-matrix | intake-quality |
| Calibração | rapport-architect, respondent-quality-auditor, readiness-gatekeeper | response-reliability-model, social-desirability-screen | calibration-quality |
| Traços | trait-chief, big-five-analyst, hexaco-analyst, neo-16pf-analyst, hogan-bright-side-analyst | big-five, hexaco, neo-pi-3, 16pf, hogan-hpi | trait-assessment-quality |
| Tipos/Estilos | type-style-chief, mbti-analyst, disc-analyst, insights-social-style-analyst, predictive-index-analyst, firo-pcm-birkman-analyst | mbti, disc, insights-discovery, social-style, predictive-index, firo, pcm, birkman | type-assessment-quality |
| Motivações | motivation-chief, enneagram-analyst, sdi-analyst, reiss-analyst, mvpi-driving-forces-analyst | enneagram, sdi-2-0, reiss, hogan-mvpi, 12-driving-forces | motivation-assessment-quality |
| Forças | strengths-chief, cliftonstrengths-analyst, via-strengths-analyst, belbin-analyst | cliftonstrengths, via-character-strengths, belbin-team-roles | strengths-assessment-quality |
| Carreira/Ação | career-fit-analyst, riasec-strong-analyst, kolbe-analyst | riasec, strong-interest-inventory, kolbe-a | career-fit-quality, conation-quality |
| Contradições | contradiction-auditor, readiness-gatekeeper | cross-framework-reconciliation, trait-vs-type-model, adaptation-vs-identity-model | contradiction-audit-quality |
| Síntese | synthesis-architect, development-planner, human-mapping-chief | persona-synthesis-model, development-prioritization | synthesis-quality |
| Relatório | report-writer, human-mapping-chief | executive-brief-model | executive-report-quality, deep-report-quality |

---

## 4. Modelo de Agentes (34)

### 4.1 Grafo de Dependências

```
                    ┌─────────────────────┐
                    │ human-mapping-chief  │ ◀── Orquestra TUDO
                    └──────────┬──────────┘
                               │
            ┌──────────────────┼──────────────────┐
            ▼                  ▼                   ▼
   ┌────────────────┐ ┌───────────────┐ ┌──────────────────┐
   │readiness-      │ │intake-        │ │respondent-       │
   │gatekeeper      │ │orchestrator   │ │quality-auditor   │
   │(gate global)   │ │               │ │                  │
   └────────────────┘ │context-mapper │ │rapport-architect │
                      └───────┬───────┘ └──────────────────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │   trait-chief    │ ◀── PRIMEIRO (base estável)
                    ├─────────────────┤
                    │ big-five-analyst │
                    │ hexaco-analyst   │
                    │ neo-16pf-analyst │
                    │ hogan-bright-   │
                    │   side-analyst   │
                    └────────┬────────┘
                             │
                             ▼
                   ┌──────────────────┐
                   │ type-style-chief │ ◀── DEPOIS de traços
                   ├──────────────────┤
                   │ mbti-analyst     │
                   │ disc-analyst     │
                   │ insights-social- │
                   │   style-analyst  │
                   │ predictive-      │
                   │   index-analyst  │
                   │ firo-pcm-        │
                   │   birkman-analyst│
                   └────────┬─────────┘
                            │
                            ▼
                  ┌──────────────────┐
                  │ motivation-chief │ ◀── DEPOIS de tipos
                  ├──────────────────┤
                  │ enneagram-analyst│
                  │ sdi-analyst      │
                  │ reiss-analyst    │
                  │ mvpi-driving-    │
                  │   forces-analyst │
                  └────────┬─────────┘
                           │
              ┌────────────┼────────────┐
              ▼                         ▼
    ┌──────────────────┐     ┌──────────────────┐
    │ strengths-chief  │     │career-fit-analyst│
    ├──────────────────┤     │riasec-strong-    │
    │ cliftonstrengths-│     │   analyst        │
    │   analyst        │     │kolbe-analyst     │
    │ via-strengths-   │     └────────┬─────────┘
    │   analyst        │              │
    │ belbin-analyst   │              │
    └────────┬─────────┘              │
             │                        │
             └───────────┬────────────┘
                         ▼
               ┌──────────────────────┐
               │ contradiction-auditor│ ◀── OBRIGATÓRIO
               └──────────┬───────────┘
                          ▼
               ┌──────────────────────┐
               │ synthesis-architect  │
               └──────────┬───────────┘
                          │
                ┌─────────┼─────────┐
                ▼                   ▼
     ┌──────────────────┐ ┌────────────────┐
     │  report-writer   │ │ development-   │
     │                  │ │   planner      │
     └──────────────────┘ └────────────────┘
```

### 4.2 Camadas de Agentes

| Camada | Agentes | Quantidade |
|--------|---------|------------|
| Comando & Orquestração | human-mapping-chief, readiness-gatekeeper | 2 |
| Intake & Qualidade | intake-orchestrator, context-mapper, rapport-architect, respondent-quality-auditor | 4 |
| Traços | trait-chief, big-five-analyst, hexaco-analyst, neo-16pf-analyst, hogan-bright-side-analyst | 5 |
| Tipos & Estilos | type-style-chief, mbti-analyst, disc-analyst, insights-social-style-analyst, predictive-index-analyst, firo-pcm-birkman-analyst | 6 |
| Motivação & Drives | motivation-chief, enneagram-analyst, sdi-analyst, reiss-analyst, mvpi-driving-forces-analyst | 5 |
| Forças & Talentos | strengths-chief, cliftonstrengths-analyst, via-strengths-analyst, belbin-analyst | 4 |
| Carreira & Ação | career-fit-analyst, riasec-strong-analyst, kolbe-analyst | 3 |
| Integração & Auditoria | contradiction-auditor, synthesis-architect, report-writer, development-planner | 4 |
| **TOTAL** | | **34** |

---

## 5. Regras Anti-Caos

1. **human-mapping-chief** define profundidade, resolve conflitos entre frameworks, aprova laudo final
2. **readiness-gatekeeper** impede conclusão prematura — sem evidência suficiente, não fecha
3. **respondent-quality-auditor** detecta respostas inválidas ANTES de interpretar
4. **contradiction-auditor** é OBRIGATÓRIO — todo perfil passa por auditoria de contradição
5. **trait-chief** roda ANTES de type-style-chief — traços são base, tipos são derivação
6. **motivation-chief** roda DEPOIS de tipos — motivação profunda exige mais contexto
7. **report-writer** NUNCA entrega laudo sem score de confiança por camada

---

## 6. Modelo de Confiança

### Escala

| Nível | Score | Significado |
|-------|-------|-------------|
| Low | 0.0-0.4 | Inferência fraca, poucos dados, possível viés. Requer mais evidência. |
| Medium | 0.4-0.7 | Inferência razoável, múltiplas fontes parciais, alguma convergência. |
| High | 0.7-1.0 | Forte convergência entre frameworks, dados consistentes, respondente calibrado. |

### Regras

- Todo score é atribuído POR CAMADA e POR CONCLUSÃO
- Confiança final = média ponderada das camadas (traços pesam mais que tipos)
- Se confiança < 0.4 em qualquer camada obrigatória → gatekeeper bloqueia relatório
- Contradições não resolvidas reduzem confiança da camada afetada
- Modo Oficial (instrumento formal) tem bonus de +0.15 na confiança base
- Modo Proxy (inferência) parte de baseline 0.3 e sobe com evidência cruzada

---

## 7. Modelo de Contradição

### Tipos de Contradição

| Tipo | Exemplo | Severidade |
|------|---------|------------|
| Traço vs Tipo | Big Five diz introvertido, MBTI diz ENFP | Alta |
| Motivação vs Estilo | Eneagrama 3 (achievement) mas DISC S (steady) | Média |
| Força vs Papel | CliftonStrengths Analytical mas Belbin Plant | Baixa |
| Intra-framework | Respostas contraditórias no mesmo framework | Alta |
| Adaptação vs Identidade | Comportamento no trabalho ≠ comportamento em casa | Informacional |

### Protocolo de Reconciliação

1. Detectar: contradiction-auditor cruza todas as camadas
2. Classificar: severidade + tipo + camadas envolvidas
3. Investigar: é traço real ou adaptação contextual?
4. Reconciliar: usar modelo adaptation-vs-identity para separar
5. Documentar: registrar no contradiction-map com explicação
6. Ajustar confiança: reduzir score das camadas afetadas

---

## 8. Dois Modos de Operação

### Official Instrument Mode

- Respondente fez assessment formal (ex: CliftonStrengths online, NEO-PI-3 aplicado)
- Resultados oficiais são importados
- Confiança base mais alta (+0.15)
- Agente analista interpreta e contextualiza
- Ainda cruza com outros frameworks

### Proxy Inference Mode (DEFAULT)

- Sem instrumento formal disponível
- Usa entrevistas estruturadas + baterias próprias de perguntas
- Cruzamento inferencial entre múltiplos frameworks
- Confiança base mais baixa (0.3) — sobe com convergência
- Respondent-quality-auditor é AINDA MAIS crítico neste modo
- Cada conclusão requer evidência de pelo menos 2 frameworks convergentes

---

## 9. Cross-Squad Integration

```
                    ┌──────────────────┐
                    │  HUMAN-MAPPING   │
                    │     SQUAD        │
                    └────────┬─────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                     │
        ▼                    ▼                     ▼
┌───────────────┐  ┌─────────────────┐  ┌──────────────────┐
│  ADVISORY     │  │   C-LEVEL       │  │  SALES CALL      │
│  BOARD        │  │   SQUAD         │  │  INTELLIGENCE    │
│               │  │                 │  │                  │
│ ← liderança  │  │ ← exec profiles│  │ ← closer profiles│
│ → contexto   │  │ ← team comp    │  │ ← comm style     │
│   estratégico │  │ → hiring needs │  │ → performance    │
└───────────────┘  └─────────────────┘  └──────────────────┘
        │                    │                     │
        ▼                    ▼                     ▼
┌───────────────┐  ┌─────────────────┐  ┌──────────────────┐
│  BRAND        │  │  STORYTELLING   │  │  MOVEMENT        │
│  SQUAD        │  │  SQUAD          │  │  SQUAD           │
│               │  │                 │  │                  │
│ ← personality │  │ ← personality  │  │ ← motivation     │
│   for brand   │  │   insights     │  │   /values        │
│ → archetype   │  │ → narrative    │  │ → cultural       │
│               │  │   preferences  │  │   identity       │
└───────────────┘  └─────────────────┘  └──────────────────┘
                             │
                             ▼
                   ┌─────────────────┐
                   │   DATA SQUAD    │
                   │                 │
                   │ ← metrics       │
                   │ → statistical   │
                   │   validation    │
                   └─────────────────┘
```

### Protocolo de Handoff

1. human-mapping-chief autoriza handoff
2. Dados são formatados com template `cross-squad-handoff-template.md`
3. Score de confiança é incluído
4. Registrado em `data/registries/cross-squad-deliveries.yaml`
5. Squad receptor confirma recebimento

---

## 10. Quality Gates

### Obrigatórios (toda sessão)

| Gate | Descrição | Bloqueante |
|------|-----------|------------|
| calibration-quality | Respondente calibrado | Sim |
| trait-assessment-quality | Traços medidos com confiança | Sim |
| contradiction-audit-quality | Contradições auditadas | Sim |
| confidence-map-quality | Score de confiança por camada | Sim |
| synthesis-quality | Síntese integrada e coerente | Sim |

### Por Domínio

| Domínio | Gates |
|---------|-------|
| Intake | intake-quality |
| Traços | big-five-quality, trait-confidence-quality |
| Tipos | mbti-inference-quality, type-vs-trait-separation |
| Motivação | motivation-depth-quality |
| Forças | strength-vs-skill-separation |
| Carreira | career-fit-quality |
| Contradição | cross-framework-alignment |
| Relatório | actionability-quality |

---

## 11. Estrutura de Diretórios

```
squads/human-mapping/
├── agents/              (34)  — Prompts de agentes de IA
├── archive/             (18+) — Conteúdo histórico e icônico
├── authority/           (18)  — Sumários, cases, workshops
├── checklists/          (85+) — Quality gates por camada
├── data/                (30+) — Registries, mapas, perfis
├── docs/                (18)  — Documentação completa
├── frameworks/          (52)  — 26 assessments + 14 operacionais + 12 referência
├── lib/                 (38+) — Componentes, padrões, rubrics, taxonomias
├── phrases/             (18)  — Bancos de perguntas e frases
├── projects/            (45+) — 7 tipos de projeto com fases
├── reference/           (70+) — Livros, psicometria, coaching, indústrias
├── scripts/             (14)  — Scoring, análise, reporting
├── swipe/               (12+) — Exemplos bons e ruins
├── swipe-sources/       (8)   — Fontes de pesquisa
├── tasks/               (30+) — Definições de tarefas
├── templates/           (27+) — Templates reutilizáveis
├── voice/               (22+) — Tom, linguagem, canais
├── workflows/           (21)  — Fluxos numerados 00-20
├── ARCHITECTURE.md             — Este documento
├── config.yaml                 — Configuração completa
├── README.md                   — Visão geral
└── swipe.config                — Configuração de swipes
```

**Total: ~626+ arquivos**

---

## 12. KPIs

### Qualidade do Assessment

| KPI | Descrição |
|-----|-----------|
| confidence_average_per_layer | Confiança média por camada |
| contradiction_resolution_rate | Taxa de resolução de contradições |
| cross_framework_alignment_score | Alinhamento entre frameworks |
| respondent_consistency_score | Consistência do respondente |

### Profundidade

| KPI | Descrição |
|-----|-----------|
| frameworks_covered_per_session | Frameworks cobertos por sessão |
| facets_resolved_per_trait | Facetas resolvidas por traço |
| layers_completed | Camadas completadas |
| depth_score | Score de profundidade |

### Impacto

| KPI | Descrição |
|-----|-----------|
| profile_accuracy_feedback | Feedback de acurácia |
| development_plan_adoption | Adoção do plano de desenvolvimento |
| reassessment_consistency | Consistência em reavaliação |
| cross_squad_utility_score | Utilidade para outros squads |

### Operacional

| KPI | Descrição |
|-----|-----------|
| session_completion_rate | Taxa de completação |
| average_session_duration | Duração média |
| methodology_calibration_rate | Taxa de calibração |
| registry_currency | Registries atualizados |

---

## 13. Comandos

| Comando | Descrição | Profundidade |
|---------|-----------|--------------|
| `/start` | Inicia bateria completa | Padrão |
| `/resume` | Retoma sessão anterior | - |
| `/fast` | Versão resumida (traços + tipos + motivação) | Rápida |
| `/deep` | Versão profunda (todas as camadas + contradições) | Profunda |
| `/report` | Entrega laudo final | - |
| `/contradictions` | Exibe conflitos entre frameworks | - |
| `/development` | Entrega plano de desenvolvimento | - |
| `/career` | Foco em carreira | Especializado |
| `/team` | Foco em papel no time | Especializado |
| `/leadership` | Foco em liderança | Especializado |
| `/hiring` | Foco em contratação | Especializado |

---

## 14. O que alguém 100x mais inteligente faria?

Não criaria um agente que "descobre MBTI". Criaria um **sistema de evidência cruzada** que responde:

1. **Quem essa pessoa é quando está regulada** — traços estáveis, padrões naturais
2. **Quem ela vira sob pressão** — sequência de conflito, stress patterns, dark side
3. **O que a move de verdade** — motivação profunda vs superficial, valores vs adaptação
4. **Onde ela performa melhor** — ambiente, papel, tipo de desafio
5. **Em que ambiente ela floresce ou degrada** — fit cultural, necessidades ocultas
6. **Quais frameworks convergem** — evidência cruzada forte
7. **Quais frameworks estão "mentindo"** — por causa de contexto, fase ou máscara social

---

## 15. Cascata de Decisão HRM

O Human-Mapping Squad opera dentro de uma hierarquia de decisão em 5 níveis:

### Nível 1 — Agente Individual
- Executa subtask dentro do seu escopo
- Quality gate: checklist específico do agente
- Se PASS → entrega ao próximo agente ou ao chief da camada
- Se FAIL → rework interno (máximo 2 ciclos)
- Se FAIL após 2 ciclos → escala para chief da camada

### Nível 2 — Chief da Camada
- Orquestra múltiplos agentes na mesma camada (trait-chief, type-style-chief, etc.)
- Quality gate: checklist da camada (ex: `checklists/traits/big-five-quality.md`)
- Se PASS → handoff para próxima camada via go/no-go gate
- Se FAIL → retorna ao agente com feedback específico
- Se impasse → escala para human-mapping-chief

### Nível 3 — Human-Mapping Chief (Squad Chief)
- Orquestra todo o pipeline, resolve conflitos, aprova output final
- Quality gate: `checklists/chief/chief-report-approval-quality.md`
- Se PASS → output aprovado para entrega ou handoff cross-squad
- Se FAIL → retorna ao synthesis-architect ou report-writer
- Se decisão ultrapassa escopo → escala para HRM Central

### Nível 4 — Cross-Squad Handoff
- Output sai do Human-Mapping para outro squad
- Quality gate de SAÍDA: `checklists/chief/chief-cross-squad-handoff-quality.md`
- Quality gate de ENTRADA: definido pelo squad receptor
- Se REJEITADO pelo receptor → retorna ao chief com feedback
- Registro: `data/registries/cross-squad-deliveries.yaml`

### Nível 5 — HRM Central (Diretor Presidente)
- Decisão final quando squad chief não pode resolver
- Critérios de escalação (de `config.yaml` escalation_rules):
  - Confiança global < 0.5 após todas tentativas
  - Handoff rejeitado pelo squad receptor
  - Preocupação ética (consentimento, discriminação, uso indevido)
  - Mudança metodológica que afeta todo o pipeline
  - Cliente disputa resultados com contra-evidência válida

### Diagrama da Cascata

```
Agente → [gate] → Chief Camada → [gate] → Squad Chief → [gate] → Cross-Squad/Entrega
   ↑ rework          ↑ rework              ↑ rework
   └─ max 2x         └─ max 2x             └─ max 1x → HRM Central
```

---

## 16. Protocolo de Rework Loop

Quando um quality gate reprova um output, o sistema entra em loop de melhoria:

### Triggers Automáticos (de `config.yaml` rework_triggers)

| Trigger | Ação | Máximo de Ciclos |
|---------|------|-----------------|
| Confiança da camada < 0.4 | Retorna ao chief da camada para coleta adicional | 2 |
| Teste Barnum FAIL no relatório | Retorna ao report-writer para reescrita com especificidade | 1 |
| Contradição S4 (intra-framework) | Retorna ao respondent-quality-auditor para validação | 1 |
| Síntese faltando ≥2 camadas obrigatórias | Retorna ao synthesis-architect com dados faltantes | 1 |

### Triggers por Decisão do Chief

| Trigger | Ação |
|---------|------|
| Tom do relatório inadequado | Retorna ao report-writer com guidance de voz |
| Plano de desenvolvimento não acionável | Retorna ao development-planner com requisitos |

### Regras do Loop

1. **Máximo 2 ciclos** por trigger automático — após isso, escala para chief
2. **Máximo 1 ciclo** por decisão do chief — após isso, escala para HRM Central
3. **Cada rework** deve documentar: o que falhou, o que foi corrigido, evidência de melhoria
4. **Confiança NÃO sobe automaticamente** após rework — precisa de nova evidência
5. **Se o rework não melhora** → aceitar com caveats OU coletar dados adicionais OU encerrar sessão

---

## 17. Loop de Memória e Aprendizado

### Como o Squad Aprende

O Human-Mapping Squad implementa aprendizado contínuo via RalphLoop:

```
Sessão → Registro → Análise → Calibração → Melhoria → Verificação
```

### Componentes do Loop

1. **Registro pós-sessão** (`data/registries/`)
   - Toda sessão registra: resultados, confiança, contradições, feedback
   - Registries: session-index, persona-registry, contradiction-registry, lessons-learned

2. **Análise periódica** (`workflows/20-ralphloop-assessment-retro.md`)
   - A cada 10 sessões: retrospectiva
   - Identifica: padrões recorrentes, gaps metodológicos, frameworks mais/menos úteis

3. **Calibração** (`frameworks/ralphloop-assessment.md`)
   - Ajusta pesos de frameworks baseado em dados de acurácia
   - Atualiza rubrics se thresholds precisam refinamento
   - Documenta mudanças com evidência (mínimo 3 sessões mostrando problema)

4. **Verificação**
   - Aplica mudança retroativamente a 3 sessões passadas
   - Compara resultados antes/depois
   - Se melhoria confirmada → permanece; se não → rollback

### Rastreabilidade

| O que | Onde |
|-------|------|
| Decisões de sessão | `data/registries/session-index.yaml` |
| Perfis gerados | `data/registries/persona-registry.yaml` |
| Contradições detectadas | `data/registries/contradiction-registry.yaml` |
| Lições aprendidas | `data/registries/lessons-learned.yaml` |
| Efetividade de frameworks | `data/registries/framework-effectiveness.yaml` |
| Feedback de respondentes | `data/registries/respondent-feedback.yaml` |
| Histórico de calibração | `data/registries/calibration-history.yaml` |

---

## 18. Go/No-Go Gates do Pipeline

Cada transição entre estágios do pipeline tem um gate explícito (definido em `config.yaml`):

| Transição | Condição GO | Condição NO-GO |
|-----------|-------------|----------------|
| Intake → Calibração | Objetivo definido + contexto classificado + profundidade selecionada | Retorna ao intake-orchestrator |
| Calibração → Traços | Consistência ≥ 0.5 + desejabilidade social ≤ MEDIUM | rapport-architect ajusta abordagem |
| Traços → Tipos | Big Five confiança ≥ 0.5 em todas 5 dimensões | trait-chief solicita evidência adicional |
| Tipos → Motivação | ≥2 frameworks de tipo avaliados + separação traço vs tipo verificada | type-style-chief adiciona frameworks |
| Motivação → Forças | Motivação core identificada com ≥ 0.5 confiança | motivation-chief aprofunda |
| Forças → Carreira | ≥2 frameworks de força + força vs habilidade separada | strengths-chief adiciona evidência |
| Carreira → Contradições | Código RIASEC identificado OU carreira fora do escopo | career-fit-analyst adiciona dados |
| Contradições → Síntese | Todas contradições S3/S4 resolvidas OU documentadas como irresolvíveis | contradiction-auditor investiga |
| Síntese → Relatório | Integração multi-camada completa + confidence map + Barnum PASS | synthesis-architect rework |
| Relatório → Entrega | Chief aprova + confiança ≥ 0.5 global | report-writer rework |

---

*Versão 2.0.0 — Human-Mapping Squad / MMOS*
