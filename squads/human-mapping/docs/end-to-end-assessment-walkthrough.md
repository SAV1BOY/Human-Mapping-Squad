---
type: doc
squad: human-mapping
version: "2.0.0"
---

# Walkthrough Completo: Assessment de Alex Santos

> Este documento mostra o pipeline COMPLETO do Assessment OS em ação, do `/start` ao relatório final, usando uma persona real para demonstrar cada fase.

---

## Contexto

| Campo | Valor |
|-------|-------|
| Respondente | Alex Santos, 35 anos |
| Cargo | Tech Lead — empresa de tecnologia (50 pessoas) |
| Objetivo | Programa de desenvolvimento de liderança |
| Profundidade | `/deep` |
| Modo | Proxy Inference |
| Session ID | HMS-2026-0042 |

---

## Fase 1: Intake (`/start`)

**Agentes**: human-mapping-chief, intake-orchestrator, context-mapper

### Perguntas e Respostas

| # | Pergunta (intake-orchestrator) | Resposta de Alex |
|---|-------------------------------|------------------|
| 1 | "Qual o objetivo desta análise?" | "Quero entender se estou pronto para uma posição de gestão" |
| 2 | "Em que contexto profissional você está?" | "Empresa de tecnologia, 50 pessoas, crescendo rápido" |
| 3 | "Já fez algum assessment antes?" | "Não, é meu primeiro" |
| 4 | "Quanto tempo pode dedicar?" | "Posso dedicar 90 minutos" |
| 5 | "Alguma preocupação sobre o processo?" | "Tenho medo de que digam que não sirvo para liderar" |

### Classificação do Contexto (context-mapper)
- Contexto: **Liderança** (desenvolvimento, não contratação)
- Profundidade: `/deep` (todas camadas + contradições + desenvolvimento)
- Frameworks prioritários: Big Five + Enneagram + CliftonStrengths + Hogan (liderança)

### Quality Gate: `intake-quality` → **PASS**

---

## Fase 2: Calibração

**Agentes**: rapport-architect, respondent-quality-auditor

### Rapport
- Tom inicial: `curious-explorer`
- Detecção de ansiedade: Alex mostrou tensão ao mencionar "medo de não servir"
- Ajuste: Mudou para `empathetic-listener` — "É muito comum sentir isso. O assessment não julga, mapeia."
- Defensividade: 4/10 (moderada, normal para primeiro assessment)

### Quality Check (respondent-quality-auditor)

| Indicador | Score | Status |
|-----------|-------|--------|
| Consistência interna | 0.82 | ✓ GO |
| Desejabilidade social | LOW | ✓ GO |
| Fadiga | NONE | ✓ GO |
| Overclaiming | NONE | ✓ GO |
| Context switching | NONE | ✓ GO |

### Quality Gate: `calibration-quality` → **PASS** (consistência 0.82 ≥ 0.50)

---

## Fase 3: Traços (Big Five + HEXACO)

**Agentes**: trait-chief, big-five-analyst, hexaco-analyst

### Resultados Big Five

| Dimensão | Percentil | Confiança | Evidência Comportamental |
|----------|-----------|-----------|--------------------------|
| **Openness** | 82 | 0.85 | "Propôs mudança de stack 3x no último ano. Lê sobre tendências todo dia." |
| **Conscientiousness** | 74 | 0.80 | "Cumpre sprints no prazo, documenta tudo, planeja antes de executar." |
| **Extraversion** | 38 | 0.75 | "Prefere 1:1, drena energia em reuniões > 5 pessoas, recarrega sozinho." |
| **Agreeableness** | 65 | 0.78 | "Colabora bem mas defende posição técnica quando discorda firmemente." |
| **Neuroticism** | 45 | 0.72 | "Ansioso com prazos apertados mas recupera em 24h. Sono regular." |

### HEXACO Adição
- **Honesty-Humility**: 78 (alto) — Transparente sobre limitações, não exagera conquistas, divide crédito.

### Facetas Relevantes (NEO-PI-3)
- Openness → Ideas: **91** (extremo alto — investigar impacto)
- Extraversion → Gregariousness: **28** (muito baixo — confirma introversão social)
- Extraversion → Assertiveness: **52** (moderado — consegue se posicionar quando necessário)
- Conscientiousness → Order: **81** (alto) vs Self-Discipline: **68** (moderado — gap interessante)

### Decisão do trait-chief: Facetas ativadas por score extremo (Ideas 91, Gregariousness 28)

### Quality Gate: `trait-assessment-quality` → **PASS** (confiança ≥ 0.50 todas dimensões)

---

## Fase 4: Tipos/Estilos (MBTI + DISC)

**Agentes**: type-style-chief, mbti-analyst, disc-analyst

### MBTI (proxy): **INTJ**
- **I**: Big Five E 38 → confirma introversão
- **N**: Big Five O 82 → alta intuição, preferência por abstração
- **T**: Big Five A 65 → levemente Thinking, mas não extremo (T leve)
- **J**: Big Five C 74 → organizado, planejador
- Confiança: 0.72

### DISC: **CS** (Compliance-Steadiness)
| Eixo | Score | Interpretação |
|------|-------|---------------|
| D (Dominance) | 42 | Moderado-baixo — não impõe, influencia por competência |
| I (Influence) | 35 | Baixo — confirma introversão, pouco networking |
| S (Steadiness) | 55 | Moderado — cooperativo, busca estabilidade |
| C (Compliance) | 68 | Alto — analítico, metódico, orientado a dados |

### DISC Natural vs Adaptado
- Delta I: +15 (adapta extroversão no trabalho — custo energético!)
- Delta D: +8 (levemente mais assertivo no trabalho)

### Cross-check traço↔tipo
- Big Five E 38 ↔ MBTI I ↔ DISC I 35 → **CONVERGENTE** ✓
- Big Five O 82 ↔ MBTI N → **CONVERGENTE** ✓
- Big Five C 74 ↔ MBTI J ↔ DISC C 68 → **CONVERGENTE** ✓

### Quality Gate: `type-assessment-quality` → **PASS**

---

## Fase 5: Motivação (Enneagram + SDI)

**Agentes**: motivation-chief, enneagram-analyst, sdi-analyst

### Enneagram (proxy): **Tipo 5w6**
- **Core fear**: Ser incompetente ou incapaz
- **Core desire**: Ser capaz, competente e autossuficiente
- **Comportamento**: Acumula conhecimento antes de agir, observa antes de participar
- **Wing 6**: Adiciona lealdade e busca por segurança (não é 5w4 que seria mais artístico)
- **Nível**: 3 (saudável — compartilha conhecimento, contribui ativamente)
- **Instinto**: Self-preservation (foco em recursos, autonomia, preparação)
- Confiança: 0.68

### SDI: **Green** (Analytic-Autonomizing)
- **Em paz**: Analisa, pesquisa, busca entendimento profundo antes de decidir
- **Conflito Stage 1**: Persiste com lógica e dados (Green→Green)
- **Conflito Stage 2**: Busca harmonia e conexão (Green→Blue)
- **Conflito Stage 3**: Assertividade direta (Green→Red — último recurso)
- Confiança: 0.70

### Quality Gate: `motivation-assessment-quality` → **PASS**

---

## Fase 6: Forças (CliftonStrengths + VIA + Belbin)

**Agentes**: strengths-chief, cliftonstrengths-analyst, via-strengths-analyst, belbin-analyst

### CliftonStrengths (proxy Top 5)
| Rank | Tema | Domínio | Evidência |
|------|------|---------|-----------|
| 1 | **Learner** | Strategic Thinking | "Estudo todo dia, faço cursos constantemente" |
| 2 | **Analytical** | Strategic Thinking | "Preciso de dados antes de decidir qualquer coisa" |
| 3 | **Strategic** | Strategic Thinking | "Vejo 3-4 caminhos antes de escolher" |
| 4 | **Deliberative** | Executing | "Planejo, avalio riscos, só então executo" |
| 5 | **Intellection** | Strategic Thinking | "Adoro pensar profundamente sobre problemas complexos" |

**Nota**: 4 de 5 são Strategic Thinking — perfil altamente intelectual, baixo em Influencing.

### VIA Signature Strengths
- Love of Learning, Judgment, Prudence, Curiosity, Perspective

### Belbin: **Monitor Evaluator** (primário), **Specialist** (secundário)
- Contribuição: Análise crítica, avaliação de opções, parecer baseado em evidência
- Allowable weakness: Pode parecer frio/distante, baixa criatividade radical

### Quality Gate: `strengths-assessment-quality` → **PASS**

---

## Fase 7: Carreira/Ação (RIASEC + Kolbe)

### RIASEC (proxy): **IAC** (Investigative-Artistic-Conventional)
- Investigative: 85 (dominante — pesquisa, análise, resolução de problemas)
- Artistic: 62 (secundário — criatividade intelectual, não visual)
- Conventional: 58 (terciário — organização, sistemas, processos)

### Kolbe A (proxy): **8-7-4-3**
| Action Mode | Score | Zona | Interpretação |
|-------------|-------|------|---------------|
| Fact Finder | 8 | Initiate | Pesquisa profundamente antes de agir |
| Follow Thru | 7 | Initiate | Organiza em sistemas e processos |
| Quick Start | 4 | Accommodate | Moderado em risco/inovação rápida |
| Implementor | 3 | Prevent | Prefere trabalho abstrato a hands-on |

### Quality Gate: `career-fit-quality` → **PASS**

---

## Fase 8: Contradições Detectadas

**Agente**: contradiction-auditor (OBRIGATÓRIO)

### Contradição 1
| Campo | Valor |
|-------|-------|
| **Frameworks** | Big Five Extraversion (38) vs DISC Adaptado I (+15 delta) |
| **Severidade** | S2 (Moderada) |
| **Natureza** | Introvertido natural adapta extroversão no trabalho |
| **Investigação** | Birkman revelaria: comportamento usual extrovertido, necessidade real introvertida |
| **Resolução** | CONTEXTUAL — introvertido por natureza, adapta-se para liderar standups e 1:1s. Custo energético documentado. |
| **Impacto confiança** | -0.05 |

### Contradição 2
| Campo | Valor |
|-------|-------|
| **Frameworks** | Enneagram 5 (autonomia, conhecimento) vs Aspiração de gestão de pessoas |
| **Severidade** | S2 (Moderada) |
| **Investigação** | Quer liderar TECNICAMENTE, não gerenciar PESSOAS. Padrão "reluctant-manager". |
| **Resolução** | INFORMACIONAL — aspiração é liderança técnica (Staff/Principal Engineer), não people management. Precisa de clarificação de carreira. |
| **Impacto confiança** | -0.03 |

### Contradições S3/S4: **ZERO**

### Quality Gate: `contradiction-audit-quality` → **PASS**

---

## Fase 9: Síntese

**Agentes**: synthesis-architect, human-mapping-chief

### Quem é Alex Santos (7 dimensões)

1. **Quem é quando regulado**: Pensador profundo e analítico (O 82, C 74, E 38). Opera melhor quando pode pesquisar antes de decidir.

2. **Quem vira sob pressão**: Isola-se (Enneagram 5 → retrai). SDI Green→Blue→Red. Pode parecer frio/indiferente quando está processando.

3. **O que move de verdade**: Competência e domínio (5w6). Energiza com problemas complexos. Drena com networking superficial.

4. **Onde performa melhor**: Arquitetura técnica, pesquisa profunda, mentoria 1:1. Não em palco ou gerenciando conflitos interpessoais.

5. **Ambiente ideal**: Autonomia + desafio intelectual + estrutura + poucas reuniões. Remote-friendly.

6. **Frameworks convergentes**: Big Five, MBTI, DISC, Enneagram, CliftonStrengths, Kolbe TODOS apontam → pensador analítico introvertido. Convergência 91%.

7. **O que os frameworks podem estar "mentindo"**: DISC adaptado mostra mais extroversão do que Alex realmente tem. A adaptação funciona mas tem custo.

### Confidence Map

| Camada | Score | Classificação | Ação |
|--------|-------|---------------|------|
| Traços | 0.78 | Alta | Proceder |
| Tipos/Estilos | 0.75 | Alta | Proceder |
| Motivação | 0.69 | Moderada | Proceder com ressalva |
| Forças | 0.72 | Alta | Proceder |
| Carreira/Ação | 0.65 | Moderada | Proceder com ressalva |
| Contradições | 0.82 | Alta | Proceder |
| **Global** | **0.74** | **Alta** | **GO** |

### Quality Gate: `synthesis-quality` → **PASS** (Barnum test: PASS, integração multi-camada: completa)

---

## Fase 10: Relatório

### Executive Snapshot (preenchido)

**Quem é Alex:**
- Alta Abertura (percentil 82) → explorador intelectual que busca profundidade antes de agir
- Introvertido funcional (E 38, DISC I adaptado +15) → lidera por competência, não por carisma
- Consciencioso e metódico (C 74, Kolbe 8-7) → confiável para projetos complexos com dependências

**Como Age:**
- INTJ/DISC CS → decide com dados, comunica com precisão, evita confronto desnecessário
- Enneagram 5w6 → prepara-se excessivamente antes de agir, valoriza competência acima de tudo
- SDI Green → em conflito: analisa primeiro, busca harmonia depois, confronta como último recurso

**O Que Move:**
- Domínio e competência (5w6 + Learner + Analytical)
- Energiza: problemas complexos, aprendizado novo, autonomia intelectual
- Drena: reuniões longas sem objetivo, networking superficial, decisões sem dados

**Onde Brilha:**
- Arquitetura técnica, pesquisa profunda, mentoria 1:1, quality reviews
- Melhor fit: papel técnico sênior com influência (Staff/Principal), não gestão de pessoas

**Riscos:**
- Padrão "reluctant-manager" detectado — quer liderar mas não gerenciar
- Custo energético da adaptação extrovertida pode levar a burnout se não gerenciado
- Pode parecer frio/distante sob pressão (Enneagram 5 retrai)

**Confiança: 0.74 (Alta) | Modo: Proxy**

### Plano de Desenvolvimento

| # | Tipo | Ação | Prazo | Evidência |
|---|------|------|-------|-----------|
| 1 | Quick Win | Estruturar "office hours" 1:1 — usa força de mentoria sem drenar energia | 2 semanas | Learner + E 38 |
| 2 | Quick Win | Criar template de comunicação para grupos — compensa introversão com estrutura | 2 semanas | DISC I 35 + C 74 |
| 3 | Estratégico | Desenvolver delegação — Enneagram 5 tende a acumular, precisa soltar | 3 meses | 5w6 + Fact Finder 8 |
| 4 | Estratégico | Programa de exposição gradual: grupos 3→5→10 pessoas | 6 meses | E 38, adaptação +15 |
| 5 | Monitorar | Check-in mensal de energia — burnout de adaptação extrovertida | Contínuo | Delta DISC +15 |

### Quality Gate: `chief-report-approval-quality` → **PASS** (confiança 0.74, Barnum PASS, contradições resolvidas)

---

## Registros Atualizados

- `data/registries/session-index.yaml`: HMS-2026-0042 adicionado
- `data/registries/persona-registry.yaml`: Alex Santos adicionado (status: ativo, confiança: 0.74)
- `data/registries/contradiction-registry.yaml`: 2 contradições registradas (S2, resolvidas)
- `data/registries/lessons-learned.yaml`: Padrão introvert-leader + reluctant-manager combinado documentado

---

## Lições Aprendidas desta Sessão

1. **Padrão combinado** introvert-leader + reluctant-manager é comum em tech leads — documentar em `lib/patterns/`
2. **Adaptação extrovertida alta** (delta DISC +15) é sinal claro de custo energético — monitorar burnout
3. **Enneagram 5w6 com aspiração de liderança** precisa de clarificação: liderança técnica ≠ people management
4. **4 de 5 CliftonStrengths em Strategic Thinking** é forte mas desequilibrado — baixo Influencing é o gap principal
5. **Convergência 91% entre frameworks** dá alta confiança — contradições são S2, não S3/S4

---

*Walkthrough executado seguindo: `workflows/00-start-command-flow.md` → `workflows/09-synthesis-and-integration-flow.md` → `workflows/10-executive-report-generation.md`*

*Versão 2.0.0 — Human-Mapping Squad / MMOS*
