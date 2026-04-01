# Começando com o Human Mapping Squad

## Visão Geral
Este guia apresenta os primeiros passos para utilizar os serviços e recursos do
Human Mapping Squad. Seja você um novo membro do squad, um cliente interno ou
um colaborador de outro squad, aqui você encontra o ponto de partida.

## Conteúdo

### Para novos membros do squad
1. Leia o `squad-overview.md` para entender missão, visão e estrutura
2. Consulte o `agent-roles-guide.md` para entender os papéis dos agentes
3. Familiarize-se com os frameworks em `authority/framework-summaries/`
4. Revise o `workflow-guide.md` para entender os fluxos de trabalho
5. Leia o `ethical-use-policy.md` — leitura obrigatória antes de operar

### Para clientes internos
1. Identifique o tipo de projeto que você precisa em `projects/`
2. Consulte o `assessment-pipeline-guide.md` para entender o processo
3. Solicite um projeto via canal oficial do squad
4. Acompanhe o progresso conforme cronograma acordado

### Para squads parceiros
1. Leia o `cross-squad-integration-guide.md` para entender interfaces
2. Consulte o `naming-conventions.md` para padronização de dados
3. Registre entregas no `cross-squad-deliveries.yaml`

---

## Seu Primeiro Assessment em 5 Passos

Se você quer executar um mapeamento de persona do início ao fim, siga este roteiro:

### Passo 1 — Definir objetivo e escopo (15 min)
Abra o workflow `00-start-command-flow.md` e responda: qual o propósito do mapeamento?
Isso determina o tipo de projeto (Full Persona, Leadership, Hiring, etc.) e quais
frameworks serão candidatos. Registre no template de intake do projeto correspondente
em `projects/`.

### Passo 2 — Executar intake e calibração (30-60 min)
O `intake-orchestrator` coleta dados do respondente e o `readiness-gatekeeper` valida
se há dados suficientes para prosseguir. Consulte `02-respondent-calibration.md` para
o fluxo de calibração. Ao final, você terá um plano de avaliação aprovado com
frameworks selecionados e nível de confiança-alvo.

### Passo 3 — Rodar os fluxos de avaliação (1-3 dias)
Execute os workflows de avaliação na ordem:
- `03-trait-assessment-flow.md` (Big Five, HEXACO, NEO/16PF)
- `04-type-style-assessment-flow.md` (MBTI, DISC, Insights)
- `05-motivation-assessment-flow.md` (MVPI, Eneagrama, Reiss)
- `06-strengths-assessment-flow.md` (CliftonStrengths, VIA, Belbin)
Cada fluxo envolve os agentes analistas especializados e o chief da camada.

### Passo 4 — Resolver contradições e sintetizar (2-4 horas)
O `contradiction-auditor` identifica divergências entre frameworks. O
`synthesis-architect` integra tudo em um perfil coerente. Consulte
`08-contradiction-audit-flow.md` e `09-synthesis-and-integration-flow.md`.

### Passo 5 — Gerar e entregar o relatório (1-2 horas)
O `report-writer` gera o documento final. Escolha entre relatório executivo
(`10-executive-report-generation.md`) ou aprofundado (`11-deep-report-generation.md`).
Revise com o checklist de qualidade antes de entregar.

> **Walkthrough completo**: para um exemplo passo a passo com dados reais, consulte
> o projeto-template em `projects/full-persona-mapping/` que contém todas as fases
> documentadas com exemplos.

## Referências
- `docs/squad-overview.md` — Visão geral do squad
- `docs/workflow-guide.md` — Guia de fluxos de trabalho
- `docs/contribution-guide.md` — Como contribuir
- `docs/assessment-pipeline-guide.md` — Pipeline completo de avaliação
- `docs/framework-selection-guide.md` — Como escolher frameworks
