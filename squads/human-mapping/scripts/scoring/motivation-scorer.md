---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Motivation Scorer

## Propósito

Calcular o perfil motivacional do respondente, gerando um ranking hierárquico de motivadores intrínsecos e extrínsecos com scores de intensidade e confiança.

## Input

- `motivation-responses`: Respostas às perguntas de motivação
- `ranking-data`: Dados do ranking forçado de motivadores
- `scenario-responses`: Respostas aos cenários situacionais
- `trait-scores`: Scores OCEAN para cruzamento
- `type-result`: Tipo inferido para cruzamento

## Processo (step by step algorithm)

1. **Scoring direto de motivadores**
   - Para cada motivador (Autonomia, Maestria, Propósito, Pertencimento, Reconhecimento, Segurança, Crescimento):
     - Calcular score base a partir das respostas diretas (0-100)
     - Aplicar peso das perguntas conforme relevância

2. **Incorporar dados do ranking forçado**
   - Converter ranking em scores relativos:
     - Posição 1: +30 pontos de bônus
     - Posição 2: +20 pontos
     - Posição 3: +10 pontos
     - Últimas posições: -10 a -20 pontos
   - Combinar com score direto (peso: 40% ranking, 60% respostas)

3. **Validar com cenários situacionais**
   - Para cada cenário, identificar qual motivador a escolha revela
   - Comparar motivador revelado com ranking declarado
   - Se consistente: aumentar confiança (+10%)
   - Se inconsistente: reduzir confiança (-15%) e investigar

4. **Cruzamento com personalidade e tipo**
   - Verificar coerência com padrões esperados:
     - ENTP/INTP: tipicamente alta Autonomia e Maestria
     - ESFJ/ENFJ: tipicamente alto Pertencimento e Propósito
     - Alta Conscienciosidade: tipicamente alta Maestria e Segurança
   - Desvios do esperado não são erros, mas devem ser notados

5. **Separar motivadores intrínsecos e extrínsecos**
   - Intrínsecos: Autonomia, Maestria, Propósito, Crescimento
   - Extrínsecos: Reconhecimento, Segurança, Pertencimento
   - Gerar ranking separado para cada categoria

6. **Identificar desmotivadores**
   - Desmotivadores = inverso dos motivadores mais baixos
   - Ex: Autonomia no topo -> Microgerenciamento é desmotivador
   - Ex: Segurança no topo -> Instabilidade é desmotivador

7. **Gerar perfil motivacional completo**
   - Ranking final com scores
   - Top 3 intrínsecos e top 3 extrínsecos
   - Desmotivadores mapeados
   - Nível de confiança por motivador

## Output

- `motivation-ranking`: Ranking completo de motivadores com scores
- `intrinsic-top3`: Top 3 motivadores intrínsecos
- `extrinsic-top3`: Top 3 motivadores extrínsecos
- `demotivators`: Lista de desmotivadores com intensidade
- `motivation-confidence`: Confiança por motivador

## Uso

Chamado por `tasks/assessment/run-motivation-layer.md` após a coleta das respostas de motivação.
