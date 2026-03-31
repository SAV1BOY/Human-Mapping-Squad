---
type: rubric
squad: human-mapping
version: "2.0.0"
---

# Trait-Type Alignment Rubric

## Proposito

Fornecer um metodo sistematico para verificar se os trait scores de um respondente
alinham com os personality types atribuidos. Desalinhamentos significativos devem ser
investigados antes de prosseguir com a sintese do perfil.

## Escala de Avaliacao

| Status | Significado | Acao |
|--------|-------------|------|
| GREEN | Traits e types totalmente alinhados | Prosseguir com confianca |
| YELLOW | Desalinhamento menor, explicavel por contexto | Documentar e prosseguir |
| ORANGE | Desalinhamento significativo que requer investigacao | Investigar antes de prosseguir |
| RED | Contradicao direta que pode invalidar dados | Parar e resolver |

## Criterios por Nivel

### GREEN: Alinhamento Completo

**Criterio**: Traits confirmam o type atribuido em todas as dimensoes relevantes.

**Exemplos de alinhamento GREEN**:
- Big Five E alto (percentil >70) + MBTI tipo E___ = GREEN
- Big Five C alto (percentil >70) + DISC C alto = GREEN
- Big Five A alto + DISC S alto = GREEN
- Big Five O alto + MBTI tipo _N__ = GREEN
- Big Five N baixo + PCM base Thinker = GREEN

### YELLOW: Desalinhamento Menor

**Criterio**: Um trait esta na zona intermediaria (percentil 40-60) enquanto o type sugere
uma direcao clara, OU o desalinhamento e explicavel por facetas especificas.

**Exemplos de desalinhamento YELLOW**:
- Big Five E percentil 50 + MBTI tipo ENFP = YELLOW (E/I borderline)
- Big Five C percentil 55 + DISC C alto = YELLOW (C moderado, nao alto)
- HEXACO Agreeableness moderado + DISC S alto = YELLOW (faceta especifica pode explicar)

**Acao**: Documentar. Verificar facetas para ver se o padrao se explica em nivel mais granular.

### ORANGE: Desalinhamento Significativo

**Criterio**: Um trait esta claramente em uma direcao (percentil >65 ou <35) enquanto o type
sugere a direcao oposta, mas ha explicacoes plausiveis.

**Exemplos de desalinhamento ORANGE**:
- Big Five E percentil 75 + MBTI tipo INTJ = ORANGE
  - Possivel: MBTI pode estar medindo preferencia cognitiva, nao sociabilidade
- Big Five A percentil 30 + DISC S alto = ORANGE
  - Possivel: S pode refletir ritmo (lento/constante), nao concordancia
- HEXACO Emotionality alto + PCM base Promoter = ORANGE
  - Possivel: Adaptacao situacional ou stress pattern

**Acao**: Investigar. Verificar contexto de aplicacao, entrevistar respondente, buscar dados adicionais.

### RED: Contradicao Direta

**Criterio**: Trait e type em oposicao extrema sem explicacao plausivel.

**Exemplos de contradicao RED**:
- Big Five E percentil 95 + MBTI tipo ISTJ com preferencia I muito clara = RED FLAG
- Big Five C percentil 10 + DISC C percentil 95 = RED FLAG
- Big Five A percentil 90 + DISC D puro (percentil 95) = RED FLAG
- Big Five N percentil 95 + PI Promoter profile = RED FLAG

**Acao**: Parar analise. Verificar se dados estao corretos, se os assessments foram aplicados
corretamente, se o respondente entendeu as questoes. Considerar reaplicacao.

## Alignment Table: Big Five <-> Types

### Extraversion

| Big Five E Score | MBTI E/I | DISC | Insights | Status |
|-----------------|----------|------|----------|--------|
| >70 percentil | E___ | D ou I alto | Red ou Yellow | GREEN |
| >70 percentil | I___ | S ou C alto | Green ou Blue | RED |
| 40-60 percentil | Qualquer | Qualquer | Qualquer | YELLOW |
| <30 percentil | I___ | S ou C alto | Green ou Blue | GREEN |
| <30 percentil | E___ | D ou I alto | Red ou Yellow | RED |

### Conscientiousness

| Big Five C Score | MBTI J/P | DISC | Status |
|-----------------|----------|------|--------|
| >70 percentil | ___J | C alto | GREEN |
| >70 percentil | ___P | D ou I alto | ORANGE |
| <30 percentil | ___P | I ou S alto | GREEN |
| <30 percentil | ___J | C alto | RED |

### Agreeableness

| Big Five A Score | DISC | SDI | Status |
|-----------------|------|-----|--------|
| >70 percentil | S alto | Blue | GREEN |
| >70 percentil | D alto | Red | RED |
| <30 percentil | D alto | Red | GREEN |
| <30 percentil | S alto | Blue (puro) | ORANGE |

### Openness to Experience

| Big Five O Score | MBTI S/N | Insights | Status |
|-----------------|----------|----------|--------|
| >70 percentil | _N__ | Yellow ou Blue | GREEN |
| >70 percentil | _S__ | Red ou Green | ORANGE |
| <30 percentil | _S__ | Red ou Green | GREEN |
| <30 percentil | _N__ | Yellow ou Blue | RED |

### Neuroticism / Emotional Stability

| Big Five N Score | PCM Base | PI Profile | Status |
|-----------------|----------|------------|--------|
| >70 percentil (alto N) | Harmonizer | Altruist | GREEN |
| >70 percentil (alto N) | Promoter | Venturer | RED |
| <30 percentil (estavel) | Thinker, Promoter | Controller | GREEN |
| <30 percentil (estavel) | Harmonizer (stress) | — | YELLOW |

## Como Aplicar

### Passo 1: Listar todos os trait scores disponiveis
Registrar cada score com sua fonte e data de aplicacao.

### Passo 2: Listar todos os types atribuidos
Registrar cada type com sua fonte e data de aplicacao.

### Passo 3: Verificar cada par trait-type na Alignment Table
Para cada combinacao, determinar o status (GREEN/YELLOW/ORANGE/RED).

### Passo 4: Consolidar resultado
- Se TODOS GREEN: Prosseguir com alta confianca
- Se algum YELLOW: Documentar e prosseguir
- Se algum ORANGE: Investigar ANTES de prosseguir com sintese
- Se algum RED: Parar e resolver ANTES de qualquer sintese

### Passo 5: Documentar
Para cada desalinhamento ORANGE ou RED, registrar:
- Quais dados estao em conflito
- Hipoteses de explicacao
- Acao tomada para resolucao
- Resolucao final (se alcancada)

## Exemplos

### Exemplo: Perfil Alinhado
- Big Five: E=75, O=80, A=60, C=45, N=30
- MBTI: ENFP
- DISC: I alto, D moderado
- **Resultado**: Todos GREEN. Alta confianca no perfil.

### Exemplo: Perfil com Red Flag
- Big Five: E=25, C=85
- MBTI: ESTP
- DISC: D alto, I alto
- **Red Flags**: E baixo + MBTI E = RED; C alto + MBTI P = ORANGE; E baixo + DISC DI = RED
- **Acao**: Verificar dados imediatamente. Possivel troca de respondente ou erro na aplicacao.

### Exemplo: Perfil com Nuances
- Big Five: E=55, A=40, C=70
- MBTI: INTJ
- DISC: C alto, D moderado
- **Status**: E borderline + MBTI I = YELLOW; C alto + MBTI J = GREEN; A moderado + D moderado = GREEN
- **Acao**: Documentar zona intermediaria de Extraversion. Perfil provavelmente confiavel.
