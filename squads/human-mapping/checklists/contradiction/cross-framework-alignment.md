---
type: checklist
level: layer
layer: contradiction
squad: human-mapping
version: "2.0.0"
---
# Checklist: Alinhamento Entre Frameworks

## Proposito
Verificar que o alinhamento entre todos os frameworks utilizados foi verificado sistematicamente, identificando concordancias e discordancias de forma estruturada.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Matriz de alinhamento entre todos os frameworks foi construida — Evidencia: `matriz NxN com grau de alinhamento por par de frameworks`
- [ ] Cada par de frameworks foi comparado em dimensoes equivalentes — Evidencia: `tabela de dimensoes equivalentes por par`
- [ ] Alinhamentos fortes (concordancia > 80%) documentados — Evidencia: `lista de alinhamentos fortes com evidencia`
- [ ] Desalinhamentos significativos (concordancia < 50%) sinalizados — Evidencia: `lista de desalinhamentos com magnitude`
- [ ] Causa provavel de cada desalinhamento foi investigada — Evidencia: `analise causal por desalinhamento`
- [ ] Score de alinhamento global calculado — Evidencia: `score numerico de alinhamento global`
- [ ] Frameworks com menor alinhamento ao conjunto foram identificados — Evidencia: `ranking de frameworks por alinhamento medio`
- [ ] Decisao sobre como tratar desalinhamentos foi registrada — Evidencia: `registro de decisao por desalinhamento`

### Desejaveis (aumentam confianca)
- [ ] Peso diferenciado foi dado a frameworks mais confiaveis para o respondente
- [ ] Padroes sistematicos de desalinhamento foram buscados
- [ ] Respondente foi consultado sobre desalinhamentos relevantes
- [ ] Historico de consistencia do respondente foi considerado

## Evidencia Necessaria
- Matriz de alinhamento NxN completa
- Tabela de dimensoes equivalentes entre frameworks
- Lista de alinhamentos e desalinhamentos com magnitude
- Analise causal de desalinhamentos
- Score de alinhamento global
- Registro de decisoes sobre desalinhamentos

## Acao se Falhar
- Se matriz nao foi construida: construir matriz sistematica antes de qualquer conclusao
- Se desalinhamentos nao foram investigados: aplicar analise causal para cada desalinhamento > 30%
- Se score global e baixo: reduzir confianca geral do perfil e sinalizar para revisao
- Se causa nao foi identificada: considerar re-aplicacao do framework menos confiavel

## Agente Responsavel
- **Agente principal**: Agente de Contradicao
- **Agentes de suporte**: Agente de Cross-Framework, Agente de Calibracao
- **Aprovador final**: Agente de Qualidade
