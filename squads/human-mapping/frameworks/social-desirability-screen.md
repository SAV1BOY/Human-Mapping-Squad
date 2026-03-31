---
framework: social-desirability-screen
category: operational
squad: human-mapping
version: "2.0.0"
---

# Social Desirability Screen

## Propósito

O Social Desirability Screen é um protocolo de detecção de respostas socialmente desejáveis — quando o respondente, consciente ou inconscientemente, apresenta uma versão idealizada de si mesmo. Este é o viés mais comum em assessments, especialmente em contextos de contratação e avaliação de desempenho. Não é necessariamente desonestidade; frequentemente é uma combinação de falta de autoconhecimento, pressão situacional e tendência humana natural de querer ser visto positivamente.

O screen não busca "pegar" a pessoa mentindo. Busca calibrar a interpretação: se detectamos desejabilidade social alta, ajustamos o confidence score para baixo e triangulamos com fontes adicionais.

## Quando Usar

- Em TODO assessment, como checagem de rotina
- Com ênfase especial em contextos de contratação e promoção
- Quando o perfil parece "bom demais" em todas as dimensões
- Quando há discrepância entre autorrelato e dados observados
- Antes de emitir conclusões em ambientes de alta pressão

## Modelo / Estrutura

### Os 4 Indicadores de Desejabilidade Social

#### Indicador 1: Respostas Sistematicamente no Polo Positivo
- Todos os scores em dimensões "desejáveis" estão altos
- Todos os scores em dimensões "indesejáveis" estão baixos
- Exemplo: Alta Conscientiousness, Alta Agreeableness, Baixa Neuroticism, Alta Extraversion — tudo ao mesmo tempo no extremo
- Threshold: >80% dos scores no quartil mais "desejável"

#### Indicador 2: Ausência de Fraquezas Admitidas
- A pessoa não reconhece nenhum ponto de desenvolvimento
- Em instrumentos com itens de vulnerabilidade, todas as respostas negam fraqueza
- Em entrevista, todas as "fraquezas" são na verdade forças disfarçadas ("sou perfeccionista demais")
- Threshold: zero itens de vulnerabilidade endossados

#### Indicador 3: Inconsistência entre Autorrelato e Comportamento Observado
- O que a pessoa diz sobre si mesma não bate com o que se observa
- Exemplo: "Sou muito organizado" mas entrega atrasada e sem estrutura
- Exemplo: "Sou ótimo em conflito" mas evita qualquer confronto
- Requer dados observacionais (referências, entrevistas, feedback 360)
- Threshold: 3+ inconsistências significativas

#### Indicador 4: Padrão "Too Good to Be True"
- O perfil global é implausível na sua perfeição
- Nenhum ser humano é excelente em tudo simultaneamente
- Exemplo: Alta em todas as 34 CliftonStrengths domains, alto em todos os Big Five, zero dark side no Hogan HDS
- Threshold: avaliação holística — quando "tudo é ótimo", algo está errado

### Classificação de Severidade

```
Nenhum indicador presente        →  SEM EVIDÊNCIA de desejabilidade social
1 indicador presente             →  LEVE — monitorar, não requer ação
2 indicadores presentes          →  MODERADA — ajustar confidence, triangular
3 indicadores presentes          →  ALTA — cautela significativa nas conclusões
4 indicadores presentes          →  CRÍTICA — considerar invalidar e re-aplicar
```

## Como Aplicar (step by step)

### Step 1: Revisão Inicial dos Scores
- Plotar todos os scores do respondente em uma tabela unificada
- Marcar os que estão no polo "desejável" de cada dimensão
- Calcular a porcentagem de scores no quartil desejável
- Se >80%: flag para Indicador 1

### Step 2: Análise de Itens de Vulnerabilidade
- Revisar itens específicos que medem vulnerabilidade/fraqueza
- Verificar se o respondente endossou algum item de vulnerabilidade
- Checar respostas em instrumentos com escalas de impression management (Hogan, NEO-PI-R)
- Se zero fraquezas admitidas: flag para Indicador 2

### Step 3: Cruzamento com Dados Observacionais
- Se disponíveis, comparar autorrelato com:
  - Feedback 360°
  - Referências profissionais
  - Observação comportamental em entrevista
  - Histórico de desempenho
- Documentar inconsistências específicas
- Se 3+ inconsistências significativas: flag para Indicador 3

### Step 4: Avaliação Holística do Perfil
- Olhar o perfil como um todo
- Perguntar: "Esse perfil é plausível para um ser humano real?"
- Comparar com base de perfis conhecidos — perfeição completa é estatisticamente improvável
- Se o perfil parece implausível: flag para Indicador 4

### Step 5: Classificar Severidade
- Contar o número de indicadores flaggeados
- Aplicar a classificação de severidade
- Documentar a classificação com evidências específicas

### Step 6: Executar Protocolo de Ação

#### Se LEVE (1 indicador):
- Documentar, mas prosseguir normalmente
- Reduzir confidence score da camada afetada em 0.05-0.10
- Mencionar no relatório como nota

#### Se MODERADA (2 indicadores):
- Reduzir confidence score em 0.15-0.20
- Buscar triangulação ativa (dados observacionais, entrevista aprofundada)
- Na devolutiva, explorar os pontos de discrepância com o respondente
- Não emitir conclusões fortes sem triangulação

#### Se ALTA (3 indicadores):
- Reduzir confidence score em 0.25-0.35
- Obrigatório triangular com pelo menos 2 fontes externas
- Considerar re-aplicação com instruções explícitas de honestidade
- Reportar a preocupação ao solicitante (sem julgamento sobre o respondente)
- Documentar que conclusões são preliminares

#### Se CRÍTICA (4 indicadores):
- Reduzir confidence score em 0.40+
- Discutir com o squad se o assessment tem validade suficiente
- Considerar re-aplicação com mudança de contexto (ex: framing diferente)
- Se contratação: recomendar fontes alternativas (assessment center, trial period)
- Não emitir relatório conclusivo — emitir relatório de cautela

## Critérios de Qualidade

| Critério | Indicador de Qualidade |
|----------|----------------------|
| Não-julgamental | O screen avalia respostas, não o caráter da pessoa |
| Baseado em evidência | Cada flag tem critérios observáveis e mensuráveis |
| Proporcional | A ação é proporcional à severidade detectada |
| Documentado | Toda detecção é registrada com evidências |
| Contextualizado | Considera que alguma desejabilidade social é ESPERADA em certos contextos |

### Nota Importante sobre Viés do Facilitador
- Desejabilidade social não é mentira intencional na maioria dos casos
- Muitas pessoas genuinamente não conhecem seus pontos fracos
- O contexto influencia: em processo seletivo, é RACIONAL apresentar seu melhor lado
- O screen não deve ser usado para julgar a pessoa, mas para calibrar interpretações

## Integração com Pipeline

### Input
- Scores de todos os instrumentos aplicados
- Dados observacionais disponíveis (entrevistas, referências, feedback)
- Contexto do assessment (do Intake Canvas)

### Output
- Classificação de severidade → **Response Reliability Model** (Dimensão 5)
- Ajuste de confidence → **Confidence Scoring Model**
- Recomendação de ação → facilitador e solicitante

### Posição no Pipeline
```
[Scores dos Instrumentos] → [Social Desirability Screen] → [Response Reliability Model]
                                      ↓
                            [Confidence Scoring Model]
                                      ↓
                            [Decisão: prosseguir / triangular / re-aplicar]
```

## Exemplos

### Exemplo 1: Candidato a VP de Vendas
- Indicador 1: 85% dos scores no quartil desejável → FLAG
- Indicador 2: Impression Management Scale do Hogan = percentil 90 → FLAG
- Indicador 3: Referência menciona "dificuldade com feedback" — autorrelato diz "adoro feedback" → FLAG
- Indicador 4: Perfil global plausível para vendedor (extroversão alta é esperada)
- **Classificação: ALTA (3 indicadores). Triangulação obrigatória. Assessment center recomendado.**

### Exemplo 2: Pessoa em Coaching Voluntário
- Indicador 1: 55% dos scores no quartil desejável → OK
- Indicador 2: Admite 3 pontos fracos espontaneamente → OK
- Indicador 3: Sem dados observacionais disponíveis → N/A
- Indicador 4: Perfil realista com pontos fortes e fracos → OK
- **Classificação: SEM EVIDÊNCIA. Prosseguir normalmente.**

### Exemplo 3: Líder Avaliado em Programa Corporativo Obrigatório
- Indicador 1: 70% no quartil desejável → borderline, mas não flag
- Indicador 2: Admite uma fraqueza genérica → parcialmente flag
- Indicador 3: Feedback 360° diverge em gestão de conflito → FLAG
- Indicador 4: Perfil plausível, mas com pontos suspeitamente altos em "soft skills"
- **Classificação: MODERADA (2 indicadores borderline + 1 claro). Ajustar confidence, explorar na devolutiva.**
