---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: mandatory
---
# Checklist: Qualidade da Calibracao

## Proposito
Assegurar que o respondente foi devidamente calibrado antes das avaliacoes, verificando consistencia, desejabilidade social, fadiga e estabelecendo baseline de confianca para toda a sessao.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Teste de consistencia foi aplicado e resultado esta dentro do limiar aceitavel — Evidencia: `score de consistencia >= limiar`
- [ ] Perguntas de verificacao cruzada foram respondidas de forma coerente — Evidencia: `delta entre respostas cruzadas < margem`
- [ ] Indicador de desejabilidade social foi avaliado — Evidencia: `score de desejabilidade social calculado`
- [ ] Nivel de desejabilidade social nao compromete a validade das respostas — Evidencia: `score abaixo do limiar critico`
- [ ] Indicadores de fadiga foram medidos no inicio da sessao — Evidencia: `baseline de fadiga registrado`
- [ ] Fadiga inicial nao compromete a capacidade de resposta — Evidencia: `indicador de fadiga dentro do aceitavel`
- [ ] Baseline de confianca foi estabelecido para a sessao — Evidencia: `baseline registrado com metricas`
- [ ] Tempo de resposta medio esta dentro do intervalo esperado — Evidencia: `media de tempo por resposta calculada`
- [ ] Respondente demonstrou compreensao das instrucoes — Evidencia: `respostas de teste coerentes`

### Desejaveis (aumentam confianca)
- [ ] Respondente nao apresentou padrao de aquiescencia (concordancia automatica)
- [ ] Variabilidade nas respostas indica engajamento genuino
- [ ] Respondente reportou estar em estado adequado para a sessao
- [ ] Calibracao foi feita em ambiente controlado e sem distracoes
- [ ] Nenhuma resposta extrema sistematica foi detectada

## Evidencia Necessaria
- Score de consistencia com limiar utilizado
- Resultado da verificacao cruzada com deltas calculados
- Score de desejabilidade social com classificacao
- Baseline de fadiga com indicadores utilizados
- Baseline de confianca com metricas compostas
- Media de tempo de resposta com desvio padrao
- Registro de compreensao das instrucoes

## Acao se Falhar
- Se consistencia esta baixa: repetir calibracao com instrucoes mais claras
- Se desejabilidade social esta alta: aplicar correcao nos resultados ou alertar no relatorio
- Se fadiga esta comprometendo: adiar sessao ou permitir pausa antes de continuar
- Se baseline de confianca esta abaixo do minimo: avaliar se a sessao deve prosseguir
- Se tempo de resposta esta anomalo: investigar causa e considerar recalibracao
- Sessao nao deve prosseguir sem calibracao aprovada

## Agente Responsavel
- **Agente principal**: Agente de Calibracao
- **Agentes de suporte**: Orquestrador de Sessao
- **Aprovador final**: Agente de Qualidade
