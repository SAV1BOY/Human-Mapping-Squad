---
type: rubric
squad: human-mapping
version: "2.0.0"
---

# Report Quality Rubric

## Proposito

Definir criterios objetivos para avaliar a qualidade de um report de perfil produzido
pelo Human Mapping Squad. Esta rubric serve como checklist final antes da entrega,
garantindo que o report atenda padroes de accuracy, specificity, actionability e
rigor analitico. Reports que nao atingem o nivel minimo devem ser revisados.

## Escala de Avaliacao

| Score | Nivel | Significado |
|-------|-------|-------------|
| 1 | Insuficiente | Nao atende criterios minimos, requer reescrita |
| 2 | Abaixo do Padrao | Atende parcialmente, requer revisao significativa |
| 3 | Adequado | Atende criterios minimos, pode ser entregue com ajustes |
| 4 | Bom | Atende bem todos os criterios, ajustes menores |
| 5 | Excelente | Supera expectativas, referencia de qualidade |

## Criterios por Nivel

### Criterio 1: Accuracy (Precisao) — Peso 25%

**Pergunta-chave**: As afirmacoes do report sao factualmente corretas e
fundamentadas nos dados?

| Score | Descricao |
|-------|-----------|
| 1 | Contem erros factuais nos dados do assessment ou interpretacoes claramente incorretas |
| 2 | Interpretacoes imprecisas ou oversimplificadas; confunde construtos entre frameworks |
| 3 | Dados corretos; interpretacoes geralmente adequadas com 1-2 imprecisoes menores |
| 4 | Dados corretos; interpretacoes precisas e nuancadas; cross-references verificados |
| 5 | Dados corretos com fontes citadas; interpretacoes exemplares com caveats apropriados |

**Red Flags de Accuracy**:
- Tipo MBTI incorreto ou inconsistente ao longo do report
- Scores de assessment citados erroneamente
- Confusao entre frameworks (ex: atribuir faceta do Big Five ao HEXACO)
- Afirmacoes categoricas sem dados que suportem

### Criterio 2: Specificity (Nao-Barnum) — Peso 25%

**Pergunta-chave**: As descricoes sao suficientemente especificas para distinguir
ESTE respondente de qualquer outra pessoa?

| Score | Descricao |
|-------|-----------|
| 1 | Descricoes genericas aplicaveis a qualquer pessoa ("voce valoriza honestidade") |
| 2 | Maioria das descricoes sao vagas; poucas sao diferenciadas |
| 3 | Mix de descricoes especificas e genericas; as mais importantes sao especificas |
| 4 | Descricoes predominantemente especificas com exemplos e dados concretos |
| 5 | Cada afirmacao e unica para este respondente; leitor reconheceria a pessoa |

**Teste de Barnum**: Para cada afirmacao, perguntar "isto se aplicaria a 50%+ das pessoas?"
Se sim, a afirmacao e Barnum e deve ser refinada.

**Exemplos contrastados**:
- BARNUM: "Voce e uma pessoa dedicada que se preocupa com a qualidade do seu trabalho"
- ESPECIFICO: "Seu padrao Achiever (#1) + Deliberative (#4) cria um ciclo de alta
  produtividade seguido de revisao meticulosa — voce produz muito E revisa tudo,
  o que explica tanto sua reputacao de qualidade quanto a sobrecarga reportada"

### Criterio 3: Actionability (Acionabilidade) — Peso 20%

**Pergunta-chave**: O leitor sabe EXATAMENTE o que fazer depois de ler o report?

| Score | Descricao |
|-------|-----------|
| 1 | Nenhuma recomendacao de desenvolvimento, ou recomendacoes vagas ("melhore sua comunicacao") |
| 2 | Recomendacoes genericas sem conexao com o perfil especifico |
| 3 | 3-5 recomendacoes conectadas ao perfil, mas sem primeiro passo concreto |
| 4 | 3-5 recomendacoes especificas com primeiro passo, timeline e connection ao perfil |
| 5 | Plano de desenvolvimento priorizado usando Impact x Effort, com sequenciamento e milestones |

**Checklist de Actionability**:
- [ ] Cada recomendacao tem um "primeiro passo" concreto?
- [ ] As recomendacoes foram priorizadas (nao e apenas uma lista)?
- [ ] Ha conexao explicita entre cada recomendacao e os dados do perfil?
- [ ] O respondente conseguiria comecar AMANHA com pelo menos 1 acao?
- [ ] As acoes alavancam strengths do respondente?

### Criterio 4: Evidence-Based (Baseado em Evidencias) — Peso 15%

**Pergunta-chave**: Cada afirmacao significativa esta vinculada a dados concretos?

| Score | Descricao |
|-------|-----------|
| 1 | Afirmacoes sem qualquer referencia a dados ou assessments |
| 2 | Referencia ocasional a dados, maioria das afirmacoes e opiniao do analista |
| 3 | Principais conclusoes referenciadas; algumas afirmacoes sem suporte |
| 4 | Todas as conclusoes referenciadas; evidencias citadas inline |
| 5 | Cada afirmacao com evidencia, confidence score e citacao da fonte de dados |

**Formato recomendado para evidencia inline**:
"[Afirmacao] (Big Five E=82, DISC I alto, CliftonStrengths Communication #2; confidence: 0.85)"

### Criterio 5: Confidence-Scored — Peso 10%

**Pergunta-chave**: O report inclui confidence scores para afirmacoes significativas?

| Score | Descricao |
|-------|-----------|
| 1 | Nenhum confidence score em nenhuma parte do report |
| 2 | Confidence score apenas no resumo geral, nao em afirmacoes individuais |
| 3 | Confidence scores nas principais conclusoes (traits, types, motivacoes) |
| 4 | Confidence scores em todas as afirmacoes significativas + explicacao do calculo |
| 5 | Confidence scores completos + metadados (quais criterios contribuiram, quais dados faltam) |

### Criterio 6: Readability (Legibilidade) — Peso 5%

**Pergunta-chave**: O report e acessivel para o publico-alvo?

| Score | Descricao |
|-------|-----------|
| 1 | Jargao tecnico sem explicacao; estrutura confusa; linguagem inacessivel |
| 2 | Excesso de jargao; estrutura parcialmente organizada; dificil de seguir |
| 3 | Linguagem adequada; estrutura clara; jargao explicado quando necessario |
| 4 | Linguagem acessivel e engajante; estrutura intuitiva; flow narrativo |
| 5 | Linguagem elegante e precisa; estrutura exemplar; leitor nao-tecnico compreende |

## Como Aplicar

### Passo 1: Avaliar cada criterio (1-5)
Ler o report completo e atribuir score para cada um dos 6 criterios.

### Passo 2: Calcular score ponderado
```
Quality Score = (Accuracy x 0.25) + (Specificity x 0.25) + (Actionability x 0.20)
             + (Evidence x 0.15) + (Confidence x 0.10) + (Readability x 0.05)
```

### Passo 3: Determinar acao

| Score Final | Nivel | Acao |
|-------------|-------|------|
| 1.0 - 2.0 | Insuficiente | Reescrever o report |
| 2.0 - 3.0 | Abaixo do Padrao | Revisao significativa antes da entrega |
| 3.0 - 3.5 | Adequado | Ajustes pontuais, pode entregar |
| 3.5 - 4.5 | Bom | Ajustes menores opcionais |
| 4.5 - 5.0 | Excelente | Pronto para entrega |

### Passo 4: Identificar criterios abaixo de 3
Qualquer criterio individual abaixo de 3 e um blocker que deve ser corrigido,
independente do score total.

## Exemplos

### Exemplo: Report com Score 4.1 (Bom)
- Accuracy: 4 (dados corretos, interpretacoes precisas)
- Specificity: 4 (descricoes diferenciadas, poucos Barnums)
- Actionability: 4 (5 recomendacoes com primeiro passo e timeline)
- Evidence: 4 (conclusoes referenciadas inline)
- Confidence: 3 (scores presentes nas conclusoes principais, falta em secundarias)
- Readability: 5 (excelente flow narrativo)
- **Calculo**: (4x0.25)+(4x0.25)+(4x0.20)+(4x0.15)+(3x0.10)+(5x0.05) = 4.05
- **Acao**: Ajustar confidence scores em afirmacoes secundarias. Pronto para entrega.

### Exemplo: Report com Score 2.3 (Abaixo do Padrao)
- Accuracy: 3 (dados corretos, 2 interpretacoes imprecisas)
- Specificity: 2 (muitas afirmacoes Barnum)
- Actionability: 2 (recomendacoes genericas)
- Evidence: 2 (pouca referencia a dados)
- Confidence: 1 (nenhum confidence score)
- Readability: 4 (bem escrito, porem vazio de conteudo)
- **Calculo**: (3x0.25)+(2x0.25)+(2x0.20)+(2x0.15)+(1x0.10)+(4x0.05) = 2.25
- **Acao**: Revisao significativa. Adicionar especificidade, evidencias, confidence scores
  e recomendacoes actionable antes de entregar.
