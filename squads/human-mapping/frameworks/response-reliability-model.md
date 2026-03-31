---
framework: response-reliability-model
category: operational
squad: human-mapping
version: "2.0.0"
---

# Response Reliability Model

## Propósito

O Response Reliability Model avalia a confiabilidade das respostas fornecidas pelo respondente ao longo do processo de assessment. Pessoas respondem instrumentos sob influência de diversos fatores: cansaço, desejabilidade social, falta de autoconhecimento, contexto emocional, motivação para distorcer. Este modelo fornece uma estrutura sistemática para avaliar se as respostas obtidas são confiáveis o suficiente para sustentar conclusões válidas.

A confiabilidade não é binária (confiável/não confiável). É um espectro que afeta o grau de certeza das conclusões. Respostas com baixa confiabilidade não invalidam o assessment — elas reduzem o confidence score e exigem triangulação adicional.

## Quando Usar

- Após a coleta de cada instrumento/camada
- Quando o facilitador percebe inconsistências nas respostas
- Antes de emitir qualquer conclusão ou recomendação
- Na etapa de reconciliação entre frameworks
- Quando o respondente demonstra resistência, pressa ou desinteresse
- Em contextos de alta pressão (contratação, promoção) onde distorção é esperada

## Modelo / Estrutura

### As 5 Dimensões de Confiabilidade

#### Dimensão 1: Consistência Interna
- As respostas dentro do mesmo instrumento são coerentes entre si?
- Itens que medem o mesmo construto convergem?
- Indicadores: escalas de consistência built-in (ex: Hogan tem validity scales)
- Score: 0.0 a 1.0

#### Dimensão 2: Estabilidade Temporal
- Se o respondente fosse testado novamente, daria respostas similares?
- Quando há re-test: comparar diretamente
- Quando não há re-test: avaliar pela firmeza das respostas e ausência de padrão aleatório
- Score: 0.0 a 1.0

#### Dimensão 3: Convergência entre Métodos
- Frameworks diferentes que medem construtos similares chegam a conclusões parecidas?
- Exemplo: Big Five Extraversion converge com DISC "I" (Influence)?
- Alta convergência = alta confiabilidade
- Baixa convergência = investigar (pode ser problema de resposta OU nuance real)
- Score: 0.0 a 1.0

#### Dimensão 4: Discriminância
- As respostas discriminam entre construtos diferentes?
- Tudo alto ou tudo baixo sugere response set (viés de resposta)
- Perfil completamente flat = suspeito
- Variabilidade adequada entre dimensões = boa discriminância
- Score: 0.0 a 1.0

#### Dimensão 5: Ausência de Viés Sistemático
- Há padrão de desejabilidade social?
- Há acquiescence bias (tendência a concordar com tudo)?
- Há extreme response bias (sempre nos extremos)?
- Há central tendency bias (sempre no meio)?
- Score: 0.0 a 1.0

### Escala de Confiabilidade Resultante

```
Score Composto = Média ponderada das 5 dimensões

Pesos:
  Consistência Interna:     0.25
  Estabilidade Temporal:     0.15
  Convergência:              0.30
  Discriminância:            0.15
  Ausência de Viés:          0.15

Interpretação:
  0.85 - 1.00  →  ALTA confiabilidade     → Conclusões firmes
  0.70 - 0.84  →  ADEQUADA confiabilidade  → Conclusões com ressalvas pontuais
  0.50 - 0.69  →  MODERADA confiabilidade  → Conclusões cautelosas, triangular mais
  0.30 - 0.49  →  BAIXA confiabilidade     → Conclusões tentativas, recomendar re-test
  0.00 - 0.29  →  INSUFICIENTE             → Não emitir conclusões, investigar causa
```

## Como Aplicar (step by step)

### Step 1: Coletar Dados de Cada Instrumento
- Registrar respostas brutas e scores processados
- Anotar condições de aplicação (ambiente, tempo, estado do respondente)
- Verificar se o instrumento tem escalas de validade internas

### Step 2: Avaliar Consistência Interna (Dimensão 1)
- Checar escalas de validade do instrumento (se disponíveis)
- Comparar itens reversos com itens diretos
- Verificar se não há padrão mecânico (ex: todas as respostas "4")
- Atribuir score de 0.0 a 1.0

### Step 3: Avaliar Estabilidade Temporal (Dimensão 2)
- Se há re-test disponível: correlacionar respostas
- Se não há: avaliar qualidade subjetiva (respostas reflexivas vs apressadas)
- Considerar o contexto emocional do respondente no momento
- Atribuir score de 0.0 a 1.0

### Step 4: Avaliar Convergência entre Métodos (Dimensão 3)
- Mapear construtos similares entre frameworks aplicados
- Verificar se convergem (ex: alto Neuroticism no Big Five + alto Excitable no Hogan HDS)
- Documentar convergências e divergências
- Divergência não é automaticamente problema — pode ser nuance legítima
- Atribuir score de 0.0 a 1.0

### Step 5: Avaliar Discriminância (Dimensão 4)
- Verificar variabilidade do perfil
- Perfil com todos os scores altos, todos baixos ou todos médios = flag
- Calcular desvio padrão dos scores: DP muito baixo = baixa discriminância
- Atribuir score de 0.0 a 1.0

### Step 6: Avaliar Ausência de Viés (Dimensão 5)
- Aplicar Social Desirability Screen (framework separado)
- Verificar padrões de aquiescência (tendency to agree)
- Checar extreme response style
- Atribuir score de 0.0 a 1.0

### Step 7: Calcular Score Composto
- Aplicar fórmula com pesos
- Classificar na escala de interpretação
- Documentar justificativa para cada dimensão
- Alimentar o Confidence Scoring Model

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Objetividade | Cada dimensão tem critérios observáveis, não apenas impressão |
| Documentação | Cada score tem justificativa escrita |
| Consistência do avaliador | Dois facilitadores chegariam ao mesmo score (±0.1) |
| Atualização | Score é recalculado quando nova informação chega |
| Transparência | O respondente pode solicitar ver sua avaliação de confiabilidade |

### Armadilhas Comuns
- Confundir baixa confiabilidade com perfil "errado" — respostas não confiáveis não significam que a pessoa é problemática
- Ignorar o contexto: respostas em processo seletivo têm viés esperado diferente de coaching
- Dar peso excessivo a uma dimensão: usar sempre o composto
- Não recalcular quando novas camadas trazem informação adicional

## Integração com Pipeline

### Input
- Respostas brutas de cada instrumento
- Condições de aplicação (do Intake Canvas, Q4)
- Resultados do Social Desirability Screen

### Output
- Score de confiabilidade por camada → **Confidence Scoring Model**
- Flags de investigação → **Cross-Framework Reconciliation**
- Recomendação de re-test ou triangulação adicional

### Posição no Pipeline
```
[Aplicação de Instrumento] → [Response Reliability Model] → [Interpretação]
                                      ↓
                            [Social Desirability Screen]
                                      ↓
                            [Confidence Scoring Model]
```

## Exemplos

### Exemplo 1: Candidato em Processo Seletivo
- Consistência Interna: 0.85 (respostas coerentes)
- Estabilidade Temporal: 0.60 (sem re-test, respostas rápidas)
- Convergência: 0.70 (Big Five e DISC convergem razoavelmente)
- Discriminância: 0.50 (perfil tendendo ao polo positivo em tudo)
- Ausência de Viés: 0.40 (padrão de desejabilidade social detectado)
- **Score Composto: 0.63 — MODERADA. Triangular com entrevista estruturada.**

### Exemplo 2: Coaching Voluntário
- Consistência Interna: 0.90
- Estabilidade Temporal: 0.85 (re-test em 2 semanas, alta correlação)
- Convergência: 0.90 (todos os frameworks convergem)
- Discriminância: 0.85 (perfil diferenciado)
- Ausência de Viés: 0.80 (reconhece pontos fracos)
- **Score Composto: 0.87 — ALTA. Conclusões firmes.**

### Exemplo 3: Funcionário Avaliado pelo Chefe (sem escolha)
- Consistência Interna: 0.75
- Estabilidade Temporal: 0.50 (respondeu em 5 minutos, sem reflexão)
- Convergência: 0.45 (discrepâncias entre instrumentos)
- Discriminância: 0.60 (algumas escalas flat)
- Ausência de Viés: 0.55 (padrão misto — nem cooperativo nem sabotador)
- **Score Composto: 0.56 — MODERADA. Cautela nas conclusões, considerar contexto involuntário.**
