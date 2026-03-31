---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Objetivo de mapeamento classificado como orientacao de carreira"
agents: [career-fit-analyst, synthesis-architect, report-writer, development-planner]
quality_gates: [career-alignment-checklist, options-viability-checklist]
---

# Workflow: Orientacao de Carreira

## Trigger

Ativado quando o objetivo do mapeamento e orientar decisoes de carreira: transicao, reinvencao, escolha de especializacao, ou alinhamento profissional.

## Pre-condicoes

- Workflows 03 a 09 concluidos (assessment completo + auditoria).
- Mapa unificado disponivel.
- Momento de carreira do respondente identificado (inicio, transicao, consolidacao, reinvencao).

## Sequencia

### Passo 1: Diagnosticar Situacao Atual de Carreira
- **Agente:** career-fit-analyst
- **Acao:** Avalia alinhamento entre perfil comportamental e posicao atual:
  - Score de alinhamento RIASEC vs funcao atual.
  - Score de alinhamento motivacional (Reiss/Eneagrama) vs ambiente atual.
  - Score de uso de forcas (Clifton/VIA) no dia a dia.
  - Score de estilo (DISC/MBTI) vs cultura organizacional.
  - Nivel de satisfacao inferido (combinacao dos scores acima).
  - Kolbe: modo de acao natural vs demandas da funcao.
- **Decisao:** Classificar situacao: alinhado, parcialmente alinhado, desalinhado, criticamente desalinhado.
- **Output:** `diagnostico_carreira_atual{}`, `scores_alinhamento{}`, `classificacao_alinhamento`.

### Passo 2: Mapear Aspiracoes e Restricoes
- **Agente:** career-fit-analyst
- **Acao:** Coleta informacoes adicionais do respondente:
  - Aspiracoes de carreira: onde gostaria de estar em 1, 3, 5, 10 anos.
  - Restricoes reais: geograficas, financeiras, familiares, de formacao.
  - Experiencias anteriores: o que ja tentou e como foi.
  - Valores inegociaveis: o que jamais abriria mao em um trabalho.
  - Medos e barreiras percebidas.
- **Decisao:** Se aspiracoes contraditam perfil comportamental, explorar (nao descartar — pode ser crescimento genuino).
- **Output:** `aspiracoes_carreira{}`, `restricoes_reais[]`, `valores_inegociaveis[]`, `barreiras_percebidas[]`.

### Passo 3: Gerar Opcoes de Carreira
- **Agente:** career-fit-analyst
- **Acao:** Cruza perfil comportamental + aspiracoes + restricoes para gerar opcoes:
  - **Opcao A — Otimizacao:** Ajustes na funcao/empresa atual para melhorar alinhamento.
  - **Opcao B — Transicao interna:** Mudanca de funcao ou area dentro da mesma organizacao.
  - **Opcao C — Transicao externa:** Mudanca de organizacao mantendo area similar.
  - **Opcao D — Reinvencao:** Mudanca de area/industria para novo campo.
  - **Opcao E — Empreendedorismo:** Se perfil indica (alto Quick Start Kolbe, alta D DISC, tipo E RIASEC).
  - Para cada opcao: viabilidade (baixa/media/alta), alinhamento com perfil, esforco necessario, risco.
- **Decisao:** Se alguma opcao e claramente inviavel (restricoes duras), marcar mas nao excluir — informar.
- **Output:** `opcoes_carreira[]` (3-5 opcoes viáveis), cada uma com analise detalhada.

### Passo 4: Analisar Trade-offs
- **Agente:** synthesis-architect
- **Acao:** Para cada opcao viavel, mapeia trade-offs:
  - O que ganha vs o que perde em cada cenario.
  - Impacto na motivacao (sustentavel vs temporario).
  - Impacto no uso de forcas.
  - Riscos comportamentais (perfil sob pressao neste cenario).
  - Tempo e investimento para concretizar.
  - Alinhamento com valores inegociaveis.
- **Output:** `analise_trade_offs{}` por opcao.

### Passo 5: Gerar Relatorio de Orientacao de Carreira
- **Agente:** report-writer
- **Acao:** Redige documento de orientacao:
  - Diagnostico atual: "Onde voce esta e por que se sente assim."
  - Perfil em linguagem de carreira: "Voce e o tipo de profissional que..."
  - Opcoes mapeadas com pros, contras e viabilidade.
  - Analise de trade-offs em formato comparativo.
  - Recomendacao sugerida (sem impor — apresentar como a mais alinhada).
  - Primeiros passos concretos para a opcao escolhida.
  - Nota: "A decisao final e sempre sua."
- **Output:** `relatorio_carreira_final`.

### Passo 6: Gerar Plano de Transicao
- **Agente:** development-planner
- **Acao:** Se respondente escolhe uma opcao, cria plano de transicao:
  - **Fase 1 — Preparacao (0-3 meses):** Pesquisa, networking, upskilling.
  - **Fase 2 — Posicionamento (3-6 meses):** Marca pessoal, portfolio, conexoes.
  - **Fase 3 — Execucao (6-12 meses):** Candidatura, entrevistas, negociacao.
  - **Fase 4 — Integracao (12-18 meses):** Primeiros meses no novo contexto.
  - Cada fase personalizada conforme perfil comportamental.
- **Decisao:** Se respondente nao escolhe opcao imediata, gerar plano de exploracao ao inves de transicao.
- **Output:** `plano_transicao_carreira{}` ou `plano_exploracao_carreira{}`.

## Quality Gates (checkpoints)

- [ ] Diagnostico atual com scores de alinhamento por dimensao.
- [ ] Aspiracoes e restricoes coletadas diretamente do respondente.
- [ ] Minimo 3 opcoes de carreira viáveis geradas.
- [ ] Trade-offs analisados para cada opcao.
- [ ] Relatorio em tom de orientacao (nao imposicao).
- [ ] Plano de transicao ou exploracao personalizado conforme perfil.
- [ ] Valores inegociaveis respeitados em todas as opcoes.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_carreira_final` | Markdown/PDF | Respondente |
| `opcoes_carreira[]` | JSON | Arquivo, follow-up |
| `diagnostico_carreira_atual{}` | JSON | Reavaliacao futura |
| `plano_transicao_carreira{}` | JSON | Follow-up, development-planner |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Respondente nao sabe o que quer | Normal. Usar perfil para sugerir direcoes. Plano de exploracao ao inves de transicao. |
| Aspiracao completamente desalinhada do perfil | Nao invalidar. Explorar: "O que nesta area te atrai?" Pode revelar motivacao latente. |
| Restricoes eliminam todas as opcoes boas | Buscar solucoes criativas. Opcoes hibridas, graduais, ou de longo prazo. |
| Respondente entra em crise existencial durante processo | Rapport-architect retoma. Normalizar a duvida. Sugerir pausa e reflexao. |

## Proximo Workflow

- `12-development-plan-generation.md` (complementar ao plano de carreira)
- `19-follow-up-reassessment-flow.md` (reavaliacao apos transicao)
