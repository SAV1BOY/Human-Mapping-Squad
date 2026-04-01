# Diretorio de Agentes — Human Mapping Squad

## Visao Geral

Este documento indexa todos os 34 agentes do Human Mapping Squad, organizados por camada funcional. Cada agente tem um papel especifico no pipeline de assessment, desde a ingestao de dados ate a geracao de relatorios.

## Camada: Orquestracao e Comando

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 1 | **Human Mapping Chief** | Orquestrador principal do squad. Coordena todos os agentes e o fluxo completo de assessment. | `agents/human-mapping-chief.md` |
| 2 | **Intake Orchestrator** | Gerencia a entrada de dados: coleta informacoes iniciais, valida completude e direciona para analistas. | `agents/intake-orchestrator.md` |
| 3 | **Readiness Gatekeeper** | Valida se ha dados suficientes para prosseguir com o assessment. Controle de qualidade pre-analise. | `agents/readiness-gatekeeper.md` |

## Camada: Chiefs de Dominio

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 4 | **Trait Chief** | Coordena analistas de tracos de personalidade (Big Five, HEXACO, NEO). | `agents/trait-chief.md` |
| 5 | **Type & Style Chief** | Coordena analistas de tipologias (MBTI, Enneagrama, DISC, Insights). | `agents/type-style-chief.md` |
| 6 | **Strengths Chief** | Coordena analistas de forcas (CliftonStrengths, VIA, Belbin). | `agents/strengths-chief.md` |
| 7 | **Motivation Chief** | Coordena analistas de motivacao e valores (MVPI, Reiss, SDI). | `agents/motivation-chief.md` |

## Camada: Analistas de Framework — Tracos

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 8 | **Big Five Analyst** | Interpreta resultados dos 5 grandes fatores de personalidade (OCEAN). | `agents/big-five-analyst.md` |
| 9 | **HEXACO Analyst** | Analisa o modelo HEXACO de 6 fatores incluindo Honestidade-Humildade. | `agents/hexaco-analyst.md` |
| 10 | **NEO/16PF Analyst** | Interpreta NEO-PI-R e 16PF de Cattell em nivel de facetas. | `agents/neo-16pf-analyst.md` |
| 11 | **Hogan Bright Side Analyst** | Analisa HPI (Hogan Personality Inventory) — o lado brilhante. | `agents/hogan-bright-side-analyst.md` |
| 12 | **Hogan Dark Side Analyst** | Interpreta HDS — os 11 derailers e riscos de derailment. | `agents/hogan-dark-side-analyst.md` |

## Camada: Analistas de Framework — Tipologias e Estilos

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 13 | **MBTI Analyst** | Interpreta os 16 tipos Myers-Briggs e funcoes cognitivas. | `agents/mbti-analyst.md` |
| 14 | **Enneagram Analyst** | Analisa os 9 tipos, asas, instintos e niveis de saude. | `agents/enneagram-analyst.md` |
| 15 | **DISC Analyst** | Interpreta perfis DISC e estilos de comunicacao. | `agents/disc-analyst.md` |
| 16 | **Insights/Social Style Analyst** | Analisa Insights Discovery (4 cores) e Social Styles. | `agents/insights-social-style-analyst.md` |
| 17 | **Predictive Index Analyst** | Interpreta PI behavioral assessment e 17 Reference Profiles. | `agents/predictive-index-analyst.md` |

## Camada: Analistas de Framework — Forcas e Conacao

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 18 | **CliftonStrengths Analyst** | Analisa os 34 temas de forca do Gallup StrengthsFinder. | `agents/cliftonstrengths-analyst.md` |
| 19 | **VIA Strengths Analyst** | Interpreta as 24 forcas de carater do VIA Institute. | `agents/via-strengths-analyst.md` |
| 20 | **Belbin Analyst** | Analisa os 9 papeis de equipe de Belbin. | `agents/belbin-analyst.md` |
| 21 | **Kolbe Analyst** | Interpreta os 4 modos de acao do Kolbe A Index. | `agents/kolbe-analyst.md` |

## Camada: Analistas de Framework — Motivacao e Valores

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 22 | **MVPI/Driving Forces Analyst** | Analisa Hogan MVPI e outros inventarios de valores/motivos. | `agents/mvpi-driving-forces-analyst.md` |
| 23 | **Reiss Analyst** | Interpreta os 16 desejos basicos do Reiss Motivation Profile. | `agents/reiss-analyst.md` |
| 24 | **SDI Analyst** | Analisa SDI 2.0: MVS, sequencia de conflito e forcas exageradas. | `agents/sdi-analyst.md` |
| 25 | **FIRO/PCM/Birkman Analyst** | Interpreta FIRO-B, Process Communication Model e Birkman Method. | `agents/firo-pcm-birkman-analyst.md` |

## Camada: Analistas de Framework — Carreira

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 26 | **RIASEC/Strong Analyst** | Analisa codigos Holland RIASEC e Strong Interest Inventory. | `agents/riasec-strong-analyst.md` |
| 27 | **Career Fit Analyst** | Avalia adequacao carreira-pessoa integrando multiplos frameworks. | `agents/career-fit-analyst.md` |

## Camada: Integracao e Sintese

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 28 | **Context Mapper** | Mapeia contexto organizacional, cultural e situacional do avaliado. | `agents/context-mapper.md` |
| 29 | **Contradiction Auditor** | Identifica e resolve contradicoes entre resultados de diferentes frameworks. | `agents/contradiction-auditor.md` |
| 30 | **Respondent Quality Auditor** | Avalia qualidade e confiabilidade das respostas do avaliado. | `agents/respondent-quality-auditor.md` |
| 31 | **Synthesis Architect** | Integra todas as analises em um perfil unificado e coerente. | `agents/synthesis-architect.md` |

## Camada: Output e Comunicacao

| # | Agente | Papel | Arquivo |
|---|--------|-------|---------|
| 32 | **Development Planner** | Cria planos de desenvolvimento individualizados baseados no perfil integrado. | `agents/development-planner.md` |
| 33 | **Rapport Architect** | Projeta a melhor abordagem de comunicacao para a devolutiva. | `agents/rapport-architect.md` |
| 34 | **Report Writer** | Gera o relatorio final em formato e linguagem adequados ao publico-alvo. | `agents/report-writer.md` |

## Fluxo de Ativacao

```
Intake Orchestrator → Readiness Gatekeeper → Chiefs de Dominio → Analistas
    → Contradiction Auditor → Respondent Quality Auditor
    → Synthesis Architect → Development Planner
    → Rapport Architect → Report Writer
    → Human Mapping Chief (validacao final)
```

## Notas de Navegacao

- Todos os arquivos de agente estao em `squads/human-mapping/agents/`.
- Cada agente documenta: papel, inputs, outputs, regras de operacao e dependencias.
- O Human Mapping Chief e o unico agente com autoridade para sobrescrever decisoes de outros agentes.
- Para entender como os agentes interagem, consulte `docs/workflow-guide.md`.
