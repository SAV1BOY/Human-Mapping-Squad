# Guia de Pontuação de Confiança

## Visão Geral
Este guia define o sistema de pontuação de confiança utilizado pelo squad para
indicar o grau de certeza em cada afirmação, dimensão e perfil gerado. A
transparência sobre confiança é um princípio fundamental do squad.

## Conteúdo

### Escala de confiança (0.0 a 1.0)
| Faixa | Rótulo | Significado |
|-------|--------|-------------|
| 0.9-1.0 | Muito alta | Múltiplas fontes convergentes, instrumento validado |
| 0.7-0.8 | Alta | Instrumento validado, dados completos |
| 0.5-0.6 | Moderada | Proxy-inference ou dados parciais |
| 0.3-0.4 | Baixa | Inferência indireta com poucos dados |
| 0.0-0.2 | Muito baixa | Estimativa especulativa, sinalizar claramente |

### Fatores que aumentam a confiança
- Uso de instrumento psicometricamente validado
- Convergência entre múltiplos frameworks
- Dados recentes (menos de 2 anos)
- Autoavaliação corroborada por observadores
- Resolução bem-sucedida de contradições

### Fatores que diminuem a confiança
- Proxy-inference em vez de avaliação direta
- Dados antigos (mais de 3 anos)
- Contradições não resolvidas entre frameworks
- Apenas uma fonte de dados
- Sinais de desejabilidade social nas respostas

### Regras de aplicação
1. Atribuir confiança a cada dimensão individualmente
2. Nunca apresentar resultado sem nível de confiança
3. Recalcular confiança quando novas evidências surgem
4. Registrar histórico de confiança no confidence-history.yaml

---

## Exemplo Prático: Cálculo de Confiança Passo a Passo

Cenário: avaliar Extroversão de uma persona usando Big Five (direto) e DISC (proxy).

### Passo 1 — Confiança base por fonte
- **Big Five (NEO-PI-R)**: instrumento validado com dados completos → base = 0.85
- **DISC (proxy via Big Five)**: mapeamento proxy com confiança moderada → base = 0.55

### Passo 2 — Aplicar modificadores
Para o Big Five:
- Dados recentes (6 meses): +0.05 → 0.90
- Autoavaliação apenas (sem observador): -0.05 → 0.85
- **Confiança Big Five final = 0.85**

Para o DISC (proxy):
- Conversão proxy Big Five → DISC: penalidade de -0.20 já inclusa na base
- Dados recentes: +0.05 → 0.60
- **Confiança DISC proxy final = 0.60**

### Passo 3 — Verificar convergência
- Big Five diz: Extroversão alta (percentil 78)
- DISC proxy diz: perfil "I" alto (compatível com extroversão alta)
- **Convergência confirmada**: os dois resultados apontam na mesma direção

### Passo 4 — Calcular confiança composta
Quando fontes convergem, usar a fórmula:
`confiança_composta = max(fontes) + bonus_convergência`
`confiança_composta = 0.85 + 0.05 = 0.90`

Se houvesse divergência:
`confiança_composta = min(fontes) - penalidade_divergência`
`confiança_composta = 0.60 - 0.10 = 0.50`

### Passo 5 — Registrar e comunicar
- No relatório: "Extroversão alta (percentil 78, confiança: 0.90 - Muito Alta)"
- No `confidence-history.yaml`: registrar data, dimensão, fontes, valor final
- Sinalizar que DISC é [proxy] na seção de metodologia

> **Regra de ouro**: se a confiança composta ficar abaixo de 0.50, considere coletar
> dados adicionais antes de incluir a dimensão no relatório final.

## Referências
- `data/registries/confidence-history.yaml` — Histórico de confiança
- `docs/proxy-inference-methodology.md` — Metodologia de proxy
- `authority/models/confidence-scoring-model.md` — Modelo formal de confiança
