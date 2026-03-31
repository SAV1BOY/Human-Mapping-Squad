---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 09-synthesis-and-integration-flow"
agents: [report-writer]
quality_gates: [executive-clarity-checklist, one-page-limit-checklist]
---

# Workflow: Geracao de Relatorio Executivo

## Trigger

Recebe handoff do `09-synthesis-and-integration-flow.md` com `mapa_unificado{}` e `narrativa_central{}`.

## Pre-condicoes

- Mapa unificado finalizado e validado pelo chief.
- Narrativa central com 7 dimensoes disponivel.
- Objetivo do mapeamento claro para direcionar o foco do relatorio.

## Sequencia

### Passo 1: Selecionar Conteudo Prioritario
- **Agente:** report-writer
- **Acao:** Filtra o mapa unificado para extrair apenas informacoes de alto impacto:
  - Top 3 tracos mais definidores.
  - Tipo/estilo dominante (1 framework principal).
  - Motor motivacional principal.
  - Top 3 forcas de genialidade.
  - Principal ponto cego ou risco.
  - Recomendacao central (1 frase).
- **Decisao:** Priorizar conforme objetivo: se lideranca, enfatizar estilo e motivacao; se contratacao, enfatizar fit e riscos.
- **Output:** `conteudo_executivo_selecionado{}`.

### Passo 2: Redigir Snapshot Executivo
- **Agente:** report-writer
- **Acao:** Redige relatorio de 1 pagina (maximo 400 palavras) com estrutura:
  - **Titulo:** Nome do respondente + "Perfil Comportamental - Visao Executiva".
  - **Resumo em 1 paragrafo:** Quem e essa pessoa em essencia (3-4 frases).
  - **Destaques Positivos:** 3-5 bullet points com forcas e diferenciais.
  - **Pontos de Atencao:** 2-3 bullet points com riscos e pontos cegos.
  - **Recomendacao Central:** 1-2 frases direcionadas ao objetivo.
  - **Indicador de Confianca:** Barra visual ou percentual da confianca geral.
  - **Rodape:** Nota sobre profundidade do assessment e sugestao de ler relatorio completo.
- **Decisao:** Se confianca geral < 60%, incluir aviso explicito no topo.
- **Output:** `relatorio_executivo_rascunho`.

### Passo 3: Aplicar Linguagem Executiva
- **Agente:** report-writer
- **Acao:** Revisa o rascunho garantindo:
  - Linguagem acessivel para qualquer stakeholder (sem jargoes de psicometria).
  - Tom profissional, respeitoso e construtivo.
  - Frases curtas e diretas.
  - Nenhuma rotulacao negativa (ex: "neurotico" vira "sensivel a estresse").
  - Equilibrio entre pontos positivos e de atencao (proporcao 2:1 minimo).
  - Termos tecnicos substituidos por equivalentes cotidianos.
- **Output:** `relatorio_executivo_revisado`.

### Passo 4: Formatar para Entrega
- **Agente:** report-writer
- **Acao:** Aplica formatacao final:
  - Cabecalho com logo/identidade do squad.
  - Data do assessment e session_id.
  - Layout limpo com hierarquia visual clara.
  - Graficos simplificados (se aplicavel): radar chart com 5 dimensoes principais.
  - Versao para impressao e versao digital.
- **Output:** `relatorio_executivo_final`.

### Passo 5: Validacao de Qualidade
- **Agente:** report-writer
- **Acao:** Auto-revisao contra checklist:
  - Cabe em 1 pagina? (se nao, cortar).
  - Responde ao objetivo do usuario em 10 segundos de leitura?
  - Alguma afirmacao sem respaldo nos dados?
  - Tom e construtivo e acionavel?
  - Confianca esta representada honestamente?
- **Decisao:** Se falhar em qualquer item, revisar antes de entregar.
- **Output:** `validacao_executivo_ok` (boolean), `relatorio_executivo_entregue`.

## Quality Gates (checkpoints)

- [ ] Relatorio cabe em 1 pagina (maximo 400 palavras).
- [ ] Linguagem acessivel sem jargoes tecnicos.
- [ ] Equilibrio positivos vs atencao (minimo 2:1).
- [ ] Recomendacao central alinhada ao objetivo.
- [ ] Indicador de confianca presente e honesto.
- [ ] Nenhuma afirmacao sem respaldo nos dados do mapa.
- [ ] Tom respeitoso e construtivo.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_executivo_final` | Markdown/PDF | Usuario, stakeholders |
| `conteudo_executivo_selecionado{}` | JSON | Arquivo da sessao |
| `validacao_executivo_ok` | Boolean | Log de qualidade |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Relatorio excede 1 pagina | Report-writer corta informacoes menos criticas. Referencia relatorio profundo para detalhes. |
| Linguagem ainda tecnica apos revisao | Aplicar regra: "Uma pessoa sem formacao em psicologia entenderia isso?" Se nao, reescrever. |
| Confianca muito baixa para relatorio util | Incluir disclaimer explicito e recomendar reassessment antes de tomar decisoes. |
| Objetivo nao claro o suficiente para recomendacao | Usar recomendacao generica de desenvolvimento e sugerir sessao de follow-up. |

## Proximo Workflow

- `11-deep-report-generation.md` (sempre executado em paralelo ou sequencia)
- Workflows especializados conforme objetivo (12-16)
