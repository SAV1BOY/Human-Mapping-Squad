---
type: task
squad: human-mapping
version: "2.0.0"
agent: synthesis-agent
workflow: synthesis-workflow
---

# Task: Construir Relatório Profundo

## Objetivo

Construir o relatório profundo e detalhado do perfil humano, cobrindo todas as dimensões avaliadas com análise aprofundada, evidências, nuances e recomendações específicas.

## Pré-condições

- Perfil integrado sintetizado
- Snapshot executivo construído
- Profundidade da sessão é `/start` ou `/deep`
- Confiança agregada >= 65

## Passos

1. Executar `scripts/reporting/deep-report-builder.md` com dados completos do perfil
2. Estruturar o relatório com as seguintes seções:
   - **Sumário Executivo**: Versão expandida do snapshot (2-3 parágrafos)
   - **Perfil de Personalidade**: Análise detalhada OCEAN com facetas, comparação com normas populacionais
   - **Tradução para o Trabalho**: Bright side, dark side e valores (Hogan), impacto prático no dia a dia
   - **Estilo Cognitivo**: Tipo, funções cognitivas, estilo de aprendizagem e tomada de decisão
   - **Mapa Motivacional**: Hierarquia de motivadores com cenários ilustrativos
   - **Inventário de Forças**: Top forças, forças subutilizadas, oportunidades de desenvolvimento
   - **Dinâmica de Equipe**: Papéis Belbin, estilo de colaboração, contribuições e gaps
   - **Fit de Carreira**: Análise RIASEC, ambientes ideais, carreiras compatíveis
   - **Modo de Ação**: Perfil Kolbe, estilo operacional, dicas de produtividade
   - **Análise Integrada**: Temas centrais, paradoxos produtivos, narrativa unificada
   - **Mapa de Confiança**: Visualização da confiança por dimensão
3. Para cada seção, incluir:
   - Dados quantitativos (scores, percentis)
   - Interpretação qualitativa em linguagem acessível
   - Evidências das respostas do respondente
   - Implicações práticas
4. Adicionar seção de limitações e metodologia
5. Formatar conforme template profundo do squad

## Outputs

- `deep-report`: Relatório profundo completo formatado
- `report-metadata`: Metadados do relatório (sessão, data, confiança, versão)
- `evidence-index`: Índice de evidências citadas no relatório

## Checklist de Conclusão

- [ ] Deep report builder executado
- [ ] Todas as 10+ seções compostas
- [ ] Dados quantitativos e qualitativos incluídos
- [ ] Evidências vinculadas a cada afirmação
- [ ] Implicações práticas documentadas
- [ ] Limitações e metodologia incluídas
- [ ] Mapa de confiança gerado
- [ ] Formatação conforme template

## Próxima Task

`tasks/synthesis/build-development-plan.md` — Construir plano de desenvolvimento
