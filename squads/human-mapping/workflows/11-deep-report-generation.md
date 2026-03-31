---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 09-synthesis-and-integration-flow (paralelo ao 10)"
agents: [report-writer]
quality_gates: [evidence-coverage-checklist, confidence-transparency-checklist, depth-completeness-checklist]
---

# Workflow: Geracao de Relatorio Profundo

## Trigger

Recebe handoff do `09-synthesis-and-integration-flow.md`. Pode ser executado em paralelo com `10-executive-report-generation.md`.

## Pre-condicoes

- Mapa unificado finalizado com todas as camadas.
- Auditoria de contradicoes concluida com reconciliacoes.
- Mapa de confianca atualizado disponivel.

## Sequencia

### Passo 1: Estruturar Documento
- **Agente:** report-writer
- **Acao:** Define estrutura completa do relatorio profundo:
  1. Sumario Executivo (resumo do relatorio executivo).
  2. Contexto e Objetivo do Mapeamento.
  3. Metodologia e Instrumentos Utilizados.
  4. Camada 1: Tracos de Personalidade (detalhado).
  5. Camada 2: Tipos e Estilos (detalhado).
  6. Camada 3: Motivacao e Valores (detalhado).
  7. Camada 4: Forcas e Talentos (detalhado).
  8. Camada 5: Interesses e Modo de Acao (detalhado).
  9. Analise Integrada e Narrativa Central.
  10. Contradicoes e Reconciliacoes.
  11. Mapa de Confianca.
  12. Recomendacoes.
  13. Anexos e Referencias.
- **Output:** `estrutura_relatorio_profundo`.

### Passo 2: Redigir Cada Camada com Evidencia
- **Agente:** report-writer
- **Acao:** Para cada camada (secoes 4-8), escreve com a seguinte estrutura:
  - **Resumo da Camada:** 2-3 frases sobre o que foi encontrado.
  - **Resultados por Instrumento:** Dados especificos de cada framework utilizado.
  - **Evidencia:** Citacoes ou exemplos das respostas do respondente que sustentam os resultados.
  - **Convergencias:** Onde instrumentos da camada concordam.
  - **Divergencias:** Onde instrumentos da camada discordam e como foi reconciliado.
  - **Confianca da Camada:** Score numerico + justificativa textual.
  - **Implicacoes Praticas:** O que isso significa no dia a dia.
- **Decisao:** Se camada tem confianca < 50%, incluir box de alerta destacado.
- **Output:** `secoes_camadas[]` (5 secoes completas).

### Passo 3: Redigir Analise Integrada
- **Agente:** report-writer
- **Acao:** Escreve secao 9 (Analise Integrada) baseada na narrativa central:
  - Responde as 7 dimensoes da narrativa com profundidade.
  - Conecta camadas entre si mostrando como tracos influenciam tipos, tipos modulam motivacao, etc.
  - Apresenta o "retrato completo" da pessoa como narrativa coesa.
  - Inclui cenarios praticos: "Em uma reuniao de equipe, esta pessoa provavelmente..."
  - Destaca paradoxos genuinos que fazem parte da complexidade humana.
- **Output:** `secao_analise_integrada`.

### Passo 4: Documentar Contradicoes e Confianca
- **Agente:** report-writer
- **Acao:** Escreve secoes 10 e 11 com transparencia total:
  - **Contradicoes:** Lista cada contradicao encontrada, classificacao, causa investigada e reconciliacao aplicada.
  - **Confianca:** Mapa visual de confianca por camada e geral. Explicacao do que significa cada nivel.
  - Tom: honesto sem ser alarmista. Contradicoes sao normais e esperadas.
- **Output:** `secao_contradicoes`, `secao_confianca`.

### Passo 5: Redigir Recomendacoes
- **Agente:** report-writer
- **Acao:** Gera recomendacoes estratificadas:
  - **Imediatas (0-30 dias):** Acoes rapidas baseadas nos insights mais confiaveis.
  - **Curto prazo (1-3 meses):** Ajustes de comportamento ou ambiente.
  - **Medio prazo (3-12 meses):** Desenvolvimento de competencias ou transicoes.
  - **Longo prazo (1-3 anos):** Trajetoria de crescimento alinhada ao perfil.
  - Cada recomendacao vinculada a evidencia especifica do mapa.
- **Decisao:** Se objetivo e especifico (ex: contratacao), priorizar recomendacoes relevantes.
- **Output:** `secao_recomendacoes`.

### Passo 6: Compilar e Revisar
- **Agente:** report-writer
- **Acao:** Une todas as secoes no documento final. Revisao completa:
  - Consistencia de linguagem ao longo do documento.
  - Todas as afirmacoes tem evidencia referenciada.
  - Indices de confianca presentes em cada secao.
  - Nenhuma rotulacao pejorativa ou determinista.
  - Ressalvas da auditoria refletidas onde relevante.
  - Sumario executivo coerente com conteudo detalhado.
- **Output:** `relatorio_profundo_final`.

## Quality Gates (checkpoints)

- [ ] Todas as 5 camadas documentadas com resultados, evidencia e confianca.
- [ ] Analise integrada responde as 7 dimensoes da narrativa central.
- [ ] Contradicoes documentadas com transparencia.
- [ ] Mapa de confianca visual incluido.
- [ ] Recomendacoes estratificadas por horizonte temporal.
- [ ] Cada recomendacao vinculada a evidencia.
- [ ] Linguagem respeitosa, nao determinista, construtiva.
- [ ] Nenhuma afirmacao sem respaldo nos dados.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `relatorio_profundo_final` | Markdown/PDF | Usuario |
| `secoes_camadas[]` | JSON | Arquivo, reavaliacao futura |
| `secao_recomendacoes` | Texto | Development-planner |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Relatorio muito longo (>30 paginas) | Mover detalhes granulares para anexos. Corpo principal max 15-20 paginas. |
| Evidencia insuficiente para uma camada | Marcar secao como "dados limitados" e reduzir peso das recomendacoes derivadas. |
| Tom do relatorio percebido como negativo | Revisao adicional focada em reframing construtivo. Toda fraqueza e uma forca em contexto errado. |
| Inconsistencia entre executivo e profundo | Alinhar: executivo e subconjunto do profundo, nunca contraditorio. |

## Proximo Workflow

- Workflows especializados conforme objetivo (12-16).
- `17-cross-squad-handoff-flow.md` se necessario compartilhar com outros squads.
