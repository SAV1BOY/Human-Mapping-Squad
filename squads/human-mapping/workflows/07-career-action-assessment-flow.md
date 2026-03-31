---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 06-strengths-assessment-flow"
agents: [career-fit-analyst, riasec-analyst, kolbe-analyst]
quality_gates: [career-fit-checklist, action-mode-checklist]
---

# Workflow: Assessment de Carreira e Modo de Acao

## Trigger

Recebe handoff do `06-strengths-assessment-flow.md` apos conclusao da camada de forcas.

## Pre-condicoes

- Camadas de tracos, tipos, motivacao e forcas concluidas.
- Camada de carreira/acao incluida em `camadas_ativas[]`.
- Dados de contexto organizacional e momento de carreira disponiveis.

## Sequencia

### Passo 1: Executar RIASEC (Holland Codes)
- **Agente:** riasec-analyst
- **Acao:** Avalia os 6 tipos de interesse vocacional de Holland:
  - **Realista (R):** Pratico, mecanico, atletico, hands-on.
  - **Investigativo (I):** Analitico, intelectual, cientifico, explorador.
  - **Artistico (A):** Criativo, expressivo, original, intuitivo.
  - **Social (S):** Cooperativo, prestativo, educador, curador.
  - **Empreendedor (E):** Competitivo, lider, persuasivo, ambicioso.
  - **Convencional (C):** Organizado, detalhista, sistematico, eficiente.
- **Decisao:** Gerar codigo de 3 letras (ex: EIS). Se dois tipos empatinam, considerar ambas combinacoes.
- **Output:** `riasec_codigo_3`, `riasec_scores_6{}`, `ambiente_ideal_derivado`, `carreiras_alinhadas[]`.

### Passo 2: Executar Strong Interest Inventory
- **Agente:** career-fit-analyst
- **Acao:** Aprofunda alem do RIASEC com escalas adicionais:
  - **Temas Ocupacionais Gerais (GOT):** Expande os 6 tipos Holland.
  - **Escalas de Interesse Basico (BIS):** 30 areas especificas de interesse.
  - **Escalas Ocupacionais (OS):** Semelhanca com profissionais satisfeitos em diversas carreiras.
  - **Escalas de Estilo Pessoal (PSS):** Preferencias de trabalho, aprendizado, lideranca, tomada de risco, trabalho em equipe.
- **Decisao:** Se profundidade = "Rapido", usar apenas GOT. Se "Padrao" ou "Profundo", incluir BIS e PSS.
- **Output:** `strong_got{}`, `strong_bis[]` (se aplicavel), `strong_pss{}` (se aplicavel), `ocupacoes_alinhadas[]`.

### Passo 3: Executar Kolbe A Index
- **Agente:** kolbe-analyst
- **Acao:** Avalia os 4 modos de acao instintiva (como a pessoa age naturalmente sob pressao):
  - **Fact Finder:** Nível de detalhe buscado antes de agir (simplificar vs especificar).
  - **Follow Thru:** Nível de sistematizacao (adaptar vs sistematizar).
  - **Quick Start:** Nível de tolerancia ao risco e mudanca (estabilizar vs improvisar).
  - **Implementor:** Nível de uso de recursos tangíveis (imaginar vs construir).
- **Decisao:** Cada modo gera score de 1-10. Zonas: Preventivo (1-3), Acomodativo (4-6), Iniciativo (7-10). Identificar modo dominante (onde inicia a acao).
- **Output:** `kolbe_4_modos{}`, `modo_dominante`, `zona_por_modo{}`, `estilo_acao_resumo`.

### Passo 4: Integracao Carreira e Acao
- **Agente:** career-fit-analyst
- **Acao:** Cruza RIASEC + Strong + Kolbe para gerar visao integrada:
  - Alinhamento entre interesses (RIASEC/Strong) e modo de acao (Kolbe).
  - Ambientes de trabalho ideais considerando todos os instrumentos.
  - Carreiras e funcoes com maior probabilidade de satisfacao E desempenho.
  - Cruzamento com forcas (Clifton/VIA) e motivacao (Eneagrama/Reiss).
  - Gaps identificados: interesses fortes mas sem modo de acao compativel (ou vice-versa).
- **Output:** `mapa_carreira_acao{}`, `ambientes_ideais[]`, `funcoes_recomendadas[]`, `gaps_interesse_acao[]`, `confianca_camada_carreira`.

### Passo 5: Validacao com Contexto Real
- **Agente:** career-fit-analyst
- **Acao:** Compara o mapa gerado com a situacao atual do respondente:
  - Posicao atual e alinhada com o perfil mapeado?
  - Se desalinhada, qual e o grau e as implicacoes?
  - Oportunidades de ajuste dentro do contexto atual.
  - Movimentos de carreira de curto, medio e longo prazo sugeridos.
- **Decisao:** Se alinhamento atual > 70%, focar em otimizacao. Se < 40%, sinalizar necessidade de transicao.
- **Output:** `alinhamento_atual_score`, `recomendacoes_carreira[]`, `horizonte_temporal{}`.

## Quality Gates (checkpoints)

- [ ] RIASEC com codigo de 3 letras e scores para os 6 tipos.
- [ ] Strong com pelo menos GOT completo.
- [ ] Kolbe com scores para os 4 modos de acao.
- [ ] Integracao carreira-acao realizada com cruzamento de camadas anteriores.
- [ ] Validacao com contexto real do respondente.
- [ ] Confianca da camada >= 60%.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `riasec_codigo_3` + scores | JSON | Synthesis, report-writer |
| `strong_*` | JSON | Synthesis, career-guidance |
| `kolbe_4_modos{}` | JSON | Synthesis, development-planner |
| `mapa_carreira_acao{}` | JSON | Synthesis, report-writer |
| `funcoes_recomendadas[]` | Array | Career-guidance, hiring |
| `alinhamento_atual_score` | Float | Report-writer |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| RIASEC gera perfil plano (todos scores similares) | Usar perguntas de forced-choice para diferenciar. Pode indicar interesses genuinamente amplos. |
| Kolbe e DISC divergem sobre estilo de acao | Normal: Kolbe mede instinto conativo, DISC mede comportamento. Documentar como complementar. |
| Respondente insatisfeito com carreiras sugeridas | Explorar se insatisfacao e com as sugestoes ou com a realidade do desalinhamento. |
| Contexto atual nao se encaixa em nenhuma categoria | Career-fit-analyst cria categoria ad-hoc e documenta para calibracao futura. |

## Proximo Workflow

`08-contradiction-audit-flow.md` (OBRIGATORIO)
