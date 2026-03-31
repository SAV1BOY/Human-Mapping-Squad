---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 09-synthesis com objetivo de desenvolvimento pessoal/profissional"
agents: [development-planner]
quality_gates: [plan-actionability-checklist, plan-alignment-checklist]
---

# Workflow: Geracao de Plano de Desenvolvimento

## Trigger

Ativado quando o objetivo do mapeamento inclui desenvolvimento pessoal ou profissional. Recebe `mapa_unificado{}` e `secao_recomendacoes` do relatorio profundo.

## Pre-condicoes

- Mapa unificado disponivel com todas as camadas relevantes.
- Recomendacoes do relatorio profundo geradas.
- Contexto do respondente (momento de carreira, organizacao) disponivel.

## Sequencia

### Passo 1: Identificar Areas de Desenvolvimento
- **Agente:** development-planner
- **Acao:** Analisa mapa unificado para identificar areas prioritarias:
  - **Forcas subutilizadas:** Talentos Clifton/VIA nao aplicados no trabalho atual.
  - **Pontos cegos criticos:** Riscos que podem limitar crescimento.
  - **Gaps de competencia:** Distancia entre perfil atual e requisitos do proximo passo de carreira.
  - **Motivacao desalinhada:** Motor motivacional nao atendido no contexto atual.
  - **Estresse cronico:** Indicadores de desalinhamento DISC natural vs adaptado.
- **Decisao:** Priorizar maximo 5 areas. Mais que isso dilui foco e reduz execucao.
- **Output:** `areas_desenvolvimento[]` (max 5), `prioridade_justificada{}`.

### Passo 2: Definir Metas SMART
- **Agente:** development-planner
- **Acao:** Para cada area de desenvolvimento, cria meta SMART:
  - **Especifica:** O que exatamente sera desenvolvido.
  - **Mensuravel:** Como saber que houve progresso.
  - **Alcancavel:** Realista dado o perfil e contexto.
  - **Relevante:** Conectada ao objetivo e ao motor motivacional.
  - **Temporal:** Prazo definido com marcos intermediarios.
- **Decisao:** Se meta parece inatingivel dado o perfil de tracos, ajustar para meta mais realista ou dividir em sub-metas.
- **Output:** `metas_smart[]` (1 por area).

### Passo 3: Desenhar Estrategias por Perfil
- **Agente:** development-planner
- **Acao:** Personaliza estrategias de desenvolvimento conforme o perfil mapeado:
  - **Conforme MBTI/Kolbe:** Sugere metodos de aprendizado alinhados ao tipo cognitivo e modo de acao.
  - **Conforme Eneagrama:** Usa direcoes de integracao como guia de crescimento.
  - **Conforme Clifton:** Aplica abordagem strengths-based (desenvolver forcas > corrigir fraquezas).
  - **Conforme DISC:** Ajusta abordagem ao estilo natural (D=desafios, I=social, S=gradual, C=estruturado).
  - **Conforme SDI:** Considera motivacao em conflito para preparar resiliencia.
- **Output:** `estrategias_personalizadas[]`, cada uma com metodo + justificativa baseada no perfil.

### Passo 4: Criar Cronograma de Desenvolvimento
- **Agente:** development-planner
- **Acao:** Estrutura plano temporal:
  - **Fase 1 - Quick Wins (0-30 dias):** 2-3 acoes imediatas de baixo esforco e alto impacto.
  - **Fase 2 - Construcao (1-3 meses):** Habitos e praticas regulares para desenvolver.
  - **Fase 3 - Consolidacao (3-6 meses):** Desafios maiores, aplicacao em contextos reais.
  - **Fase 4 - Integracao (6-12 meses):** Novos comportamentos incorporados como habitos.
  - Cada fase com: acoes especificas, recursos sugeridos, indicadores de progresso.
- **Decisao:** Se respondente tem urgencia (ex: promocao iminente), comprimir fases 1 e 2.
- **Output:** `cronograma_desenvolvimento{}`.

### Passo 5: Definir Mecanismos de Acompanhamento
- **Agente:** development-planner
- **Acao:** Estabelece como o progresso sera monitorado:
  - Check-ins sugeridos (frequencia baseada no perfil: D/I=quinzenal, S/C=mensal).
  - Indicadores quantitativos e qualitativos por meta.
  - Triggers para reavaliacao: se meta nao avanca em 2 ciclos, revisar estrategia.
  - Sugestao de accountability partner ou mentor (perfil ideal baseado no mapa).
  - Data sugerida para reassessment completo (workflow 19).
- **Output:** `mecanismos_acompanhamento{}`, `data_reassessment_sugerida`.

### Passo 6: Compilar Plano Final
- **Agente:** development-planner
- **Acao:** Gera documento do plano de desenvolvimento com:
  - Resumo do perfil (extraido do executivo).
  - Areas de desenvolvimento priorizadas.
  - Metas SMART.
  - Estrategias personalizadas com justificativa.
  - Cronograma com 4 fases.
  - Mecanismos de acompanhamento.
  - Compromisso: espaco para respondente assinar/confirmar comprometimento.
- **Output:** `plano_desenvolvimento_final`.

## Quality Gates (checkpoints)

- [ ] Maximo 5 areas de desenvolvimento priorizadas.
- [ ] Cada meta e SMART e vinculada ao mapa comportamental.
- [ ] Estrategias personalizadas conforme pelo menos 3 frameworks do perfil.
- [ ] Cronograma com 4 fases e acoes especificas em cada.
- [ ] Quick wins definidos para gerar momentum imediato.
- [ ] Mecanismos de acompanhamento realistas e personalizados.
- [ ] Plano e acionavel (respondente sabe exatamente o que fazer amanha).

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `plano_desenvolvimento_final` | Markdown/PDF | Usuario |
| `metas_smart[]` | JSON | Acompanhamento, reassessment |
| `cronograma_desenvolvimento{}` | JSON | Follow-up |
| `data_reassessment_sugerida` | Data | Workflow 19 |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Muitas areas identificadas (>5) | Forcar priorizacao: qual area, se desenvolvida, gera mais impacto no objetivo? |
| Metas parecem genericas | Vincular explicitamente a dados do mapa. "Porque SEU perfil X, a meta Y funciona assim..." |
| Respondente resiste ao plano | Explorar resistencia: medo de mudanca? Meta desalinhada com motivacao? Ajustar. |
| Contexto organizacional impede execucao | Adaptar estrategias para o que e possivel. Sugerir conversa com gestor se aplicavel. |

## Proximo Workflow

- `19-follow-up-reassessment-flow.md` (na data sugerida)
- `17-cross-squad-handoff-flow.md` (se desenvolvimento requer recursos de outro squad)
