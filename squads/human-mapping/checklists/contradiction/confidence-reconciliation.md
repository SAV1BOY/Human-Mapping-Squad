---
type: checklist
level: layer
layer: contradiction
squad: human-mapping
version: "2.0.0"
---
# Checklist: Reconciliacao de Confianca

## Proposito
Verificar que a confianca dos resultados foi reconciliada entre camadas afetadas por contradicoes, ajustando scores de confianca de forma proporcional e transparente.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Score de confianca original de cada camada registrado antes da reconciliacao — Evidencia: `tabela de scores pre-reconciliacao por camada`
- [ ] Impacto de cada contradicao no score de confianca quantificado — Evidencia: `calculo de impacto por contradicao com formula`
- [ ] Camadas diretamente afetadas por contradicoes tiveram score ajustado — Evidencia: `tabela de ajustes com score antes e depois`
- [ ] Camadas indiretamente afetadas foram avaliadas para efeito cascata — Evidencia: `analise de efeito cascata entre camadas`
- [ ] Score de confianca global foi recalculado pos-reconciliacao — Evidencia: `score global atualizado com justificativa`
- [ ] Limiar minimo de confianca foi verificado apos ajustes — Evidencia: `comparacao score ajustado vs limiar minimo`
- [ ] Contradicoes resolvidas restauraram confianca parcial ou total — Evidencia: `registro de restauracao de confianca por resolucao`
- [ ] Contradicoes nao resolvidas mantem reducao de confianca documentada — Evidencia: `lista de reducoes permanentes com justificativa`

### Desejaveis (aumentam confianca)
- [ ] Formula de ajuste de confianca e transparente e reproduzivel
- [ ] Sensibilidade do score global a cada contradicao foi calculada
- [ ] Respondente foi informado sobre areas de menor confianca
- [ ] Plano para aumentar confianca em areas fracas foi sugerido

## Evidencia Necessaria
- Scores de confianca pre e pos-reconciliacao por camada
- Calculo de impacto por contradicao
- Analise de efeito cascata
- Score global atualizado
- Comparacao com limiar minimo
- Registro de restauracoes e reducoes permanentes

## Acao se Falhar
- Se scores nao foram ajustados: aplicar formula de impacto para cada contradicao detectada
- Se efeito cascata nao foi avaliado: rastrear dependencias entre camadas afetadas
- Se score global esta abaixo do limiar: sinalizar para re-avaliacao das camadas mais afetadas
- Se contradicoes resolvidas nao restauraram confianca: revisar se resolucao foi adequada

## Agente Responsavel
- **Agente principal**: Agente de Contradicao
- **Agentes de suporte**: Agente de Calibracao, Agente de Qualidade
- **Aprovador final**: Agente de Qualidade
