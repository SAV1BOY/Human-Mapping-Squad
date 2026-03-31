---
framework: cross-framework-reconciliation
category: operational
squad: human-mapping
version: "2.0.0"
---

# Cross-Framework Reconciliation

## Propósito

O Cross-Framework Reconciliation é o protocolo completo para reconciliar conflitos entre frameworks de assessment. Quando múltiplos instrumentos são aplicados a uma mesma pessoa, divergências são inevitáveis. Este protocolo transforma conflitos aparentes em insights mais profundos sobre o indivíduo, separando divergências legítimas (que revelam complexidade) de divergências problemáticas (que indicam erro de medição ou distorção).

O protocolo segue 6 passos sequenciais: Detectar → Classificar → Investigar → Contextualizar → Reconciliar → Documentar. Cada passo tem critérios claros e outputs definidos.

## Quando Usar

- Após o Contradiction Baseline classificar contradições como "Preocupantes" ou "Invalidantes"
- Quando dois ou mais frameworks divergem em construtos que deveriam convergir
- Na fase de síntese do perfil, antes de montar o Persona Synthesis
- Quando o solicitante questiona por que resultados parecem contraditórios
- Em sessões de calibração do squad para resolver casos complexos

## Modelo / Estrutura

### Os 6 Passos da Reconciliação

```
┌──────────┐    ┌────────────┐    ┌────────────┐    ┌───────────────┐    ┌────────────┐    ┌────────────┐
│ DETECTAR │ →  │ CLASSIFICAR│ →  │ INVESTIGAR │ →  │CONTEXTUALIZAR │ →  │ RECONCILIAR│ →  │ DOCUMENTAR │
│          │    │ (severidade│    │ (traço real │    │ (em que        │    │ (resolução │    │ (registro  │
│          │    │  do conflito)   │  vs adaptação?)  │  contexto cada │    │  final)    │    │  formal)   │
│          │    │            │    │            │    │  framework     │    │            │    │            │
│          │    │            │    │            │    │  está certo?)  │    │            │    │            │
└──────────┘    └────────────┘    └────────────┘    └───────────────┘    └────────────┘    └────────────┘
```

### Classificação de Severidade do Conflito

| Nível | Descrição | Ação |
|-------|-----------|------|
| **S1 - Superficial** | Aparente conflito que se resolve com análise básica | Resolver inline, sem investigação profunda |
| **S2 - Moderado** | Conflito real entre construtos relacionados | Investigar contexto, buscar explicação |
| **S3 - Significativo** | Conflito em construtos que deveriam convergir fortemente | Investigação profunda, triangulação necessária |
| **S4 - Fundamental** | Conflito que questiona a validade de um ou mais instrumentos | Considerar re-aplicação, consultar squad |

### Matriz de Reconciliação Comum

| Framework A diz... | Framework B diz... | Reconciliação Provável |
|--------------------|--------------------|----------------------|
| Big Five E alto | MBTI Introvertido | MBTI mede preferência cognitiva, Big Five mede comportamento social → ambos podem estar certos |
| Hogan HDS elevado | Big Five sem flag | Hogan HDS mede comportamento sob stress → pessoa funciona bem no normal mas descarrila sob pressão |
| DISC = D alto | Agreeableness alto | DISC D mede assertividade em contexto de trabalho; Agreeableness é disposição geral → adaptação contextual |
| CliftonStrengths "Harmony" | Eneagrama Tipo 8 | Harmony como talento de criar consenso; Tipo 8 como motivação de controle → usa consenso PARA controlar |
| Kolbe Quick Start baixo | Perfil "inovador" em outros instrumentos | Kolbe mede modo de ação, não capacidade → pessoa pode ser criativa mas executar de forma metódica |

## Como Aplicar (step by step)

### Step 1: DETECTAR
- Receber as contradições classificadas pelo Contradiction Baseline
- Listar cada par conflitante: [Framework A: Resultado] vs [Framework B: Resultado]
- Identificar o construto em conflito (ex: extroversão, organização, assertividade)
- Verificar se o conflito é entre frameworks da MESMA camada ou de camadas DIFERENTES

### Step 2: CLASSIFICAR (Severidade)
- Para cada conflito, avaliar a severidade (S1 a S4)
- Critérios para classificação:
  - S1: Frameworks medem construtos apenas vagamente relacionados
  - S2: Frameworks medem construtos moderadamente relacionados
  - S3: Frameworks medem o mesmo construto (ex: dois instrumentos de traços divergem)
  - S4: O mesmo instrumento re-aplicado dá resultados diferentes, ou o conflito é tão amplo que questiona toda a avaliação

### Step 3: INVESTIGAR (Traço Real vs Adaptação?)
- Para cada conflito S2+, perguntar:
  1. **Traço real?** A pessoa genuinamente é assim em um contexto e diferente em outro?
  2. **Adaptação?** A pessoa se adapta ao contexto de forma consciente ou automática?
  3. **Erro de medição?** O instrumento falhou? A pessoa respondeu mal?
  4. **Construto diferente?** Os frameworks estão medindo coisas diferentes que PARECEM iguais?
- Buscar evidências para cada hipótese (dados adicionais, entrevista, observação)

### Step 4: CONTEXTUALIZAR
- Para cada framework no conflito, identificar:
  - Que contexto ele captura? (trabalho, geral, sob stress, ideal, necessidade?)
  - Em que população foi validado?
  - Qual sua teoria de base?
- Formular: "Framework A está certo quando [contexto A]; Framework B está certo quando [contexto B]"
- Se ambos podem estar certos em contextos diferentes → não é realmente conflito

### Step 5: RECONCILIAR
- Escolher a estratégia de reconciliação:
  1. **Integração**: Ambos estão certos → criar narrativa que integra ambos (80% dos casos)
  2. **Priorização**: Um framework é mais válido para o construto → priorizar (15% dos casos)
  3. **Invalidação**: Um dos resultados não é confiável → desconsiderar com documentação (5% dos casos)
- Redigir a reconciliação em uma frase clara
- Verificar se a reconciliação é coerente com o restante do perfil

### Step 6: DOCUMENTAR
- Registrar:
  - O conflito detectado
  - A severidade classificada
  - As hipóteses investigadas
  - A contextualização
  - A reconciliação escolhida (com estratégia)
  - O impacto no confidence score
- Formato: tabela padronizada no relatório final
- Incluir na narrativa de síntese quando a reconciliação gera insight valioso

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Completude | Todo conflito S2+ foi tratado nos 6 passos |
| Coerência | A reconciliação é coerente com o perfil global |
| Evidência | Cada reconciliação tem justificativa baseada em dados |
| Nuance | Não força convergência artificial — mantém complexidade quando legítima |
| Transparência | O solicitante pode entender a reconciliação sem jargão técnico |
| Reprodutibilidade | Outro facilitador chegaria à mesma reconciliação com os mesmos dados |

### Anti-patterns de Reconciliação
- **Forçar convergência**: Escolher um framework e ignorar o outro sem justificativa
- **Relativizar tudo**: "Cada framework mede uma coisa diferente" sem investigar de fato
- **Ignorar e seguir**: Não tratar o conflito e emitir conclusão como se não existisse
- **Sobrecorrigir**: Reduzir confiança excessivamente por conflitos esperados

## Integração com Pipeline

### Input
- Contradições classificadas do **Contradiction Baseline**
- Dados de todos os frameworks aplicados
- Contexto do assessment (do **Intake Canvas**)
- Dados observacionais disponíveis

### Output
- Reconciliações resolvidas → **Persona Synthesis Model**
- Ajustes de confiança → **Confidence Scoring Model**
- Insights de complexidade → **Executive Brief Model** e relatório completo

### Posição no Pipeline
```
[Contradiction Baseline] → [Cross-Framework Reconciliation] → [Persona Synthesis Model]
                                      ↓
                            [Confidence Scoring Model]
```

## Exemplos

### Exemplo 1: Reconciliação S1 (Superficial)
- **Conflito**: MBTI = INFJ (introvertido) vs CliftonStrengths Top 5 inclui "Communication"
- **Classificação**: S1 — construtos vagamente relacionados
- **Reconciliação**: MBTI I mede preferência por processamento interno. Communication no Clifton mede talento de articular ideias. Pessoa prefere processar internamente (I) mas quando comunica, faz bem (Communication). Integração: comunicador introvertido — prefere qualidade a quantidade de interação.

### Exemplo 2: Reconciliação S3 (Significativa)
- **Conflito**: Big Five Neuroticism = percentil 75 (alta) vs Hogan HPI Adjustment = percentil 70 (alta, = baixa neuroticism)
- **Classificação**: S3 — mesmo construto, resultados opostos
- **Investigação**: Big Five aplicado em contexto pessoal; Hogan em contexto profissional. Pessoa pode ter alta regulação emocional no trabalho mas alta reatividade na vida pessoal. Confirmado por entrevista.
- **Reconciliação**: Priorizar Hogan para predição de comportamento no trabalho; usar Big Five para entender vulnerabilidade pessoal. Ambos são válidos em seus respectivos contextos.

### Exemplo 3: Reconciliação S4 (Fundamental)
- **Conflito**: Quase todos os frameworks indicam perfil introvertido, metódico, analítico. Mas DISC feito pela empresa anterior indica perfil DI alto (dominante e influente).
- **Classificação**: S4 — divergência fundamental
- **Investigação**: DISC anterior foi feito em contexto de avaliação de desempenho com pressão do gestor. Possível distorção situacional.
- **Reconciliação**: Invalidar o DISC anterior. Re-aplicar se necessário. Manter perfil convergente dos demais instrumentos como base.
