---
framework: contradiction-baseline
category: operational
squad: human-mapping
version: "2.0.0"
---

# Contradiction Baseline

## Propósito

O Contradiction Baseline define o nível aceitável de contradição entre frameworks e dentro de um perfil individual. A premissa fundamental é: **alguma contradição é NORMAL**. Pessoas são seres complexos, contextuais e em constante adaptação. Um perfil completamente livre de contradição é mais suspeito do que um com contradições moderadas.

Este framework separa três tipos de contradição: esperada (sinal de complexidade humana), preocupante (pode indicar problema de resposta) e invalidante (compromete as conclusões). Cada camada tem um baseline diferente porque construtos diferentes têm graus diferentes de estabilidade e sobreposição.

## Quando Usar

- Durante a reconciliação entre frameworks (antes do Cross-Framework Reconciliation)
- Quando o facilitador encontra resultados aparentemente conflitantes
- Para decidir se uma contradição merece investigação ou é aceitável
- Na calibração de confiança de cada camada
- Para explicar ao solicitante por que "o MBTI diz X mas o Big Five diz Y"

## Modelo / Estrutura

### Tipos de Contradição

#### Contradição Esperada (Normal)
- Frameworks que medem construtos relacionados mas não idênticos
- Exemplo: MBTI = INTJ (introvertido) mas CliftonStrengths tem "Woo" no Top 10
  - Explicação: INTJ reflete preferência cognitiva; Woo pode ser um talento aprendido em contexto específico
- Exemplo: Big Five Agreeableness baixo mas Eneagrama Tipo 2 (helper)
  - Explicação: Tipo 2 ajuda por necessidade emocional, não por agreeableness natural

#### Contradição Preocupante (Investigar)
- Frameworks que medem o MESMO construto e divergem significativamente
- Exemplo: Big Five Extraversion = percentil 90 mas DISC = "S" puro (estabilidade/introversão)
- Exemplo: Hogan HPI Adjustment = percentil 85 mas Big Five Neuroticism = percentil 80
- Requer investigação: problema de resposta? Contexto diferente? Adaptação?

#### Contradição Invalidante (Comprometedora)
- Contradição tão severa que indica problema sistêmico nas respostas
- Exemplo: 5+ contradições preocupantes simultâneas
- Exemplo: O respondente se descreve de maneira completamente oposta em dois instrumentos aplicados no mesmo dia
- Ação: pausar, investigar causa, possivelmente re-aplicar

### Baseline por Camada

```
Camada                    Contradição Esperada    Preocupante     Invalidante
─────────────────────────────────────────────────────────────────────────────
Traços (Big Five/Hogan)   0-1 contradição         2-3             4+
Tipos (MBTI/DISC)         1-2 contradições        3-4             5+
Motivação (Reiss/VIA)     1-3 contradições        4-5             6+
Forças (Clifton/VIA)      2-3 contradições        4-5             6+
Conação (Kolbe)           0-1 contradição         2               3+
Inteligência/Referencial  0-1 contradição         2               3+
Carreira (Holland/Schein) 1-2 contradições        3               4+
Papéis de Time (Belbin)   1-2 contradições        3               4+
```

### Por que Contradição às Vezes é Sinal de PROFUNDIDADE

Não toda contradição é ruim. Algumas contradições revelam:
- **Adaptação contextual**: pessoa genuinamente se comporta diferente em contextos diferentes
- **Crescimento**: pessoa está em transição e mostra traços de quem era e quem está se tornando
- **Complexidade**: pessoas maduras integram polaridades (gentil E firme, criativo E organizado)
- **Camadas diferentes**: traço (quem sou) vs tipo (como prefiro) vs motivação (por que faço) podem legitimamente divergir

### Quando Contradição é Sinal de PROBLEMA

- Contradição em construtos que deveriam convergir fortemente (mesmo instrumento re-aplicado)
- Contradição que não tem explicação contextual plausível
- Contradição acompanhada de alta desejabilidade social
- Contradição consistente em uma direção (tudo diverge no mesmo sentido = distorção)

## Como Aplicar (step by step)

### Step 1: Mapear Construtos Correspondentes
- Listar todos os frameworks aplicados
- Identificar quais construtos se sobrepõem entre eles
- Criar uma tabela de correspondência (ex: Big Five E ↔ DISC I+D, MBTI E/I)

### Step 2: Comparar Resultados nos Construtos Correspondentes
- Para cada par de construtos correspondentes, comparar os resultados
- Marcar como convergente (mesma direção) ou divergente (direções opostas)
- Registrar a magnitude da divergência

### Step 3: Classificar Cada Contradição
- Consultar o baseline da camada
- Classificar como Esperada, Preocupante ou Invalidante
- Para cada contradição, formular uma hipótese explicativa

### Step 4: Contar e Avaliar
- Quantas contradições de cada tipo existem?
- Qual é o padrão? (aleatório, direcional, concentrado em uma camada?)
- A quantidade está dentro do baseline?

### Step 5: Decidir Ação
- Se dentro do baseline esperado → prosseguir normalmente, documentar
- Se na zona preocupante → ativar Cross-Framework Reconciliation
- Se na zona invalidante → pausar, investigar, considerar re-aplicação

### Step 6: Documentar
- Registrar todas as contradições encontradas, sua classificação e resolução
- Incluir no relatório final como nota de transparência
- Alimentar o Confidence Scoring Model com o resultado

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Calibração | Os baselines são revisados com base em dados empíricos do squad |
| Não-alarmismo | Contradições esperadas são tratadas como normais, não como problemas |
| Investigação adequada | Contradições preocupantes são investigadas, não apenas flaggeadas |
| Contextualização | Cada contradição é avaliada no contexto do indivíduo e da situação |
| Transparência | Contradições são reportadas ao solicitante quando relevantes |

### Erros Comuns
- Tratar toda contradição como problema (over-flagging)
- Ignorar contradições genuinamente preocupantes (under-flagging)
- Não considerar que frameworks diferentes medem coisas diferentes
- Esperar convergência perfeita entre instrumentos (expectativa irreal)
- Forçar reconciliação quando a contradição é legítima e informativa

## Integração com Pipeline

### Input
- Resultados de todos os frameworks aplicados
- Tabela de correspondência entre construtos
- Contexto do respondente (do Intake Canvas)

### Output
- Classificação de contradições → **Cross-Framework Reconciliation**
- Ajuste de confidence → **Confidence Scoring Model**
- Narrativa de complexidade → **Persona Synthesis Model**

### Posição no Pipeline
```
[Resultados dos Frameworks] → [Contradiction Baseline] → [Cross-Framework Reconciliation]
                                       ↓                            ↓
                              [Confidence Scoring]          [Persona Synthesis]
```

## Exemplos

### Exemplo 1: Contradição Esperada (Normal)
- Big Five Conscientiousness = percentil 85 (alta organização)
- Kolbe Quick Start = 8 (alta impulsividade, age rápido)
- **Aparente contradição**: Organizado MAS impulsivo?
- **Resolução**: Conscientiousness mede disciplina global; Quick Start mede modo de iniciar ação. Pessoa pode ser disciplinada na manutenção mas impulsiva no início. Contradição ESPERADA — revela complexidade real.

### Exemplo 2: Contradição Preocupante
- Big Five Extraversion = percentil 20 (introvertido)
- DISC = Alto "I" (Influence = extrovertido socialmente)
- Hogan HPI Sociability = percentil 75 (gregário)
- **3 frameworks, 2 dizem extrovertido, 1 diz introvertido**
- **Investigação necessária**: Big Five aplicado quando? DISC e Hogan no mesmo contexto? Pessoa pode estar em adaptação. Investigar com Cross-Framework Reconciliation.

### Exemplo 3: Contradição Invalidante
- Respondente em processo seletivo
- Big Five: perfil "perfeito" em todos os fatores
- Hogan HPI: percentis todos acima de 80
- Hogan HDS: zero elevações (sem dark side)
- DISC: perfil "ideal" para a vaga
- Kolbe: todas as dimensões no range "ótimo" para o cargo
- **5 frameworks, ZERO contradições, ZERO fraquezas = IMPLAUSÍVEL**
- **Ação**: Classificar como potencialmente invalidante por excesso de desejabilidade. Ativar Social Desirability Screen. Considerar assessment center presencial.
