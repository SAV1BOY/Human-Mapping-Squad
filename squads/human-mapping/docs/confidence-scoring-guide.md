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

## Referências
- `data/registries/confidence-history.yaml` — Histórico de confiança
- `docs/proxy-inference-methodology.md` — Metodologia de proxy
