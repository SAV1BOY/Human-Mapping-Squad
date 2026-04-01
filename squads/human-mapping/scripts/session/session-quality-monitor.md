# Monitor de Qualidade da Sessao

## Proposito

Monitorar a qualidade da sessao de assessment em tempo real,
identificando indicadores de engajamento, consistencia e fadiga
para ajustar o processo dinamicamente.

## Indicadores Monitorados

### 1. Engajamento

**Indicadores Positivos:**
- Elaboracao crescente nas respostas
- Perguntas espontaneas do avaliado
- Linguagem corporal aberta e orientada
- Contato visual adequado
- Expressoes de insight ("nunca pensei nisso")

**Indicadores Negativos:**
- Respostas cada vez mais curtas
- Olhar frequente para celular ou relogio
- Postura reclinada ou distante
- Respostas genericas ou evasivas
- Suspiros ou sinais de impaciencia

### 2. Consistencia

**Como Verificar:**
- Comparar respostas sobre temas similares em momentos diferentes
- Checar alinhamento entre auto-relato e comportamento observado
- Notar se exemplos dados sao coerentes com perfil emergente
- Monitorar discrepancias entre o que diz e como diz

**Bandeiras Vermelhas:**
- Contradicao direta sem consciencia
- Respostas que mudam conforme framing da pergunta
- Desejabilidade social extrema (tudo e positivo)
- Respostas padronizadas ou ensaiadas

### 3. Fadiga

**Sinais Precoces (agir preventivamente):**
- Diminuicao gradual do tempo de reflexao antes de responder
- Bocejos ou esfregamento dos olhos
- Respostas repetitivas ou com menos variacao
- Postura cada vez mais relaxada/curvada

**Sinais Avancados (intervir imediatamente):**
- Respostas monossilabicas apos periodo de elaboracao
- Pedidos para "pular" ou "acelerar"
- Irritabilidade com perguntas aprofundadas
- Desconexao visivel (olhar perdido)

## Protocolo de Intervencao

### Engajamento Baixo
1. Mudar tipo de atividade (questionario → conversa → exercicio)
2. Aumentar relevancia pessoal das perguntas
3. Compartilhar insight preliminar para gerar curiosidade
4. Verificar se algo externo esta interferindo

### Consistencia Baixa
1. Nao confrontar diretamente — explorar com curiosidade
2. "Antes voce mencionou X, e agora Y — como essas coisas se conectam?"
3. Considerar que ambas as respostas podem ser verdadeiras em contextos diferentes
4. Documentar a inconsistencia para analise posterior

### Fadiga Detectada
1. Oferecer pausa de 5-10 minutos
2. Se apos pausa continuar, encerrar e reagendar
3. Priorizar dimensoes ainda nao cobertas
4. Reduzir profundidade em favor de cobertura

## Registro

Anotar a cada 20 minutos:
- Nivel de engajamento (1-5)
- Consistencia percebida (alta/media/baixa)
- Fadiga (nenhuma/leve/moderada/severa)
- Intervencoes realizadas e efeito observado

## Especificacao de I/O

### Input
- Formato: YAML
- Campos obrigatorios: `session-id`, `elapsed-time`, `response-history`, `calibration-baseline`
- Exemplo: `{session-id: "HMS-20260401-0001", elapsed-time: 20, response-history: [{id: 1, length: 45, time: 12s}]}`

### Output
- Formato: YAML
- Campos: `engagement-score` (1-5), `consistency-level`, `fatigue-level`, `interventions-log`

### Thresholds
- check_interval_minutes: 20
- engagement_critical: 2 (intervir se <= 2)
- fatigue_pause_trigger: "moderada" (oferecer pausa)
- fatigue_stop_trigger: "severa" (encerrar e reagendar)
- cumulative_quality_floor: 50 (sugerir pausa se media < 50)

### Tratamento de Erros
- Input invalido: logar warning e continuar com monitoramento parcial
- Dados insuficientes: usar apenas indicadores disponiveis e flag `partial-monitoring`
