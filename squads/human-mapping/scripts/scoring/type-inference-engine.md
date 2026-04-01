---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Type Inference Engine

## Propósito

Inferir o tipo psicológico do respondente (MBTI/Jung) a partir das respostas coletadas e dos dados de traços, utilizando um algoritmo probabilístico que considera múltiplas fontes de evidência.

## Input

- `type-responses`: Respostas às perguntas tipológicas
- `trait-scores`: Scores OCEAN já calculados (para cruzamento)
- `behavioral-data`: Dados comportamentais coletados (tempo de resposta, estilo de comunicação)
- `depth-mode`: Modo de profundidade da sessão

## Processo (step by step algorithm)

1. **Scoring direto por eixo**
   - Para cada eixo de preferência, calcular score a partir das respostas diretas:
     - E/I: Somar respostas pró-extroversão vs pró-introversão
     - S/N: Somar respostas pró-sensação vs pró-intuição
     - T/F: Somar respostas pró-pensamento vs pró-sentimento
     - J/P: Somar respostas pró-julgamento vs pró-percepção
   - Resultado: score de -100 a +100 por eixo (negativo = primeiro polo, positivo = segundo)

2. **Cruzamento com dados de traços (evidência secundária)**
   - E/I: Correlacionar com Extroversão OCEAN (correlação esperada ~0.7)
   - S/N: Correlacionar com Abertura OCEAN (N correlaciona com alta Abertura)
   - T/F: Correlacionar com Amabilidade OCEAN (F correlaciona com alta Amabilidade)
   - J/P: Correlacionar com Conscienciosidade OCEAN (J correlaciona com alta Conscienciosidade)

3. **Cruzamento com dados comportamentais (evidência terciária)**
   - Tempo de resposta longo + respostas reflexivas -> indicador de I e/ou N
   - Respostas concretas e específicas -> indicador de S
   - Respostas estruturadas e organizadas -> indicador de J

4. **Calcular probabilidade por tipo**
   - Combinar as três fontes com pesos:
     - Respostas diretas: 60%
     - Cruzamento com traços: 25%
     - Dados comportamentais: 15%
   - Calcular score final por eixo

5. **Determinar tipo e clareza de preferência**
   - Tipo = combinação dos polos dominantes em cada eixo
   - Clareza = |score| por eixo (quão forte é a preferência)
   - Clareza < 15: preferência marginal (baixa confiança nesse eixo)
   - Clareza 15-40: preferência moderada
   - Clareza > 40: preferência clara

6. **Identificar funções cognitivas**
   - Derivar stack de funções a partir do tipo inferido
   - Função dominante e auxiliar (alta confiança)
   - Função terciária e inferior (confiança moderada)

7. **Validar consistência interna**
   - Verificar se o tipo inferido é consistente com o perfil geral
   - Sinalizar inconsistências com nota explicativa

## Output

- `inferred-type`: Tipo inferido (ex: INTJ, ENFP)
- `axis-scores`: Scores por eixo (-100 a +100)
- `preference-clarity`: Clareza de preferência por eixo
- `cognitive-functions`: Stack de funções cognitivas
- `type-probability`: Probabilidade do tipo inferido vs alternativas
- `consistency-notes`: Notas sobre consistência com outros dados

## Uso

Chamado por `tasks/assessment/run-type-style-layer.md` para inferir o tipo do respondente.

## Especificação de I/O

### Input
- Formato: YAML/JSON
- Campos obrigatórios: `type-responses`, `trait-scores`, `behavioral-data`, `depth-mode`
- Exemplo: `{type-responses: [{axis: "E/I", answer: "E", weight: 0.8}], trait-scores: {O: 72, C: 65, E: 45, A: 58, N: 38}}`

### Output
- Formato: YAML
- Campos: `inferred-type`, `axis-scores`, `preference-clarity`, `cognitive-functions`, `type-probability`, `consistency-notes`

### Thresholds
- axis_score_range: [-100, +100]
- marginal_preference: 15 (clareza < 15 = preferência marginal)
- moderate_preference: 40 (clareza 15-40 = moderada)
- source_weights: {direct: 0.60, traits: 0.25, behavioral: 0.15}

### Tratamento de Erros
- Input inválido: retornar erro `INVALID_TYPE_RESPONSES`
- Dados insuficientes: inferir com fontes disponíveis e marcar eixos sem dados como `indeterminate`
