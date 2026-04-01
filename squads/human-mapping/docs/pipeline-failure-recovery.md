# Recuperacao de Falhas no Pipeline

## Proposito

O pipeline de assessment tem multiplos estagios, e cada um pode falhar.
Este documento define protocolos de recuperacao para cada tipo de falha,
quando tentar novamente e quando abortar o processo.

## Estagios do Pipeline e Modos de Falha

### Estagio 1 — Coleta de Dados

**Falhas possiveis**:
- Respondente abandona o questionario no meio
- Conexao de internet interrompida durante assessment online
- Dados corrompidos ou incompletos

**Protocolo de recuperacao**:
- Se completude > 70%: usar dados parciais com flag de incompletude
- Se completude < 70%: reagendar sessao dentro de 7 dias
- Dados corrompidos: descartar e reagendar completamente
- Maximo de 2 tentativas antes de abortar

### Estagio 2 — Validacao de Qualidade

**Falhas possiveis**:
- Tempo de resposta abaixo do minimo (respondente clicou sem ler)
- Padroes de resposta invalidos (todas iguais, padrao alternado)
- Indice de desejabilidade social acima do limiar critico

**Protocolo de recuperacao**:
- Tempo rapido demais: invalidar e reaplicar com instrucoes reforaçadas
- Padrao invalido: conversa com respondente para entender motivo
- Desejabilidade social alta: complementar com metodo alternativo (entrevista)
- Se segunda tentativa tambem falhar: abortar e documentar motivo

### Estagio 3 — Scoring e Calculo

**Falhas possiveis**:
- Erro no algoritmo de scoring
- Score fora do range possivel (bug)
- Inconsistencia entre frameworks (contradicao nao resolvivel)

**Protocolo de recuperacao**:
- Erro de scoring: recalcular manualmente e reportar bug
- Score impossivel: invalidar framework especifico, manter os demais
- Contradicao critica: escalar para revisao de especialista senior
- Nunca forcar resolucao de contradicao — documentar e sinalizar

### Estagio 4 — Interpretacao e Narrativa

**Falhas possiveis**:
- Perfil nao se encaixa em nenhum padrao conhecido
- Interpretacao contradiz observacao direta do avaliador
- Avaliado contesta fortemente a interpretacao

**Protocolo de recuperacao**:
- Perfil atipico: documentar como caso especial, nao forcar categoria
- Contradicao com observacao: priorizar dados + observacao sobre framework
- Contestacao do avaliado: session de validacao colaborativa
- Se contestacao persistir: incluir perspectiva do avaliado no relatorio

### Estagio 5 — Entrega e Devolutiva

**Falhas possiveis**:
- Avaliado nao comparece a devolutiva
- Reacao emocional intensa durante devolutiva
- Stakeholder usa dados de forma inadequada

**Protocolo de recuperacao**:
- No-show: reagendar em ate 14 dias; apos 2 no-shows, enviar relatorio escrito
- Reacao emocional: pausar, acolher, oferecer continuacao em outra data
- Uso inadequado: intervir imediatamente, reforcar contrato de uso etico

## Criterios para Abortar vs Tentar Novamente

### Abortar Quando
- Respondente explicitamente recusa continuar
- Dados estao comprometidos de forma irrecuperavel
- Contexto politico torna o assessment manipulado ou inseguro
- Terceira tentativa de coleta falhou

### Tentar Novamente Quando
- Falha foi tecnica (conexao, bug) e dados podem ser recuperados
- Respondente quer continuar mas precisa de ajuste de abordagem
- Qualidade pode ser melhorada com instrumento complementar
- Primeira tentativa, sem sinais de resistencia ativa

## Documentacao de Falhas

Toda falha deve ser registrada com:
- Estagio onde ocorreu
- Tipo de falha
- Acao tomada (retry, abort, escalacao)
- Resultado da acao
- Licoes aprendidas para prevencao futura

## Metricas de Saude do Pipeline

- Taxa de completude por estagio (meta: > 85%)
- Taxa de retry por estagio (alerta se > 15%)
- Tempo medio de recuperacao por tipo de falha
- Taxa de abort (alerta se > 5% do total de assessments)
