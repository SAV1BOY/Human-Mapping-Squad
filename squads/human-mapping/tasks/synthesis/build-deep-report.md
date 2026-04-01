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

## Subtask Breakdown
1. **Executar deep-report-builder** — Agente: `synthesis-agent`. Input: dados completos + contradiction map + confidence map. Output: rascunho do relatório. Gate: builder executado.
2. **Compor seções por camada** — Agente: `synthesis-agent`. Input: scores + evidências por camada. Output: 10+ seções detalhadas. Gate: nenhuma camada omitida.
3. **Vincular evidências** — Agente: `synthesis-agent`. Input: afirmações + respostas do respondente. Output: `evidence-index`. Gate: cada afirmação-chave com evidência.
4. **Incluir mapa de confiança** — Agente: `synthesis-agent`. Input: confidence map. Output: seção visual de confiança. Gate: status por dimensão incluído.
5. **Formatar e revisar** — Agente: `synthesis-agent`. Input: rascunho completo. Output: `deep-report` final. Gate: template aplicado, limitações documentadas.

## Quality Gate
- [ ] 10+ seções compostas com dados quanti e qualitativos
- [ ] Mapa de confiança incluído
- Threshold: confiança agregada >= 65
- Se FAIL: omitir seções com confiança < 50, documentar motivo

## Rework Trigger
- Seção com confiança < 40 → retornar ao audit para verificação
- Evidências insuficientes em seção → enriquecer com dados brutos ou marcar como "indicativo"
