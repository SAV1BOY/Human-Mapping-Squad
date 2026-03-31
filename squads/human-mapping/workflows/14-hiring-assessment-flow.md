---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Objetivo de mapeamento classificado como contratacao/selecao"
agents: [synthesis-architect, chief, report-writer, career-fit-analyst]
quality_gates: [role-requirements-checklist, fit-assessment-checklist, bias-check-checklist]
---

# Workflow: Assessment para Contratacao

## Trigger

Ativado quando o objetivo do mapeamento e avaliar fit de um candidato para uma vaga ou funcao especifica. Requer input de requisitos da funcao.

## Pre-condicoes

- Workflows 03 a 09 concluidos (assessment completo + auditoria).
- Mapa unificado disponivel.
- **OBRIGATORIO:** Requisitos da funcao fornecidos pelo contratante (role requirements input).

## Sequencia

### Passo 1: Coletar Requisitos da Funcao
- **Agente:** chief
- **Acao:** Coleta e estrutura os requisitos da funcao alvo:
  - **Titulo e descricao da funcao.**
  - **Competencias tecnicas requeridas** (nao avaliadas por este squad, apenas registradas).
  - **Competencias comportamentais requeridas** (foco do assessment).
  - **Cultura da equipe/organizacao** (estilo de gestao, ritmo, valores).
  - **Desafios especificos da funcao** (ex: liderar equipe em crise, inovar produto, estabilizar operacao).
  - **Perfil do gestor direto** (se disponivel, para avaliar compatibilidade).
  - **Deal-breakers** (comportamentos absolutamente inaceitaveis).
- **Decisao:** Se requisitos sao vagos, solicitar refinamento antes de prosseguir. Minimo: competencias comportamentais + cultura.
- **Output:** `requisitos_funcao{}`.

### Passo 2: Traduzir Requisitos para Perfil Ideal
- **Agente:** career-fit-analyst
- **Acao:** Converte requisitos da funcao em perfil comportamental ideal usando os mesmos frameworks do assessment:
  - Faixas ideais de Big Five para a funcao.
  - Tipos MBTI/DISC mais compatíveis.
  - Motivacoes que sustentariam engajamento na funcao.
  - Forcas Clifton/Belbin mais relevantes.
  - RIASEC/Kolbe alinhados com a natureza do trabalho.
- **Decisao:** Perfil ideal deve ter faixas (nao valores exatos) para permitir diversidade. Evitar "clone perfeito".
- **Output:** `perfil_ideal_funcao{}`, `faixas_aceitaveis{}`, `deal_breakers_comportamentais[]`.

### Passo 3: Calcular Fit Comportamental
- **Agente:** synthesis-architect
- **Acao:** Compara mapa unificado do candidato com perfil ideal da funcao:
  - **Fit por camada:** Score de 0-100 para cada camada (tracos, tipos, motivacao, forcas, carreira).
  - **Fit geral ponderado:** Media ponderada conforme relevancia de cada camada para a funcao.
  - **Areas de forte alinhamento:** Onde candidato excede expectativas.
  - **Areas de gap:** Onde candidato fica abaixo do ideal.
  - **Deal-breakers ativados:** Se algum deal-breaker comportamental e positivo.
- **Decisao:** Se deal-breaker ativado, sinalizar imediatamente independente do fit geral.
- **Output:** `fit_por_camada{}`, `fit_geral`, `alinhamentos_fortes[]`, `gaps[]`, `deal_breakers_status[]`.

### Passo 4: Avaliar Riscos de Contratacao
- **Agente:** synthesis-architect
- **Acao:** Identifica riscos especificos de colocar este candidato nesta funcao:
  - **Risco de desengajamento:** Motivacao do candidato vs demandas da funcao.
  - **Risco de conflito cultural:** Estilo do candidato vs cultura da organizacao.
  - **Risco de burnout:** Tracos que podem ser sobre-exigidos pela funcao.
  - **Risco de subdesempenho:** Gaps que nao sao facilmente desenvolviveis.
  - **Risco de turnover:** Indicadores de que candidato pode sair em <12 meses.
  - Cada risco com probabilidade (baixa/media/alta) e impacto.
- **Output:** `riscos_contratacao[]`, `risco_geral_classificacao`.

### Passo 5: Gerar Relatorio de Contratacao
- **Agente:** report-writer
- **Acao:** Redige documento de assessment para contratacao:
  - **Parecer executivo:** 1 paragrafo — recomendacao clara (fortemente recomendado, recomendado com ressalvas, nao recomendado).
  - **Fit comportamental:** Grafico radar comparando candidato vs perfil ideal.
  - **Pontos fortes para a funcao:** O que o candidato traz de melhor.
  - **Pontos de atencao:** Gaps e riscos com mitigacoes possiveis.
  - **Compatibilidade com gestor/equipe:** Se dados disponiveis.
  - **Sugestao de onboarding:** Personalizacoes para os primeiros 90 dias.
  - **Perguntas para entrevista:** 3-5 perguntas comportamentais para explorar gaps identificados.
- **Decisao:** Tom neutro e baseado em dados. Nunca "aprovar" ou "reprovar" — apenas informar.
- **Output:** `relatorio_contratacao_final`.

### Passo 6: Validacao Anti-Vies
- **Agente:** chief
- **Acao:** Revisa relatorio contra vieses conhecidos:
  - Efeito halo (um ponto forte ofuscando fraquezas).
  - Vies de similaridade (perfil ideal = clone do gestor).
  - Vies cultural (penalizar estilos de minorias).
  - Determinismo (tratar assessment como verdade absoluta).
  - Linguagem discriminatoria ou exclusoria.
- **Decisao:** Se vies detectado, revisar e ajustar antes de entregar.
- **Output:** `validacao_anti_vies_ok` (boolean), `ajustes_realizados[]`.

## Quality Gates (checkpoints)

- [ ] Requisitos da funcao coletados com competencias comportamentais definidas.
- [ ] Perfil ideal gerado com faixas (nao valores rigidos).
- [ ] Fit calculado por camada e geral.
- [ ] Riscos de contratacao mapeados com probabilidade e impacto.
- [ ] Relatorio inclui recomendacao clara, pontos fortes e atencao.
- [ ] Validacao anti-vies realizada.
- [ ] Perguntas para entrevista geradas.
- [ ] Linguagem neutra e baseada em evidencias.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_contratacao_final` | Markdown/PDF | Contratante |
| `fit_por_camada{}` + `fit_geral` | JSON | Arquivo, comparacao entre candidatos |
| `riscos_contratacao[]` | Array | Contratante, onboarding |
| `perguntas_entrevista[]` | Array | Entrevistadores |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Requisitos da funcao nao fornecidos | BLOQUEAR. Nao gerar relatorio de contratacao sem requisitos. Solicitar ao contratante. |
| Fit geral muito baixo (<30%) | Comunicar com cuidado. Pode ser que a funcao nao e adequada, NAO que o candidato e inadequado. |
| Gestor insiste em "perfil perfeito" | Educar sobre diversidade cognitiva e riscos de homogeneidade. Ajustar faixas. |
| Candidato descobre resultado negativo | Relatorio para candidato foca em autoconhecimento, nao em fit. Separar versoes. |

## Proximo Workflow

- `17-cross-squad-handoff-flow.md` (se contratante e outro squad)
- `15-team-composition-flow.md` (se avaliando multiplos candidatos)
