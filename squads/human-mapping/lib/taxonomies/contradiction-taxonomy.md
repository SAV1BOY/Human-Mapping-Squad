---
type: taxonomy
squad: human-mapping
version: "2.0.0"
---

# Contradiction Taxonomy

## Proposito

Classificar, categorizar e priorizar contradicoes encontradas durante a analise de perfil
no Human Mapping Squad. Nem toda contradicao e um erro — muitas revelam complexidade
genuina da pessoa. Esta taxonomia distingue contradicoes que indicam dados problematicos
daquelas que indicam riqueza do perfil.

## Categorias

### 1. Trait-Type Contradictions
Quando um trait score contradiz o tipo atribuido.

**Exemplos**:
- Big Five Extraversion no percentil 90 + MBTI tipo INFP
- Big Five Agreeableness no percentil 15 + DISC estilo S alto
- HEXACO Honesty-Humility alto + Enneagram tipo 3 (image-focused)

**Causas possiveis**: Instrumento diferente mede contexto diferente, respondente em transicao,
auto-percepcao vs comportamento observado, maturidade do tipo.

### 2. Motivation-Style Contradictions
Quando a motivacao declarada ou avaliada contradiz o estilo comportamental.

**Exemplos**:
- Enneagram tipo 5 (autonomia) + DISC estilo I alto (sociabilidade constante)
- SDI Blue (altruismo) + MVPI Power alto
- Reiss Independence alto + Birkman Green (necessidade de aprovacao)

**Causas possiveis**: Motivacao compensatoria, adaptacao ao ambiente, diferenca entre
desejo e comportamento, desenvolvimento pessoal recente.

### 3. Strength-Role Contradictions
Quando strengths avaliadas nao alinham com o papel que a pessoa assume ou deseja.

**Exemplos**:
- Top 5 CliftonStrengths todos em Strategic Thinking + Belbin Shaper (Action-Oriented)
- VIA Top Strength = Prudence + papel de Resource Investigator
- Nenhuma strength em Relationship Building + papel de lideranca people-centric

**Causas possiveis**: Papel imposto vs escolhido, compensacao consciente, contexto
organizacional, skill desenvolvida sem strength subjacente.

### 4. Intra-Framework Contradictions
Quando dados DENTRO do mesmo framework sao inconsistentes.

**Exemplos**:
- MBTI funcoes cognitivas inconsistentes com as 4 letras reportadas
- CliftonStrengths: Deliberative (#1) e Activator (#3) no mesmo Top 5
- Enneagram tipo principal e wing do mesmo triad (tecnicamente possivel mas raro)
- DISC: D e S ambos no percentil 90 (opostos naturais)

**Causas possiveis**: Respondente inconsistente, momento de transicao, complexidade
genuina, instrumento mal aplicado, efeito Barnum no self-report.

### 5. Adaptation-Identity Contradictions
Quando o perfil "adaptado" ou "under stress" contradiz fortemente o perfil base.

**Exemplos**:
- Birkman usual behavior (Red) vs underlying need (Blue)
- PCM base type (Thinker) vs stress sequence (Harmonizer behaviors)
- SDI motivacao em conflito completamente oposta a motivacao em flow

**Causas possiveis**: Estas sao frequentemente ESPERADAS e representam a teoria do
framework. A contradicao e informativa, nao problematica.

## Severity Levels

### Level 1: Low (Informativa)
- **Descricao**: Contradicao entre facetas ou subdimensoes, nao entre construtos principais
- **Exemplo**: Big Five Extraversion Warmth alto mas Gregariousness baixo
- **Acao**: Documentar como nuance do perfil. Enriquece a narrativa.
- **Impacto no confidence score**: Nenhum

### Level 2: Medium (Requer Investigacao)
- **Descricao**: Contradicao parcial entre construtos de frameworks diferentes
- **Exemplo**: DISC I moderado + MBTI leve preferencia por Introversion
- **Acao**: Investigar contexto. Pode ser adaptacao situacional ou zona intermediaria.
- **Impacto no confidence score**: Reduz 0.1 ate ser resolvida

### Level 3: High (Conflito Direto)
- **Descricao**: Oposicao clara entre dados de frameworks diferentes
- **Exemplo**: Big Five Extraversion percentil 95 + MBTI I forte + DISC S puro
- **Acao**: Verificar qualidade dos dados. Entrevistar respondente. Pode invalidar um resultado.
- **Impacto no confidence score**: Reduz 0.2-0.3

### Level 4: Critical (Potencialmente Invalidante)
- **Descricao**: Contradicao que questiona a validade de um ou mais assessments
- **Exemplo**: Todos os assessments apontam direcoes radicalmente diferentes sem padrao
- **Acao**: Parar analise. Verificar se dados estao corretos. Considerar reaplicacao.
- **Impacto no confidence score**: Reduz para < 0.4 automaticamente

## Resolution Approaches

### Para Cada Severity Level

| Level | Approach | Tempo Estimado |
|-------|----------|---------------|
| Low | Incorporar como nuance na narrativa | 5 min |
| Medium | Investigar contexto, buscar terceira fonte de dados | 15 min |
| High | Entrevista de clarificacao com respondente | 30 min |
| Critical | Revisao completa dos dados, possivel reaplicacao | 60+ min |

### Estrategias de Resolucao
1. **Contextualizacao**: A contradicao desaparece quando consideramos contextos diferentes?
2. **Priorizacao de Fonte**: Qual instrumento tem maior validade para este construto?
3. **Triangulacao**: Ha uma terceira fonte de dados que desempata?
4. **Entrevista**: Perguntar diretamente ao respondente sobre a discrepancia
5. **Aceitacao**: Algumas contradicoes refletem complexidade real e devem ser mantidas

## Definicoes

| Termo | Definicao Operacional |
|-------|----------------------|
| Contradiction | Dados de dois ou mais construtos que apontam direcoes opostas |
| Nuance | Aparente contradicao que, com contexto, revela complexidade legitima |
| Invalidation | Contradicao tao severa que questiona a validade dos dados |
| Resolution | Processo de investigar e explicar uma contradicao |
| Convergence | Quando multiplas fontes apontam na mesma direcao (oposto de contradicao) |

## Uso no Pipeline

### Na Analise
- Executar checagem sistematica usando as 5 categorias de contradicao
- Classificar cada contradicao encontrada pelo severity level
- Documentar todas as contradicoes, mesmo as de Level 1

### Na Sintese
- Contradicoes Level 1-2: integrar na narrativa como complexidade do perfil
- Contradicoes Level 3: destacar explicitamente com nota de cautela
- Contradicoes Level 4: bloquear report ate resolucao

### No Report
- Transparencia: reportar contradicoes encontradas e como foram tratadas
- Nunca ignorar ou esconder contradicoes significativas
- Usar contradicoes como evidencia de profundidade analitica
