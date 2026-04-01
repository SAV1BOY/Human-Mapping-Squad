---
type: rubric
squad: human-mapping
version: "2.0.0"
---

# Respondent Engagement Rubric

## Proposito

Estabelecer criterios para avaliar o nivel de engajamento do respondente durante o processo de assessment. O engajamento impacta diretamente a qualidade dos dados coletados e, consequentemente, a confianca de todo o mapeamento. Esta rubrica permite ajustar confidence scores e escolher estrategias de intervencao.

## Niveis de Engajamento

### Nivel 1: DESENGAJADO (Low Engagement)

**Sinais observaveis:**
- Respostas monossilabicas ou genericas em entrevistas
- Tempo de resposta em assessments muito abaixo da media (indica cliques aleatorios)
- Nao faz perguntas sobre o processo ou resultados
- Postura corporal/tom de voz indicam desinteresse (em sessoes presenciais ou por video)
- Respostas com alto indice de "tanto faz" ou "nao sei" em perguntas de preferencia
- Cancelamentos e reagendamentos frequentes

**Impacto na qualidade dos dados:**
- Dados de self-report nao confiaveis — podem refletir desinteresse, nao personalidade
- Assessments formais podem ter validade comprometida por respostas aleatorias
- Confidence score maximo permitido: 0.50 (independente de outros fatores)

**Acoes recomendadas:**
- Pausar o assessment e investigar a causa do desengajamento
- Verificar se o respondente entende o proposito e os beneficios do processo
- Confirmar se a participacao e voluntaria — assessments obrigatorios geram resistencia
- Ajustar o formato: trocar questionario longo por entrevista conversacional
- Se o desengajamento persistir, documentar e reportar — dados forçados sao piores que dados ausentes

### Nivel 2: COOPERATIVO (Medium Engagement)

**Sinais observaveis:**
- Responde todas as perguntas de forma adequada mas sem elaboracao espontanea
- Completa assessments dentro do tempo esperado
- Faz poucas perguntas mas responde bem quando questionado
- Postura neutra — nem entusiasmado nem resistente
- Cumpre prazos mas nao antecipa entregas

**Impacto na qualidade dos dados:**
- Dados confiaveis para o que foi perguntado diretamente
- Pode faltar profundidade em areas que dependem de elaboracao espontanea
- Confidence score pode alcancar ate 0.80 (limitado pela falta de profundidade)

**Acoes recomendadas:**
- Aceitar como baseline adequado — nem todo respondente precisa ser entusiasmado
- Usar perguntas mais especificas e direcionadas em vez de abertas
- Complementar self-report com dados observacionais e de terceiros quando possivel
- Documentar o nivel de engajamento para contextualizar interpretacoes

### Nivel 3: PROFUNDAMENTE ENGAJADO (High Engagement)

**Sinais observaveis:**
- Elabora respostas espontaneamente com exemplos e reflexoes
- Faz perguntas sobre os frameworks e o processo
- Demonstra curiosidade genuina sobre os proprios resultados
- Completa assessments com cuidado — tempo dentro ou acima da media
- Conecta resultados a experiencias vividas sem ser solicitado
- Traz insights proprios que enriquecem a analise

**Impacto na qualidade dos dados:**
- Dados de alta qualidade com profundidade e contexto
- Self-report confiavel e rico em nuances
- Confidence score pode alcancar ate 0.95 (teto do sistema)

**Acoes recomendadas:**
- Aproveitar a abertura para aprofundar areas criticas
- Usar a devolutiva como sessao de co-construcao do perfil
- Registrar insights espontaneos do respondente como dados adicionais
- Cuidado: engajamento alto pode incluir desejabilidade social — validar com dados comportamentais

## Como Avaliar

### Passo 1: Observar durante cada interacao
Registrar sinais de engajamento em cada sessao, assessment e comunicacao.

### Passo 2: Classificar por sessao
Cada interacao recebe um nivel (1, 2 ou 3). O nivel geral e a moda das sessoes.

### Passo 3: Ajustar confidence scores
Aplicar o teto de confidence correspondente ao nivel de engajamento.

### Passo 4: Documentar no Layer Summary Card
Incluir o campo `respondent_engagement` em cada Layer Summary Card.

## Notas Importantes

- Engajamento pode variar entre camadas — o respondente pode estar altamente engajado em Strengths e desengajado em Motivation
- Desengajamento nao e defeito do respondente — pode indicar processo inadequado, falta de trust ou contexto organizacional toxico
- Nunca usar engajamento baixo para invalidar dados sem investigar a causa
- No contexto brasileiro, engajamento social alto pode mascarar desengajamento real — a pessoa sorri e concorda mas nao se aprofunda
