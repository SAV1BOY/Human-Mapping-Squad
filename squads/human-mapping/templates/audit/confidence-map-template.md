---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [audit-agent, synthesis-agent, coordinator-agent]
---
# Confidence Map — Fillable Template

> Instrucoes: Consolide os niveis de confianca de cada layer do assessment. Classificacao e formula seguem `frameworks/confidence-scoring-model.md`. Este mapa determina a credibilidade geral e a decisao GO/NO-GO.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico | HMS-YYYY-MMDD-NNN | _______________ |
| Profundidade | Nivel executado | Escolha: /fast / /start / /deep | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |

---

## Escala de Classificacao (Referencia: `frameworks/confidence-scoring-model.md`)

| Score | Classificacao | Significado | Uso no Report |
|---|---|---|---|
| 0.00-0.29 | Insuficiente | Dados muito limitados; conclusoes nao confiaveis | NAO usar para decisoes; sinalizar como lacuna |
| 0.30-0.49 | Baixa | Dados parciais; conclusoes tentativas | Usar com ressalva explicita; recomendar dados adicionais |
| 0.50-0.69 | Moderada | Dados adequados; conclusoes razoaveis | Usar com nota de cautela em areas especificas |
| 0.70-0.84 | Alta | Dados solidos; boa convergencia entre fontes | Usar com confianca para recomendacoes |
| 0.85-1.00 | Muito Alta | Dados abundantes e convergentes | Usar com alta confianca para decisoes |

---

## Fatores de Avaliacao por Layer

> Cada layer e avaliada em 4 fatores. O score final da layer e a media dos 4 fatores.

| Fator | Definicao | Como Pontuar |
|---|---|---|
| **Qualidade dos dados** | Confiabilidade dos instrumentos e qualidade das respostas | 1.0 = instrumento validado + respostas consistentes; 0.5 = instrumento razoavel ou respostas com flags; 0.0 = dados questionaveis |
| **Convergencia** | Concordancia entre frameworks diferentes na mesma layer | 1.0 = 3+ frameworks convergem; 0.7 = 2 frameworks convergem; 0.4 = resultados mistos; 0.0 = frameworks divergem |
| **Consistencia** | Ausencia de contradicoes internas e com outras layers | 1.0 = sem contradicoes; 0.7 = contradicoes S1 apenas; 0.4 = contradicoes S2; 0.0 = contradicoes S3/S4 |
| **Completude** | Cobertura dos construtos relevantes da layer | 1.0 = todos construtos cobertos; 0.7 = maioria coberta; 0.4 = cobertura parcial; 0.0 = lacunas criticas |

---

## Confidence por Layer

### Traits (Tracos de Personalidade) — LAYER OBRIGATORIA

| Fator | Definicao | Score (0.0-1.0) | Justificativa (1 frase) |
|---|---|---|---|
| Qualidade dos dados | Instrumentos utilizados e qualidade das respostas | ___ | _______________ |
| Convergencia | Concordancia entre frameworks de tracos | ___ | _______________ |
| Consistencia | Ausencia de contradicoes com outras layers | ___ | _______________ |
| Completude | Cobertura dos 5 fatores + facetas relevantes | ___ | _______________ |
| **Score da layer** | **Media dos 4 fatores** | **___/1.0** | |
| **Classificacao** | Per escala acima | **___** | |

### Types/Styles (Tipologias e Estilos) — LAYER OBRIGATORIA

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |
| **Classificacao** | **___** | |

### Motivation (Motivacao) — LAYER OBRIGATORIA

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |
| **Classificacao** | **___** | |

### Strengths (Forcas) — LAYER OBRIGATORIA

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |
| **Classificacao** | **___** | |

### Team Role — CONDICIONAL (obrigatoria para /deep)

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |

### Career Fit — CONDICIONAL (obrigatoria para /deep)

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |

### Mode of Action — CONDICIONAL (obrigatoria para /deep)

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |

### Conflict/Stress — CONDICIONAL (obrigatoria para /deep)

| Fator | Score (0.0-1.0) | Justificativa |
|---|---|---|
| Qualidade dos dados | ___ | _______________ |
| Convergencia | ___ | _______________ |
| Consistencia | ___ | _______________ |
| Completude | ___ | _______________ |
| **Score da layer** | **___/1.0** | |

---

## Tabela Resumo

| Layer | Score | Classificacao | Obrigatoria? | Status |
|---|---|---|---|---|
| Traits | ___/1.0 | _______________ | Sim | Verde/Amarelo/Vermelho |
| Types/Styles | ___/1.0 | _______________ | Sim | Verde/Amarelo/Vermelho |
| Motivation | ___/1.0 | _______________ | Sim | Verde/Amarelo/Vermelho |
| Strengths | ___/1.0 | _______________ | Sim | Verde/Amarelo/Vermelho |
| Team Role | ___/1.0 | _______________ | /deep only | Verde/Amarelo/Vermelho |
| Career Fit | ___/1.0 | _______________ | /deep only | Verde/Amarelo/Vermelho |
| Mode of Action | ___/1.0 | _______________ | /deep only | Verde/Amarelo/Vermelho |
| Conflict/Stress | ___/1.0 | _______________ | /deep only | Verde/Amarelo/Vermelho |

**Status:** Verde >= 0.70 | Amarelo 0.50-0.69 | Vermelho < 0.50

---

## Overall Assessment Confidence

**FORMULA (per `frameworks/confidence-scoring-model.md`):**

```
Overall = (Traits x 2 + Types x 2 + Motivation x 1.5 + Strengths x 1.5 + TeamRole x 1 + CareerFit x 1 + ModeAction x 1 + Conflict x 1) / Soma dos pesos aplicaveis
```

> Para /fast e /start, usar apenas layers aplicaveis. Pesos das layers nao avaliadas sao removidos do denominador.

| Metrica | Formato | Valor |
|---|---|---|
| Score geral | Decimal 0.00-1.00 (resultado da formula) | ___/1.0 |
| Classificacao | Per escala (Insuficiente a Muito Alta) | _______________ |
| Contradicoes pendentes | Numero de contradicoes S3/S4 Abertas | ___ |
| Quality flags ativas | Flags do contradiction map ou outros audit docs | ___ |

---

## Decisao GO / NO-GO / CONDITIONAL

**REGRAS DE DECISAO:**

| Decisao | Criterio | Acao |
|---|---|---|
| **GO** | Todas as layers obrigatorias >= 0.50 E nenhuma contradicao S4 aberta | Prosseguir com report final |
| **NO-GO** | Qualquer layer obrigatoria < 0.50 OU contradicao S4 aberta | Suspender report; coletar dados adicionais ou retestagem |
| **CONDITIONAL** | Layers nao-obrigatorias abaixo de 0.50 mas obrigatorias OK | Prosseguir com ressalvas nas layers afetadas |

**DECISAO PARA ESTE ASSESSMENT:** [ GO / NO-GO / CONDITIONAL ]
**JUSTIFICATIVA:** _______________

---

## Recomendacoes Baseadas na Confianca

| Categoria | Definicao | Layers |
|---|---|---|
| Confianca suficiente para decisoes | Layers com score >= 0.70 | _______________ |
| Requerem cautela | Layers com score 0.50-0.69 | _______________ |
| Requerem dados adicionais | Layers com score < 0.50 | _______________ |

**Proximos passos recomendados:** _______________

---

## EXEMPLO PREENCHIDO

**Respondente:** Marina Costa Silva | **Session ID:** HMS-2026-0315-042 | **/deep** | **2026-03-15**

| Layer | Qualidade | Convergencia | Consistencia | Completude | **Score** | **Classificacao** |
|---|---|---|---|---|---|---|
| Traits | 0.90 | 0.85 | 0.70 | 0.95 | **0.85** | Muito Alta |
| Types/Styles | 0.80 | 0.65 | 0.60 | 0.80 | **0.71** | Alta |
| Motivation | 0.70 | 0.40 | 0.80 | 0.50 | **0.60** | Moderada |
| Strengths | 0.85 | 0.75 | 0.80 | 0.80 | **0.80** | Alta |
| Team Role | 0.75 | 0.60 | 0.80 | 0.70 | **0.71** | Alta |
| Career Fit | 0.60 | 0.50 | 0.70 | 0.50 | **0.58** | Moderada |
| Mode of Action | 0.80 | 0.70 | 0.80 | 0.75 | **0.76** | Alta |
| Conflict/Stress | 0.65 | 0.50 | 0.70 | 0.60 | **0.61** | Moderada |

**Overall:** (0.85x2 + 0.71x2 + 0.60x1.5 + 0.80x1.5 + 0.71x1 + 0.58x1 + 0.76x1 + 0.61x1) / (2+2+1.5+1.5+1+1+1+1) = 8.88 / 11 = **0.73/1.0 — Alta**

**Decisao:** GO — Todas as layers obrigatorias >= 0.50, nenhuma S4 aberta.
**Cautela:** Motivation (0.60) e Career Fit (0.58) em Moderada; incluir ressalvas no report.
