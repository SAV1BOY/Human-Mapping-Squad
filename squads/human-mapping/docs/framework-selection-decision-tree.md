# Arvore de Decisao para Selecao de Frameworks

## Principio

Nem todo assessment precisa de todos os frameworks. O contexto determina quais sao obrigatorios, recomendados ou opcionais. Usar frameworks demais sem necessidade aumenta custo, tempo e confusao. Usar de menos gera analises rasas.

## Contextos Primarios

### 1. Selecao/Contratacao

**Objetivo**: Prever fit comportamental para o cargo e cultura.

| Prioridade | Framework | Justificativa |
|-----------|-----------|---------------|
| Obrigatorio | Big Five / HEXACO | Base cientifica solida para prever performance no trabalho. |
| Obrigatorio | DISC ou PI | Estilo comportamental no trabalho. Rapido e pratico. |
| Obrigatorio | Hogan HDS | Identificar riscos de derailment antes da contratacao. |
| Recomendado | Kolbe | Modo de acao — como a pessoa resolve problemas. |
| Recomendado | RIASEC | Alinhamento de interesses com a funcao. |
| Recomendado | Hogan MVPI | Alinhamento de valores com a cultura organizacional. |
| Opcional | Enneagrama | Profundidade motivacional. Mais util em cargos de lideranca. |
| Opcional | MBTI | Popular mas menor validade preditiva para selecao. |
| Evitar | VIA / CliftonStrengths | Mais adequados para desenvolvimento, nao selecao. |

**Regras**:
- Minimo 2 instrumentos obrigatorios + 1 recomendado.
- Sempre incluir HDS para cargos de lideranca.
- Entrevista estruturada comportamental e complemento obrigatorio (nao substituida por instrumentos).

### 2. Desenvolvimento Individual / Coaching

**Objetivo**: Autoconhecimento profundo e plano de crescimento.

| Prioridade | Framework | Justificativa |
|-----------|-----------|---------------|
| Obrigatorio | Big Five (nivel de facetas) | Mapa completo de personalidade. |
| Obrigatorio | Enneagrama | Motivacao profunda, padroes emocionais, caminho de crescimento. |
| Obrigatorio | SDI 2.0 | Comportamento sob pressao e forcas exageradas. |
| Recomendado | Hogan HDS | Lado sombrio — essencial para lideranca. |
| Recomendado | Kolbe | Modo de acao natural vs modo exigido pelo cargo. |
| Recomendado | CliftonStrengths ou VIA | Foco em forcas para desenvolvimento positivo. |
| Opcional | MBTI | Util para autoconhecimento, popular com clientes. |
| Opcional | DISC | Comunicacao e estilo interpessoal. |
| Opcional | Career Anchors (Schein) | Se ha questao de carreira envolvida. |

**Regras**:
- Minimo 3 instrumentos de profundidade diferente (traco + tipo + motivacao).
- Devolutiva obrigatoria — instrumentos sem conversa sao inuteis.
- Plano de acao com no maximo 3 focos de desenvolvimento.

### 3. Desenvolvimento de Time

**Objetivo**: Melhorar dinamica, comunicacao e complementaridade do time.

| Prioridade | Framework | Justificativa |
|-----------|-----------|---------------|
| Obrigatorio | DISC ou Insights Discovery | Linguagem de time simples e visual. |
| Obrigatorio | Belbin | Papeis de equipe — complementaridade explicita. |
| Recomendado | SDI 2.0 | Dinamica de conflito entre membros. |
| Recomendado | Kolbe | Modos de acao — quem inicia, quem sistematiza, quem pesquisa. |
| Opcional | Big Five | Para times que querem mais profundidade. |
| Opcional | Enneagrama | Para times com maturidade psicologica alta. |
| Evitar | Hogan HDS | Individual demais. Risco de exposicao publica do "lado sombrio". |

**Regras**:
- Maximo 2-3 instrumentos (mais do que isso confunde o time).
- Linguagem compartilhada e mais importante que profundidade.
- Nunca expor resultados individuais sem consentimento em contexto de grupo.

### 4. Orientacao de Carreira

**Objetivo**: Clareza sobre direcao profissional e adequacao.

| Prioridade | Framework | Justificativa |
|-----------|-----------|---------------|
| Obrigatorio | RIASEC / Strong Interest Inventory | Mapa de interesses vocacionais. |
| Obrigatorio | Career Anchors (Schein) | Motivacoes profissionais profundas e estaveis. |
| Obrigatorio | Big Five | Base de personalidade para prever satisfacao. |
| Recomendado | Kolbe | Como a pessoa naturalmente trabalha. |
| Recomendado | SDI 2.0 | Valores e comportamento sob pressao — relevante para ambiente de trabalho. |
| Opcional | Enneagrama | Padroes motivacionais que influenciam escolhas de carreira. |
| Opcional | DISC | Estilo de trabalho e comunicacao. |
| Evitar | Hogan HDS | Desnecessario em contexto de carreira (a menos que seja transicao de lideranca). |

**Regras**:
- RIASEC + Schein sao inegociaveis para orientacao de carreira.
- Contextualizar com realidade socioeconomica e cultural (ver `reference/careers/international-careers-cultural-fit.md`).
- Para flat profiles no RIASEC, complementar obrigatoriamente com Kolbe e Schein.

### 5. Assessment de Lideranca

**Objetivo**: Avaliar prontidao, riscos e potencial de lideranca.

| Prioridade | Framework | Justificativa |
|-----------|-----------|---------------|
| Obrigatorio | Hogan Triade (HPI + HDS + MVPI) | Bright side + Dark side + Valores. Padrao-ouro. |
| Obrigatorio | Big Five (nivel de facetas) | Base cientifica complementar. |
| Obrigatorio | DISC ou PI | Estilo de lideranca comportamental. |
| Recomendado | Enneagrama | Motivacao profunda e padroes sob estresse. |
| Recomendado | SDI 2.0 | Comportamento em conflito — critico para lideranca. |
| Recomendado | Kolbe | Modo de operacao — alinhamento com demandas do cargo. |
| Opcional | 360-degree feedback | Percepcao de stakeholders. |
| Opcional | CliftonStrengths | Foco em pontos fortes do lider. |

**Regras**:
- Hogan Triade e o minimo para assessment executivo serio.
- Sempre incluir avaliacao de risco (HDS) — nao apenas pontos fortes.
- Para C-level: adicionar simulacao/assessment center.

## Arvore de Decisao Rapida

```
Qual e o contexto?
├── Selecao/Contratacao
│   ├── Cargo de lideranca? → Hogan Triade + Big Five + DISC + entrevista
│   └── Cargo tecnico/operacional? → Big Five + DISC/PI + Kolbe + RIASEC
│
├── Desenvolvimento Individual
│   ├── Lider? → Hogan Triade + Enneagrama + SDI + CliftonStrengths
│   └── IC? → Big Five + Enneagrama + Kolbe + Career Anchors
│
├── Time
│   ├── Time novo? → DISC/Insights + Belbin + Kolbe
│   └── Time em conflito? → SDI + DISC + mediacao
│
├── Carreira
│   ├── Inicio de carreira? → RIASEC + Big Five + Schein
│   └── Transicao mid-career? → Schein + Big Five + SDI + RIASEC
│
└── Lideranca
    ├── Promocao interna? → Hogan Triade + Big Five + PI + 360
    └── Contratacao externa? → Hogan Triade + Big Five + DISC + assessment center
```

## Regras Gerais

1. **Nunca menos que 2 instrumentos**. Triangulacao e obrigatoria.
2. **Nunca mais que 5-6 instrumentos** (exceto assessment executivo complexo).
3. **Sempre incluir pelo menos 1 instrumento de risco/lado sombrio** para lideranca.
4. **Instrumentos sem devolutiva sao desperdicio**. Nao aplique o que nao vai explicar.
5. **Validade > popularidade**. Big Five > MBTI em qualquer contexto cientifico.
6. **Considerar proxy inference** quando instrumentos formais nao estao disponiveis (ver `docs/proxy-inference-mode-guide.md`).

## Referencia

- Ver `docs/framework-selection-guide.md` para orientacoes complementares.
- Ver `frameworks/confidence-scoring-model.md` para niveis de confianca por combinacao.
