---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [report-agent, synthesis-agent]
---
# Deep Persona Report — Fillable Template

> Instrucoes: Report completo e detalhado do assessment. Cada secao tem definicao, formato e fontes. Recomendado para profundidade /deep. Total esperado: 3000-5000 palavras.

---

## Informacoes do Assessment

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Respondente | Nome completo | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico | HMS-YYYY-MMDD-NNN | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |
| Assessor | Agente ou pessoa responsavel | ID do agente ou nome | _______________ |
| Profundidade | Nivel executado | /fast / /start / /deep | _______________ |
| Instrumentos | Todos os frameworks aplicados | Lista completa separada por virgula | _______________ |
| Confidence geral | Score agregado | Decimal 0.00-1.00 | ___/1.0 |

---

## 1. Executive Summary

**DEFINICAO:** Resumo autonomo que captura a essencia do perfil completo.
**FORMATO:** MAX 300 palavras. Deve conter obrigatoriamente:
1. Top 3 findings mais relevantes para o contexto do assessment
2. Confidence geral e eventuais ressalvas criticas
3. Recomendacao principal (1 frase)

**ESTRUTURA:**
> [Paragrafo 1 — 2-3 frases]: Quem e esta pessoa em essencia (tracos + tipo dominante).
> [Paragrafo 2 — 2-3 frases]: Como age e o que a move (comportamento + motivacao).
> [Paragrafo 3 — 2-3 frases]: Principais forcas, riscos e recomendacao.
> [Linha final]: "Confidence geral: X.XX/1.0 — [Classificacao]. [Ressalva se houver]."

[Inserir Executive Summary aqui — MAX 300 palavras]

---

## 2. Trait Profile (Perfil de Tracos)

**FONTE:** `templates/layers/trait-map-template.md`
**FORMATO POR SUBSECAO:**

### Big Five Overview

| Dimensao | Score (percentil) | Confidence | Descricao comportamental (2-3 frases) |
|---|---|---|---|
| Openness | ___/100 | ___/1.0 | _______________ |
| Conscientiousness | ___/100 | ___/1.0 | _______________ |
| Extraversion | ___/100 | ___/1.0 | _______________ |
| Agreeableness | ___/100 | ___/1.0 | _______________ |
| Neuroticism | ___/100 | ___/1.0 | _______________ |

### Facetas Destaque

**REGRA:** Incluir apenas facetas que desviam >15 percentis do fator (per trait-map-template). Formato: tabela com faceta, score, desvio, interpretacao.

| Faceta | Fator | Score | Desvio | Interpretacao |
|---|---|---|---|---|
| | | | | |

### HEXACO Additions

**REGRA CONDICIONAL:** Incluir somente se HEXACO foi aplicado. Caso contrario, escrever "HEXACO nao aplicado nesta avaliacao."

### Implicacoes Comportamentais

**FORMATO:** Narrativa de 150-250 palavras integrando os tracos em um retrato comportamental coerente. Nao repetir scores — focar em padroes e interacoes entre tracos.

[Inserir narrativa aqui]

---

## 3. Type/Style Profile (Perfil Tipologico)

**FONTE:** Type/Style Map template

### Tipologia Primaria
**FORMATO:** Nome do tipo + framework + descricao de 2-3 frases.

### Cross-Framework Summary
**FORMATO:** Tabela mostrando convergencia/divergencia entre frameworks tipologicos.

| Framework | Tipo/Resultado | Convergencia com outros? |
|---|---|---|
| MBTI | _______________ | _______________ |
| DISC | _______________ | _______________ |
| Enneagrama | _______________ | _______________ |

### Estilo de Comunicacao
**FORMATO:** 3-5 bullet points com comportamentos observaveis.

### Estilo de Trabalho
**FORMATO:** 3-5 bullet points com comportamentos observaveis.

---

## 4. Motivation Profile (Perfil Motivacional)

**FONTE:** `templates/layers/motivation-map-template.md`

### Motivacoes Centrais
**FORMATO:** Top 3 motivacoes rankeadas com framework de origem e evidencia.

### Valores Fundamentais
**FORMATO:** Top 3-5 valores com definicao operacional (como se manifesta).

### O que Energiza vs O que Drena
**FORMATO:** Tabela de 2 colunas, 3-5 itens cada.

| Energiza | Drena |
|---|---|
| | |

### Implicacoes para Engajamento
**FORMATO:** 2-3 frases com recomendacoes actionaveis para gestores.

---

## 5. Strength Profile (Perfil de Forcas)

**FONTE:** Strength Map template

### Top Strengths
**FORMATO:** Top 5 forcas com framework de origem. Incluir rank e score quando disponivel.

### Power Pairs
**DEFINICAO:** Combinacoes de 2 forcas que juntas criam capacidade unica.
**FORMATO:** 1-2 power pairs com descricao de 1 frase cada.

### Forcas Subutilizadas
**DEFINICAO:** Forcas com alto score mas baixa frequencia de uso no contexto atual.
**FORMATO:** 1-2 forcas com sugestao de aplicacao.

### Sombra das Forcas
**DEFINICAO:** Como cada top strength pode se tornar risco quando em excesso.
**FORMATO:** Tabela: Forca -> Sombra -> Trigger.

---

## 6-9. Layers Adicionais

**REGRA CONDICIONAL:** Secoes 6-9 sao obrigatorias para /deep, opcionais para /start, omitidas em /fast.

### 6. Team Role
**FONTE:** Team Role Map. **FORMATO:** Role primario + contribuicao + dinamicas. 150-200 palavras.

### 7. Career Fit
**FONTE:** Career Fit analysis. **FORMATO:** Interesses + ambientes + recomendacoes. 150-200 palavras.

### 8. Mode of Action
**FONTE:** Mode of Action map. **FORMATO:** MO natural + condicoes otimas + riscos. 150-200 palavras.

### 9. Conflict & Stress
**FONTE:** Conflict Sequence analysis. **FORMATO:** Comportamento sob pressao + triggers + recovery. 150-200 palavras.

---

## 10. Contradicoes Detectadas

**FONTE OBRIGATORIA:** `templates/audit/contradiction-map-template.md` — deve estar preenchido ANTES desta secao.
**FORMATO:**

### Contradicoes Principais
**Incluir:** Tabela resumo do contradiction map (ID, frameworks, severidade, status).

| ID | Frameworks | Severidade | Status |
|---|---|---|---|
| | | | |

### Explicacoes
**FORMATO:** Para cada contradicao S2+, incluir paragrafo de 2-3 frases com a explicacao documentada.

### Impacto na Interpretacao
**FORMATO:** 1-2 frases por contradicao explicando como ela afeta as conclusoes do report.

---

## 11. Reconciliacao

### Narrativa Integrada
**DEFINICAO:** Como o perfil faz sentido como um todo, INCLUINDO as contradicoes resolvidas.
**FORMATO:** 150-300 palavras. Deve tecer tracos, tipos, motivacoes e forcas em uma narrativa coerente.

### Areas de Ambiguidade Restante
**DEFINICAO:** Aspectos do perfil que permanecem incertos apos reconciliacao.
**FORMATO:** Lista com bullet points. Se nenhuma, escrever "Nenhuma ambiguidade significativa restante."

---

## 12. Confidence Map

**FONTE OBRIGATORIA:** `templates/audit/confidence-map-template.md` — deve estar preenchido ANTES desta secao.

| Layer | Confidence | Status | Nota |
|---|---|---|---|
| Traits | ___/1.0 | Verde/Amarelo/Vermelho | |
| Types/Styles | ___/1.0 | Verde/Amarelo/Vermelho | |
| Motivation | ___/1.0 | Verde/Amarelo/Vermelho | |
| Strengths | ___/1.0 | Verde/Amarelo/Vermelho | |
| Team Role | ___/1.0 | Verde/Amarelo/Vermelho | |
| Career Fit | ___/1.0 | Verde/Amarelo/Vermelho | |
| Mode of Action | ___/1.0 | Verde/Amarelo/Vermelho | |
| Conflict/Stress | ___/1.0 | Verde/Amarelo/Vermelho | |
| **Overall** | **___/1.0** | | |

**Classificacao:** Verde >= 0.70 | Amarelo 0.50-0.69 | Vermelho < 0.50

---

## 13. Recomendacoes de Desenvolvimento

**FONTE OBRIGATORIA:** Deve linkar para `templates/reports/development-plan-template.md` para detalhamento.
**FORMATO:** 3 prioridades, cada uma com:

| Campo | Formato |
|---|---|
| Area | Nome da area de desenvolvimento |
| Base | Qual finding do assessment suporta esta recomendacao |
| Acao sugerida | 1-2 frases com acao concreta |
| Prazo | Curto (1-3 meses) / Medio (3-6 meses) / Longo (6-12 meses) |

### Prioridade 1:
| Campo | Valor |
|---|---|
| Area | _______________ |
| Base | _______________ |
| Acao sugerida | _______________ |
| Prazo | _______________ |

### Prioridade 2:
| Campo | Valor |
|---|---|
| Area | _______________ |
| Base | _______________ |
| Acao sugerida | _______________ |
| Prazo | _______________ |

### Prioridade 3:
| Campo | Valor |
|---|---|
| Area | _______________ |
| Base | _______________ |
| Acao sugerida | _______________ |
| Prazo | _______________ |

> Para plano de desenvolvimento detalhado, ver: `templates/reports/development-plan-template.md`

---

## Appendix

### A. Raw Data References
**DEFINICAO:** Lista de todos os instrumentos aplicados com referencia aos dados brutos.
**FORMATO:** Tabela com framework, versao, data de aplicacao, localizacao dos dados.

| Framework | Versao | Data | Referencia |
|---|---|---|---|
| | | | |

### B. Methodology Notes
**DEFINICAO:** Descricao da metodologia de integracao multi-framework.
**FORMATO:** 3-5 frases descrevendo como os dados foram coletados, normalizados e integrados.

### C. Disclaimer
**TEXTO PADRAO (usar como esta):**
> Este report e baseado em instrumentos psicometricos e frameworks de personalidade que fornecem aproximacoes probabilisticas, nao diagnósticos definitivos. Resultados devem ser interpretados em conjunto com observacoes contextuais, entrevistas e outros dados relevantes. Nenhuma decisao de alto impacto (contratacao, demissao, promocao) deve ser baseada exclusivamente neste report. Validade estimada: 12-18 meses, dependendo de mudancas significativas de vida ou carreira.

---

**Assessor:** _______________
**Revisado por:** _______________
**Data do report:** YYYY-MM-DD
**Versao do report:** 1.0
