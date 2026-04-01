# Guia de Fluxos de Trabalho

## Visão Geral
Este guia descreve os fluxos de trabalho operacionais do Human Mapping Squad,
incluindo como projetos são iniciados, executados e finalizados, e como os
agentes colaboram em cada etapa.

## Conteúdo

### Fluxo geral de um projeto
1. **Solicitação**: cliente solicita via canal oficial
2. **Triagem**: agente de intake classifica tipo e urgência
3. **Intake**: coleta de dados e alinhamento de expectativas
4. **Calibração**: seleção de frameworks e plano de avaliação
5. **Execução**: aplicação dos instrumentos e análise
6. **Síntese**: integração e resolução de contradições
7. **Relatório**: geração e revisão do documento final
8. **Entrega**: apresentação ao cliente e coleta de feedback
9. **Registro**: atualização de todos os registries relevantes

### Handoffs entre agentes
- Intake → Avaliação: ficha de intake completa + plano aprovado
- Avaliação → Síntese: dados brutos + análises parciais
- Síntese → Relatório: narrativa integrada + mapa visual
- Relatório → Qualidade: documento para peer review
- Qualidade → Entrega: documento aprovado

### Rituais do squad
- **Daily check**: revisão rápida de projetos em andamento
- **Weekly review**: revisão de qualidade e lições aprendidas
- **Monthly calibration**: recalibração de metodologias e confiança

### Ferramentas
- Registries YAML para rastreamento de dados
- Templates de projeto em Markdown para execução
- Checklists em cada fase para garantir completude

---

## Tabela dos 22 Workflows

| # | Workflow | Trigger | Agentes principais | Output |
|---|---------|---------|-------------------|--------|
| 00 | Start Command | Solicitação do cliente | `human-mapping-chief` | Tipo de projeto definido |
| 01 | Goal & Context | Início de projeto | `intake-orchestrator`, `context-mapper` | Ficha de intake + contexto |
| 02 | Respondent Calibration | Intake completo | `readiness-gatekeeper` | Plano de avaliação aprovado |
| 03 | Trait Assessment | Plano aprovado | `trait-chief`, analistas de traços | Scores Big Five, HEXACO, Hogan |
| 04 | Type/Style Assessment | Plano aprovado | `type-style-chief`, analistas de tipos | Tipos MBTI, perfil DISC |
| 05 | Motivation Assessment | Plano aprovado | `motivation-chief`, analistas de motivação | Tipo Eneagrama, MVPI, Reiss |
| 06 | Strengths Assessment | Plano aprovado | `strengths-chief`, analistas de forças | Top talents, papéis Belbin |
| 07 | Career/Action Assessment | Avaliações completas | `career-fit-analyst`, `riasec-strong-analyst` | Fit vocacional, direcionamento |
| 08 | Contradiction Audit | Todas avaliações prontas | `contradiction-auditor` | Contradições classificadas e resolvidas |
| 09 | Synthesis & Integration | Contradições resolvidas | `synthesis-architect`, `rapport-architect` | Perfil integrado + narrativa |
| 10 | Executive Report | Síntese pronta | `report-writer` | Relatório executivo (2-3 páginas) |
| 11 | Deep Report | Síntese pronta | `report-writer` | Relatório aprofundado (10-15 páginas) |
| 12 | Development Plan | Relatório aprovado | `development-planner` | PDI com metas SMART |
| 13 | Leadership Profile | Solicitação de liderança | Chiefs + Hogan analysts | Perfil de liderança completo |
| 14 | Hiring Assessment | Solicitação de contratação | Subset de analistas | Perfil de candidato + fit |
| 15 | Team Composition | Solicitação de equipe | Belbin, DISC analysts | Mapa de composição + gaps |
| 16 | Career Guidance | Solicitação de carreira | RIASEC, CliftonStrengths | Orientação vocacional |
| 17 | Cross-Squad Handoff | Demanda de outro squad | `human-mapping-chief` | Dados compartilhados com protocolo |
| 18 | Methodology Calibration | Mensal / sob demanda | `human-mapping-chief` | Metodologias recalibradas |
| 19 | Follow-up Reassessment | Após 6-12 meses | Analistas originais | Comparação temporal + evolução |
| 20 | Assessment Retro | Fim de projeto | Todo o squad | Lições aprendidas registradas |
| 21 | Emergency Recovery | Falha no pipeline | `human-mapping-chief` | Sessão recuperada / replanejada |

### Como os Workflows se Encadeiam
Os workflows formam duas cadeias principais:

**Cadeia de avaliação completa (Full Persona)**:
`00 → 01 → 02 → [03, 04, 05, 06 em paralelo] → 07 → 08 → 09 → [10 ou 11] → 12`

Os workflows 03-06 podem rodar em paralelo porque cada camada de avaliação
é independente. O workflow 08 (contradições) precisa de todos os resultados
antes de iniciar. Após o relatório, o workflow 12 (PDI) é opcional.

**Cadeia de projeto reduzido (ex: Hiring)**:
`00 → 01 → 02 → 14 → 08 → 09 → 10`

Projetos reduzidos usam um workflow especializado (13-16) que seleciona
apenas os analistas relevantes, pulando camadas desnecessárias.

**Workflows de suporte** (17-21) podem ser acionados a qualquer momento,
independente da cadeia principal.

## Referências
- `docs/agent-roles-guide.md` — Papéis dos agentes
- `docs/assessment-pipeline-guide.md` — Pipeline de avaliação
- `workflows/` — Definição completa de cada workflow
