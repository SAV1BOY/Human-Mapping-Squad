---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Response Quality Checker

## Propósito

Verificar a qualidade das respostas do respondente em tempo real durante o assessment, detectando respostas de baixa qualidade, padrões suspeitos e desengajamento para garantir dados confiáveis.

## Input

- `response`: Resposta atual do respondente (texto ou seleção)
- `question`: Pergunta que gerou a resposta
- `session-context`: Contexto acumulado da sessão (respostas anteriores, timing)
- `calibration-data`: Dados de calibração do respondente

## Processo (step by step algorithm)

1. **Verificar comprimento mínimo da resposta**
   - Para perguntas abertas: mínimo 20 caracteres
   - Para perguntas de múltipla escolha: resposta selecionada
   - Para rankings: ranking completo (sem itens faltando)
   - Se abaixo do mínimo, gerar flag `too-short`

2. **Verificar relevância da resposta**
   - Comparar semanticamente a resposta com a pergunta
   - Detectar respostas genéricas ou evasivas:
     - "Não sei", "Depende", "Normal", "Tanto faz"
   - Se irrelevante, gerar flag `off-topic` ou `evasive`

3. **Detectar padrões de resposta suspeitos**
   - Padrão de aquiescência: >70% das respostas concordando/positivas
   - Padrão de oposição: >70% das respostas discordando/negativas
   - Padrão alternado: respostas alternando sistematicamente (sim/não/sim/não)
   - Padrão central: todas as respostas no meio da escala
   - Se detectado, gerar flag `suspicious-pattern` com tipo

4. **Verificar consistência com calibração**
   - Comparar estilo de resposta com padrão de calibração
   - Mudança abrupta na velocidade ou profundidade indica desengajamento
   - Se desvio > 2 desvios-padrão, gerar flag `engagement-drop`

5. **Calcular score de qualidade da resposta** (0-100)
   - Comprimento adequado: +25 pontos
   - Relevância: +30 pontos
   - Ausência de padrão suspeito: +25 pontos
   - Consistência com calibração: +20 pontos

6. **Decidir ação baseada no score**
   - Score >= 70: Aceitar resposta normalmente
   - Score 40-69: Aceitar com flag de cautela, considerar pergunta de follow-up
   - Score < 40: Solicitar reformulação ou aprofundamento

7. **Atualizar métricas acumuladas**
   - Média móvel de qualidade das últimas 5 respostas
   - Se média cair abaixo de 50, sugerir pausa ou encerramento

## Output

- `quality-score`: Score de qualidade da resposta (0-100)
- `flags`: Lista de flags geradas (se houver)
- `action`: Ação recomendada (accept, flag, request-rephrase)
- `cumulative-quality`: Qualidade média acumulada da sessão

## Uso

Chamado automaticamente após cada resposta do respondente durante qualquer camada de assessment. Integrado com todos os tasks de `tasks/assessment/`.

## Especificação de I/O

### Input
- Formato: YAML/JSON
- Campos obrigatórios: `response`, `question`, `session-context`, `calibration-data`
- Exemplo: `{response: "Eu prefiro trabalhar em equipe...", question: {id: "T-01", type: "open"}, session-context: {previous_quality_avg: 75}}`

### Output
- Formato: YAML
- Campos: `quality-score`, `flags`, `action`, `cumulative-quality`

### Thresholds
- min_chars_open: 20 (mínimo para perguntas abertas)
- accept_threshold: 70 (score >= 70 aceita normalmente)
- rephrase_threshold: 40 (score < 40 solicita reformulação)
- acquiescence_limit: 0.70 (> 70% concordância = padrão suspeito)
- engagement_drop_std: 2.0 (desvios-padrão para flag de desengajamento)

### Tratamento de Erros
- Input inválido: retornar quality-score = 0 e flag `invalid-input`
- Dados insuficientes: aceitar resposta com flag `insufficient-context` e quality = 50
