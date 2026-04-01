---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [audit-agent, synthesis-agent, coordinator-agent]
related_files:
  - frameworks/confidence-scoring-model.md
  - frameworks/cross-framework-reconciliation.md
  - templates/audit/contradiction-map-template.md
  - templates/reports/executive-snapshot-template.md
  - templates/reports/deep-persona-report-template.md
---
# Confidence Map — Fillable Template

> Instrucoes: Consolide os niveis de confianca de cada layer do assessment. Este mapa determina a credibilidade geral do perfil e quais areas requerem cautela na interpretacao. Cada campo tem definicao, formato e regras de preenchimento.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico da sessao | HMS-YYYY-MMDD-NNN | _______________ |
| Profundidade | Nivel de profundidade executado | Escolha: /fast / /start / /deep | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |

---

## Classificacao de Confidence

> Referencia: `frameworks/confidence-scoring-model.md`

| Score Range | Classificacao | Cor | Significado | Acao |
|---|---|---|---|---|
| 0.90 - 1.00 | Muito Alta | Verde | Multiplos frameworks convergem fortemente | Proceder livremente; resultado altamente confiavel |
| 0.70 - 0.89 | Alta | Verde | Boa convergencia entre frameworks | Proceder livremente; resultado confiavel |
| 0.50 - 0.69 | Moderada | Amarelo | Convergencia parcial ou base limitada | Proceder COM ressalvas explicitas no report |
| 0.30 - 0.49 | Baixa | Vermelho | Pouca convergencia ou poucos dados | Layer considerada inconclusiva; ressalva obrigatoria |
| 0.00 - 0.29 | Muito Baixa | Vermelho | Dados insuficientes ou contraditorios | Layer NAO deve informar decisoes; recomendar retestagem |

**REGRAS DE DECISAO:**
- Score >= 0.70: Proceder livremente — resultado usado sem ressalvas
- Score 0.50-0.69: Proceder com caveats — incluir ressalva no report explicando limitacao
- Score < 0.50: Layer inconclusiva — NAO usar para recomendacoes; incluir ressalva forte; recomendar dados adicionais

---

## Confidence por Layer

> Para cada layer: preencher Score, Classificacao, Base de Evidencia, Flags e Acao. Se a layer nao foi avaliada (ex: profundidade /fast nao inclui Team Role), escrever "N/A — nao avaliada nesta profundidade."

### Traits (Tracos de Personalidade)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score desta layer | Decimal 0.00-1.00 (2 casas) | ___/1.0 |
| Classificacao | Categoria conforme tabela acima | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais frameworks compuseram esta layer | Inteiro + lista (ex: "3: NEO-PI-R, BFI-2, HEXACO-60") | _______________ |
| Convergencia | Grau de concordancia entre frameworks | Alta (>80% concordancia) / Media (50-80%) / Baixa (<50%) | _______________ |
| Flags | Problemas de qualidade identificados | Lista ou "Nenhuma". Ex: "1 framework proxy", "auto-relato apenas" | _______________ |
| Acao | Decisao baseada no score | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score atribuido | 1-2 frases. Max 40 words. Por que este score e nao outro? | _______________ |

### Types/Styles (Tipologias e Estilos)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Motivation (Motivacao)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Strengths (Forcas)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Team Role (Papel de Equipe)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Career Fit (Adequacao de Carreira)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Mode of Action (Modo de Acao)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

### Conflict/Stress (Conflito e Estresse)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score | Confidence score | Decimal 0.00-1.00 | ___/1.0 |
| Classificacao | Categoria | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Frameworks utilizados | Quantos e quais | Inteiro + lista | _______________ |
| Convergencia | Concordancia entre frameworks | Alta / Media / Baixa | _______________ |
| Flags | Problemas de qualidade | Lista ou "Nenhuma" | _______________ |
| Acao | Decisao | Proceder / Proceder com ressalva / Layer inconclusiva | _______________ |
| Justificativa | Explicacao do score | Max 40 words | _______________ |

---

## Tabela Resumo

| Layer | Score | Classificacao | Frameworks (qtd) | Convergencia | Flags | Acao |
|---|---|---|---|---|---|---|
| Traits | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Types/Styles | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Motivation | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Strengths | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Team Role | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Career Fit | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Mode of Action | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |
| Conflict/Stress | ___/1.0 | _______________ | ___ | Alta/Media/Baixa | _______________ | Proceder / Ressalva / Inconclusiva |

---

## Overall Assessment Confidence

**FORMULA:** Media ponderada das layers conforme `frameworks/confidence-scoring-model.md`:

```
Overall = (Traits x 2 + Types/Styles x 2 + Motivation x 1.5 + Strengths x 1.5 + Team Role x 1 + Career Fit x 1 + Mode of Action x 1 + Conflict/Stress x 1) / (2 + 2 + 1.5 + 1.5 + 1 + 1 + 1 + 1)
```

**NOTA:** Layers nao avaliadas (N/A) sao excluidas do calculo. Ajustar denominador de acordo.

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Score geral | Media ponderada calculada pela formula acima | Decimal 0.00-1.00 (2 casas) | ___/1.0 |
| Classificacao | Categoria conforme tabela de classificacao | Muito Baixa / Baixa / Moderada / Alta / Muito Alta | _______________ |
| Contradicoes pendentes | Quantidade de contradicoes S3+ nao resolvidas (do contradiction-map) | Inteiro | ___ |
| Reducao por contradicoes | Total de reducao no confidence por contradicoes | Decimal negativo (do contradiction-map) | -___ |
| Score ajustado | Score geral - Reducao por contradicoes | Decimal 0.00-1.00 | ___/1.0 |
| Quality flags ativas | Flags que afetam o assessment como um todo | Lista ou "Nenhuma" | _______________ |
| Veredito | Classificacao final para stakeholders | Alta confianca / Confianca adequada / Confianca limitada / Baixa confianca | _______________ |

**REGRAS DE VEREDITO:**
- Score ajustado >= 0.70 E nenhuma S4 aberta = "Alta confianca"
- Score ajustado 0.60-0.69 OU ate 1 S3 aberta = "Confianca adequada"
- Score ajustado 0.50-0.59 OU 2+ S3 abertas = "Confianca limitada"
- Score ajustado < 0.50 OU qualquer S4 aberta = "Baixa confianca"

---

## Recomendacoes Baseadas na Confianca

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Layers para decisao | Layers com score >= 0.70 que podem informar decisoes diretamente | Lista de layers | _______________ |
| Layers com cautela | Layers com score 0.50-0.69 que requerem ressalvas | Lista de layers + ressalva especifica | _______________ |
| Layers insuficientes | Layers com score < 0.50 que nao devem informar decisoes | Lista de layers + recomendacao de dados adicionais | _______________ |
| Proximos passos | Acoes recomendadas para melhorar confianca | Lista priorizada. Max 3 items, cada max 25 words. | _______________ |

---

## QUALITY CRITERIA

Um confidence map preenchido corretamente atende a TODOS os seguintes criterios:

1. **Completude:** Todas as layers avaliadas possuem Score, Classificacao, Frameworks, Flags e Acao preenchidos
2. **Classificacao correta:** Scores seguem a tabela de classificacao (Verde/Amarelo/Vermelho) sem excecoes
3. **Formula aplicada:** Overall calculado pela formula ponderada, nao por media simples
4. **Contradicoes integradas:** Reducao por contradicoes reflete totais do contradiction-map
5. **Acoes coerentes:** Acao por layer e consistente com score (>=0.70=Proceder, 0.50-0.69=Ressalva, <0.50=Inconclusiva)
6. **Veredito fundamentado:** Veredito final segue regras definidas, nao e subjetivo
7. **Recomendacoes acionaveis:** Proximos passos sao especificos e priorizados

---

## EXEMPLO PREENCHIDO — Tabela Resumo e Overall

**Tabela Resumo (exemplo):**

| Layer | Score | Classificacao | Frameworks (qtd) | Convergencia | Flags | Acao |
|---|---|---|---|---|---|---|
| Traits | 0.85/1.0 | Alta | 3 (NEO-PI-R, BFI-2, HEXACO-60) | Alta | Nenhuma | Proceder |
| Types/Styles | 0.75/1.0 | Alta | 2 (MBTI, DISC) | Media | MBTI auto-relato | Proceder |
| Motivation | 0.55/1.0 | Moderada | 1 (SDT questionnaire) | N/A (1 framework) | Framework unico | Proceder com ressalva |
| Strengths | 0.80/1.0 | Alta | 2 (VIA, CliftonStrengths) | Alta | Nenhuma | Proceder |
| Team Role | 0.70/1.0 | Alta | 1 (Belbin) | N/A (1 framework) | Framework unico | Proceder |
| Career Fit | 0.60/1.0 | Moderada | 1 (RIASEC) | N/A (1 framework) | Framework unico, proxy | Proceder com ressalva |
| Mode of Action | 0.72/1.0 | Alta | 1 (Kolbe A) | N/A (1 framework) | Nenhuma | Proceder |
| Conflict/Stress | 0.65/1.0 | Moderada | 1 (SDI) | N/A (1 framework) | Framework unico | Proceder com ressalva |

**Overall (exemplo):**

```
Overall = (0.85x2 + 0.75x2 + 0.55x1.5 + 0.80x1.5 + 0.70x1 + 0.60x1 + 0.72x1 + 0.65x1) / 11
        = (1.70 + 1.50 + 0.825 + 1.20 + 0.70 + 0.60 + 0.72 + 0.65) / 11
        = 7.895 / 11
        = 0.72
```

| Campo | Valor |
|---|---|
| Score geral | 0.72/1.0 |
| Classificacao | Alta |
| Contradicoes pendentes | 0 |
| Reducao por contradicoes | -0.00 |
| Score ajustado | 0.72/1.0 |
| Quality flags ativas | Motivation, Career Fit e Conflict/Stress baseados em framework unico |
| Veredito | Alta confianca |

**Recomendacoes (exemplo):**

| Campo | Valor |
|---|---|
| Layers para decisao | Traits, Types/Styles, Strengths, Team Role, Mode of Action |
| Layers com cautela | Motivation (framework unico SDT), Career Fit (proxy RIASEC), Conflict/Stress (framework unico SDI) |
| Layers insuficientes | Nenhuma |
| Proximos passos | 1. Aplicar segundo framework motivacional para elevar confidence. 2. Validar career fit com entrevista estruturada. |
