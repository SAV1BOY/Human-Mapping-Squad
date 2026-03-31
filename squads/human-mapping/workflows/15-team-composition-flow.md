---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Objetivo de mapeamento classificado como composicao ou dinamica de equipe"
agents: [synthesis-architect, chief, report-writer, development-planner]
quality_gates: [multi-profile-checklist, team-dynamics-checklist, diversity-balance-checklist]
---

# Workflow: Composicao de Equipe

## Trigger

Ativado quando o objetivo envolve avaliar, montar ou otimizar uma equipe. Requer assessment de multiplos individuos.

## Pre-condicoes

- Pelo menos 2 individuos mapeados (workflows 03-09 completos para cada).
- Mapas unificados individuais disponiveis.
- Contexto da equipe: missao, desafios, cultura desejada.

## Sequencia

### Passo 1: Coletar Contexto da Equipe
- **Agente:** chief
- **Acao:** Mapeia o contexto coletivo:
  - Missao e objetivos da equipe.
  - Tamanho atual e desejado.
  - Desafios enfrentados (conflitos, baixa performance, silos, etc.).
  - Cultura de equipe atual vs desejada.
  - Lider da equipe (ja mapeado? Se sim, vincular perfil).
  - Fase da equipe (formacao, tempestade, normatizacao, desempenho, dissolucao — Tuckman).
- **Output:** `contexto_equipe{}`.

### Passo 2: Consolidar Perfis Individuais
- **Agente:** synthesis-architect
- **Acao:** Reune mapas unificados de todos os membros em formato comparavel:
  - Tabela comparativa de Big Five por membro.
  - Distribuicao de tipos MBTI/DISC na equipe.
  - Distribuicao de Belbin Roles (quais papeis cobertos, quais faltam).
  - Mapa motivacional coletivo (convergencias e divergencias).
  - Clifton: dominios representados na equipe.
- **Output:** `matriz_comparativa_equipe{}`, `membros_perfis[]`.

### Passo 3: Analisar Dinamica de Equipe
- **Agente:** synthesis-architect
- **Acao:** Avalia interacoes e dinamicas potenciais:
  - **Complementaridade:** Onde membros complementam pontos cegos uns dos outros.
  - **Redundancia:** Onde multiplos membros tem o mesmo perfil (risco de competicao).
  - **Lacunas:** Papeis Belbin, tipos DISC ou dominios Clifton nao representados.
  - **Pontos de atrito potenciais:** Combinacoes de tipos que tipicamente geram conflito.
  - **Sinergia potencial:** Combinacoes que tipicamente geram alta performance.
  - **Diversidade cognitiva:** Score de diversidade de estilos de pensamento na equipe.
- **Decisao:** Se lacunas criticas detectadas, recomendar perfil ideal para proxima contratacao.
- **Output:** `analise_dinamica{}`, `lacunas_criticas[]`, `pontos_atrito[]`, `sinergias[]`, `score_diversidade`.

### Passo 4: Mapear Compatibilidade entre Pares
- **Agente:** synthesis-architect
- **Acao:** Para cada par de membros, calcula score de compatibilidade:
  - Compatibilidade de comunicacao (DISC + MBTI).
  - Compatibilidade de valores (Reiss + MVPI).
  - Compatibilidade de trabalho (Kolbe + Belbin).
  - Potenciais de conflito (SDI sequencias de conflito cruzadas).
  - Gera matriz N x N de compatibilidade.
- **Decisao:** Pares com compatibilidade < 30% sao sinalizados como "requer atencao".
- **Output:** `matriz_compatibilidade_pares{}`, `pares_atencao[]`, `pares_sinergia[]`.

### Passo 5: Gerar Recomendacoes de Equipe
- **Agente:** synthesis-architect
- **Acao:** Produz recomendacoes acionaveis:
  - **Configuracao ideal de sub-equipes** para projetos especificos.
  - **Protocolo de comunicacao** adaptado aos perfis (quem prefere email, quem prefere call, etc.).
  - **Regras de engajamento** para reunioes baseadas nos estilos.
  - **Gestao de conflito** com estrategias especificas para os pares de atrito.
  - **Perfil ideal** para proxima contratacao que preencha lacunas.
  - **Desenvolvimento coletivo:** Areas onde toda equipe se beneficiaria.
- **Output:** `recomendacoes_equipe[]`.

### Passo 6: Gerar Relatorio de Equipe
- **Agente:** report-writer
- **Acao:** Redige documento de composicao de equipe:
  - Visao geral: "DNA comportamental da equipe" em 1 paragrafo.
  - Mapa visual da equipe (distribuicao de tipos/estilos).
  - Forcas coletivas: o que essa equipe faz muito bem junto.
  - Vulnerabilidades coletivas: onde a equipe tende a falhar.
  - Dinamica de pares: destaques de sinergia e atrito.
  - Recomendacoes priorizadas.
  - Perfil de contratacao sugerido (se lacunas existem).
  - Plano de team building personalizado.
- **Output:** `relatorio_equipe_final`.

## Quality Gates (checkpoints)

- [ ] Minimo 2 membros mapeados com workflows 03-09 completos.
- [ ] Matriz comparativa gerada com todos os frameworks relevantes.
- [ ] Dinamica analisada com complementaridade, redundancia e lacunas.
- [ ] Matriz de compatibilidade entre pares calculada.
- [ ] Recomendacoes acionaveis e especificas (nao genericas).
- [ ] Diversidade cognitiva avaliada.
- [ ] Relatorio inclui visao coletiva (nao apenas soma de individuais).

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_equipe_final` | Markdown/PDF | Lider da equipe, stakeholders |
| `matriz_comparativa_equipe{}` | JSON | Arquivo, reavaliacao |
| `matriz_compatibilidade_pares{}` | JSON | Gestao de conflito |
| `perfil_contratacao_sugerido{}` | JSON | Workflow 14 (hiring) |
| `recomendacoes_equipe[]` | Array | Development-planner |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Apenas 1 membro mapeado | Gerar perfil individual + recomendacoes de perfis complementares. Nao gerar analise de dinamica. |
| Membros mapeados em momentos diferentes | Registrar datas. Se gap > 6 meses, sugerir reavaliacao dos mais antigos. |
| Equipe muito homogenea | Alertar sobre riscos de pensamento de grupo. Recomendar diversificacao. |
| Lider da equipe nao mapeado | Recomendar mapeamento do lider. Analise parcial sem lider pode ser imprecisa. |

## Proximo Workflow

- `14-hiring-assessment-flow.md` (para preencher lacunas com contratacao)
- `12-development-plan-generation.md` (plano de desenvolvimento coletivo)
- `17-cross-squad-handoff-flow.md` (se equipe e de outro squad)
