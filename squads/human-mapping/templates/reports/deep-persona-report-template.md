---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [report-agent, synthesis-agent]
related_files:
  - frameworks/confidence-scoring-model.md
  - frameworks/cross-framework-reconciliation.md
  - templates/layers/trait-map-template.md
  - templates/layers/motivation-map-template.md
  - templates/audit/contradiction-map-template.md
  - templates/audit/confidence-map-template.md
  - templates/reports/executive-snapshot-template.md
---
# Deep Persona Report — Fillable Template

> Instrucoes: Este e o report completo e detalhado do assessment. Preencha cada secao com base nos dados das layers individuais. Recomendado para profundidade /deep. Cada secao tem orientacao de conteudo, comprimento e criterios de qualidade.

---

## Informacoes do Assessment

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Respondente | Nome completo | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico | HMS-YYYY-MMDD-NNN | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |
| Assessor | Agente ou profissional responsavel | Texto | _______________ |
| Profundidade | Nivel executado | /fast / /start / /deep | _______________ |
| Instrumentos utilizados | Lista completa de todos os frameworks aplicados | Lista separada por virgula | _______________ |
| Confidence geral | Score agregado do confidence-map | Decimal 0.00-1.00 | ___/1.0 |

---

## 1. Executive Summary

**ORIENTACAO:**
- **Comprimento:** Max 200 words
- **Conteudo obrigatorio:** (1) Confidence geral do assessment, (2) Top 3 findings mais relevantes para o contexto, (3) Principal limitacao ou ressalva
- **O que incluir:** Sintese dos achados mais impactantes; visao holistica da pessoa; contexto do assessment
- **O que excluir:** Detalhes de scores individuais; jargao de frameworks; recomendacoes (vem na secao 13)
- **Tom:** Claro, direto, acessivel a qualquer stakeholder

> **FORMATO:** 1 paragrafo de contexto (2-3 frases) + 3 bullet points de findings + 1 frase de limitacao.

**Paragrafo de contexto:**
_______________

**Top 3 Findings:**
1. _______________
2. _______________
3. _______________

**Principal limitacao:**
_______________

---

## 2. Trait Profile (Perfil de Tracos)

**ORIENTACAO:**
- **Comprimento:** 300-500 words total para a secao
- **Fonte:** `templates/layers/trait-map-template.md`
- **Formato por subsecao:** Finding + Evidencia (score/percentil) + Confidence + Limitacoes

### Big Five Overview
**Comprimento:** 150-200 words. Apresentar as 5 dimensoes com scores, destacando as 2-3 mais extremas.

| Dimensao | Score (percentil) | Confidence | Classificacao |
|---|---|---|---|
| Openness | ___/100 | ___/1.0 | Muito Alta / Alta / Moderada / Baixa / Muito Baixa |
| Conscientiousness | ___/100 | ___/1.0 | Muito Alta / Alta / Moderada / Baixa / Muito Baixa |
| Extraversion | ___/100 | ___/1.0 | Muito Alta / Alta / Moderada / Baixa / Muito Baixa |
| Agreeableness | ___/100 | ___/1.0 | Muito Alta / Alta / Moderada / Baixa / Muito Baixa |
| Neuroticism | ___/100 | ___/1.0 | Muito Alta / Alta / Moderada / Baixa / Muito Baixa |

**Narrativa:** _______________

**Limitacoes desta layer:** _______________

### Facetas Destaque
**Comprimento:** 50-100 words. Listar apenas facetas extremas (top 3 HIGH + top 3 LOW across all dimensions).

| Faceta | Dimensao | Score | Destaque |
|---|---|---|---|
| _______________ | _______________ | ___ | HIGH/LOW |
| _______________ | _______________ | ___ | HIGH/LOW |
| _______________ | _______________ | ___ | HIGH/LOW |

**Implicacao das facetas extremas:** _______________

### HEXACO Additions
**Comprimento:** 50-100 words. Preencher SOMENTE se instrumento HEXACO aplicado.
**REGRA DE DECISAO:** Se nao disponivel, escrever: "HEXACO nao aplicado neste assessment."

_______________

### Implicacoes Comportamentais
**Comprimento:** 50-100 words. Sintese de como os tracos se manifestam em comportamentos observaveis.

_______________

---

## 3. Type/Style Profile (Perfil Tipologico)

**ORIENTACAO:**
- **Comprimento:** 250-400 words total
- **Formato:** Para cada tipo/estilo: resultado + interpretacao + convergencia com outros frameworks + limitacao

### Tipologia Primaria
**Comprimento:** 80-120 words. Resultado do MBTI ou equivalente + interpretacao.

| Campo | Valor |
|---|---|
| Tipo | _______________ |
| Framework | _______________ |
| Confidence | ___/1.0 |
| Descricao | _______________ (max 60 words) |

### Cross-Framework Summary
**Comprimento:** 80-120 words. Como os diferentes frameworks tipologicos convergem ou divergem.

| Framework | Resultado | Convergencia com tipologia primaria |
|---|---|---|
| _______________ | _______________ | Alta / Media / Baixa |
| _______________ | _______________ | Alta / Media / Baixa |

**Narrativa de convergencia:** _______________

### Estilo de Comunicacao
**Comprimento:** 50-80 words. Como a pessoa prefere comunicar-se, baseado em evidencia.

_______________

### Estilo de Trabalho
**Comprimento:** 50-80 words. Ritmo, estrutura e preferencias de trabalho.

_______________

---

## 4. Motivation Profile (Perfil Motivacional)

**ORIENTACAO:**
- **Comprimento:** 200-350 words total
- **Fonte:** `templates/layers/motivation-map-template.md`
- **Formato:** Finding + evidencia + confidence + limitacoes

### Motivacoes Centrais
**Comprimento:** 80-120 words. Top 2-3 motivacoes intrinsecas com evidencia.

| Motivacao | Framework | Evidencia | Confidence |
|---|---|---|---|
| _______________ | _______________ | _______________ | ___/1.0 |
| _______________ | _______________ | _______________ | ___/1.0 |

**Narrativa:** _______________

### Valores Fundamentais
**Comprimento:** 50-80 words. Top 2-3 valores com framework de origem.

_______________

### O que Energiza vs O que Drena
**Comprimento:** 50-80 words. Formato: 2-3 pares de energiza/drena.

| Energiza | Drena |
|---|---|
| _______________ | _______________ |
| _______________ | _______________ |

### Implicacoes para Engajamento
**Comprimento:** 50-80 words. O que o ambiente precisa oferecer para manter esta pessoa engajada.

_______________

---

## 5. Strength Profile (Perfil de Forcas)

**ORIENTACAO:**
- **Comprimento:** 200-300 words total
- **Formato:** Cada finding deve citar framework + score/rank + implicacao

### Top Strengths
**Comprimento:** 80-100 words. Top 3-5 forcas com framework de origem.

| Rank | Forca | Framework | Score/Posicao | Implicacao |
|---|---|---|---|---|
| 1 | _______________ | _______________ | _______________ | _______________ |
| 2 | _______________ | _______________ | _______________ | _______________ |
| 3 | _______________ | _______________ | _______________ | _______________ |

### Power Pairs
**Comprimento:** 40-60 words. Combinacoes de forcas que se potencializam.

_______________

### Forcas Subutilizadas
**Comprimento:** 40-60 words. Forcas presentes mas nao exploradas no contexto atual.

_______________

### Sombra das Forcas
**Comprimento:** 40-60 words. Como forcas podem se tornar riscos em excesso.

_______________

---

## 6. Team Role (Papel de Equipe)

**ORIENTACAO:**
- **Comprimento:** 150-250 words total
- **REGRA DE DECISAO:** Secao obrigatoria para /deep. Para /start, incluir apenas Roles Preferidos. Para /fast, omitir secao.

### Roles Preferidos
**Comprimento:** 50-80 words. Top 2-3 roles com framework (Belbin, Team Management Wheel, etc.).

| Role | Framework | Score | Descricao (max 15 words) |
|---|---|---|---|
| _______________ | _______________ | _______________ | _______________ |
| _______________ | _______________ | _______________ | _______________ |

### Contribuicao para Equipe
**Comprimento:** 40-60 words. O que esta pessoa agrega em um time.

_______________

### Dinamicas Interpessoais
**Comprimento:** 40-60 words. Como interage, potenciais de conflito, complementaridade.

_______________

---

## 7. Career Fit (Adequacao de Carreira)

**ORIENTACAO:**
- **Comprimento:** 150-250 words total
- **REGRA DE DECISAO:** Secao obrigatoria para /deep e contextos Profissional/Hiring/Lideranca. Omitir para contexto Pessoal se nao solicitado.

### Perfil de Interesses
**Comprimento:** 50-80 words. RIASEC ou equivalente com interpretacao.

_______________

### Best-Fit Environments
**Comprimento:** 50-80 words. Tipos de organizacao, cultura e funcao onde a pessoa prospera.

_______________

### Recomendacoes de Carreira
**Comprimento:** 50-80 words. 2-3 direcoes de carreira fundamentadas nos dados.
**REGRA:** Cada recomendacao deve citar ao menos 1 evidencia (trait, strength, interest, ou motivation).

_______________

---

## 8. Mode of Action (Modo de Acao)

**ORIENTACAO:**
- **Comprimento:** 150-250 words total
- **Fonte:** Kolbe, ou outros frameworks de acao

### MO Natural
**Comprimento:** 50-80 words. Modo de acao instintivo com scores.

_______________

### Melhores Condicoes de Trabalho
**Comprimento:** 40-60 words. Condicoes que alinham com o MO natural.

_______________

### Riscos de Burnout Conativo
**Comprimento:** 40-60 words. Condicoes que forcam contra o MO natural.

_______________

---

## 9. Conflict & Stress (Conflito e Estresse)

**ORIENTACAO:**
- **Comprimento:** 150-250 words total

### Comportamento Sob Pressao
**Comprimento:** 50-80 words. Como a pessoa reage quando estressada. Comportamentos observaveis.

_______________

### Triggers
**Comprimento:** 40-60 words. Situacoes que ativam estresse/conflito. Lista de 3-5 triggers.

1. _______________
2. _______________
3. _______________

### Estrategias de Recovery
**Comprimento:** 40-60 words. O que ajuda esta pessoa a se recuperar. Baseado em dados do assessment.

_______________

---

## 10. Contradicoes Detectadas

**ORIENTACAO:**
- **Comprimento:** 100-200 words total
- **Fonte:** `templates/audit/contradiction-map-template.md`
- **REGRA:** DEVE listar TODAS as contradicoes detectadas, mesmo as resolvidas. Mostrar resolucao e impacto.
- **O que incluir:** ID, frameworks envolvidos, severidade, status, impacto
- **O que excluir:** Detalhes completos da analise (referir ao contradiction-map para detalhes)

| ID | Frameworks | Severidade | Status | Impacto |
|---|---|---|---|---|
| _______________ | _______________ | S_ | _______________ | -___ |
| _______________ | _______________ | S_ | _______________ | -___ |

**Narrativa:** _______________

**REGRA DE DECISAO:** Se nenhuma contradicao detectada, escrever: "Nenhuma contradicao inter-framework detectada. Todos os frameworks convergem dentro dos limites esperados."

---

## 11. Reconciliacao

**ORIENTACAO:**
- **Comprimento:** 100-200 words total
- **O que incluir:** Como as contradicoes foram integradas na narrativa do perfil; decisoes tomadas
- **O que excluir:** Repeticao dos detalhes ja apresentados na secao 10

### Narrativa Integrada
**Comprimento:** 60-120 words. Como o perfil final reconcilia achados divergentes.

_______________

### Areas de Ambiguidade Restante
**Comprimento:** 40-80 words. O que permanece incerto e como isso afeta interpretacao.
**REGRA:** Se todas as contradicoes foram resolvidas, escrever: "Sem ambiguidades restantes significativas."

_______________

---

## 12. Confidence Map

**ORIENTACAO:**
- **Comprimento:** Tabela + 2-3 frases de narrativa (max 60 words)
- **Fonte:** `templates/audit/confidence-map-template.md`
- **Classificacao:** Verde >= 0.70 | Amarelo 0.50-0.69 | Vermelho < 0.50

| Layer | Confidence | Status | Flags |
|---|---|---|---|
| Traits | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Types/Styles | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Motivation | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Strengths | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Team Role | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Career Fit | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Mode of Action | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Conflict/Stress | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| **Overall** | **___/1.0** | **Verde/Amarelo/Vermelho** | _______________ |

**Narrativa:** _______________

---

## 13. Recomendacoes de Desenvolvimento

**ORIENTACAO:**
- **Comprimento:** 150-250 words total (50-80 words por prioridade)
- **REGRA:** Cada recomendacao DEVE rastrear ate evidencia especifica do assessment. Formato: Recomendacao + Evidencia + Acao sugerida.
- **Limite:** Max 3 prioridades. Se mais de 3 areas de desenvolvimento, priorizar por impacto.

### Prioridade 1:

| Campo | Valor |
|---|---|
| Area de desenvolvimento | _______________ |
| Evidencia que suporta | _______________ (citar layer + score + finding especifico) |
| Acao sugerida | _______________ (max 40 words, acionavel e mensuravel) |
| Urgencia | Alta / Media / Baixa |

### Prioridade 2:

| Campo | Valor |
|---|---|
| Area de desenvolvimento | _______________ |
| Evidencia que suporta | _______________ |
| Acao sugerida | _______________ |
| Urgencia | Alta / Media / Baixa |

### Prioridade 3:

| Campo | Valor |
|---|---|
| Area de desenvolvimento | _______________ |
| Evidencia que suporta | _______________ |
| Acao sugerida | _______________ |
| Urgencia | Alta / Media / Baixa |

---

## Section-by-Section Length Guide (Referencia Rapida)

| Secao | Min Words | Max Words | Obrigatoria? |
|---|---|---|---|
| 1. Executive Summary | 150 | 200 | Sim, sempre |
| 2. Trait Profile | 300 | 500 | Sim, sempre |
| 3. Type/Style Profile | 250 | 400 | Sim, sempre |
| 4. Motivation Profile | 200 | 350 | Sim, sempre |
| 5. Strength Profile | 200 | 300 | Sim, sempre |
| 6. Team Role | 150 | 250 | /deep e /start |
| 7. Career Fit | 150 | 250 | /deep + contexto profissional |
| 8. Mode of Action | 150 | 250 | /deep |
| 9. Conflict & Stress | 150 | 250 | /deep |
| 10. Contradicoes | 100 | 200 | Sim, sempre |
| 11. Reconciliacao | 100 | 200 | Sim, sempre |
| 12. Confidence Map | — | 60 (narrativa) | Sim, sempre |
| 13. Desenvolvimento | 150 | 250 | Sim, sempre |
| **TOTAL** | **~2050** | **~3450** | — |

---

**Assessor:** _______________
**Revisado por:** _______________
**Data do report:** YYYY-MM-DD

---

## QUALITY CRITERIA

Um deep persona report preenchido corretamente atende a TODOS os seguintes criterios:

1. **Completude:** Todas as secoes obrigatorias preenchidas; secoes condicionais preenchidas/omitidas corretamente
2. **Comprimento:** Cada secao respeita os limites min/max de words
3. **Rastreabilidade:** Todo finding cita framework + score + layer de origem
4. **Contradicoes completas:** Secao 10 lista TODAS as contradicoes, nao apenas as nao resolvidas
5. **Desenvolvimento rastreavel:** Cada recomendacao da secao 13 cita evidencia especifica
6. **Confidence integrada:** Tabela da secao 12 consistente com confidence-map; narrativa menciona limitacoes
7. **Executive summary autonomo:** Secao 1 e compreensivel isoladamente, sem referencia as demais
8. **Sem jargao nao explicado:** Todo termo tecnico de framework e contextualizado na primeira ocorrencia
