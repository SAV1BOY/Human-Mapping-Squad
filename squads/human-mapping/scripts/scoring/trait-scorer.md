---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Trait Scorer

## Propósito

Calcular os scores de traços de personalidade (Big Five / OCEAN) a partir das respostas coletadas, aplicando pesos, correções de viés e normalização para gerar um perfil de traços confiável.

## Input

- `responses`: Array de respostas da camada de traços (pergunta + resposta + metadata)
- `question-weights`: Pesos de cada pergunta por dimensão (de `lib/questions/traits/`)
- `correction-factor`: Fator de correção de desejabilidade social
- `depth-mode`: Modo de profundidade da sessão

## Processo (step by step algorithm)

1. **Mapear respostas para dimensões**
   - Cada resposta contribui para 1-2 dimensões OCEAN
   - Aplicar peso da pergunta (definido no banco de perguntas)
   - Inverter score para perguntas de escala reversa

2. **Calcular score bruto por dimensão**
   - Para cada dimensão (O, C, E, A, N):
     - Somar (resposta * peso) para todas as perguntas da dimensão
     - Dividir pela soma dos pesos (média ponderada)
     - Resultado: score bruto de 0-100

3. **Aplicar correção de desejabilidade social**
   - Para dimensões afetadas (tipicamente A, C, estabilidade emocional):
     - `score_corrigido = score_bruto - (correction_factor * peso_dimensao)`
   - Garantir que score corrigido permaneça no range 0-100

4. **Normalizar scores**
   - Aplicar normalização contra normas populacionais (de `lib/norms/`)
   - Calcular percentil para cada dimensão
   - Ajustar para contexto demográfico se dados disponíveis

5. **Calcular sub-facetas** (quando profundidade permite)
   - Para modo `/start` e `/deep`, decompor cada dimensão em facetas:
     - O: Imaginação, Curiosidade Intelectual, Abertura a Experiências
     - C: Organização, Disciplina, Orientação para Resultados
     - E: Assertividade, Sociabilidade, Energia/Entusiasmo
     - A: Compaixão, Cooperação, Confiança
     - N: Ansiedade, Volatilidade, Sensibilidade ao Estresse

6. **Classificar nível por dimensão**
   - Baixo: score < 35
   - Moderado-Baixo: 35-45
   - Moderado: 45-55
   - Moderado-Alto: 55-65
   - Alto: score > 65

7. **Gerar perfil de traços completo**

## Output

- `trait-scores`: Scores por dimensão OCEAN (0-100) com percentis
- `trait-facets`: Sub-facetas quando disponíveis
- `trait-levels`: Classificação por nível (baixo a alto) por dimensão
- `raw-scores`: Scores brutos antes de correção
- `correction-applied`: Detalhes da correção aplicada

## Uso

Chamado por `tasks/assessment/run-trait-layer.md` após a coleta de todas as respostas da camada de traços.
