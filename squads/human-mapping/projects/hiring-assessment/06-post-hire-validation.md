# Fase 06: Validacao Pos-Contratacao (6 Meses)

## Objetivo

Comparar as previsoes feitas durante o assessment de contratacao com o desempenho real do profissional apos 6 meses na funcao. Esta fase fecha o loop de feedback do processo de hiring assessment, permitindo calibrar a acuracia das previsoes e melhorar assessments futuros.

## Quando Executar

- 6 meses apos a data de inicio do contratado
- Pode ser antecipado para 3 meses se houver sinais claros de desalinhamento
- Pode ser estendido para 9 meses em funcoes com ramp-up naturalmente mais longo

## Pre-Requisitos

- Hiring Assessment Report original completo (Fases 01-05)
- Acesso ao gestor direto e ao contratado para coleta de dados
- Metricas de desempenho dos primeiros 6 meses (quando disponiveis)

## Etapas

### Etapa 1: Recuperar Previsoes Originais

Listar todas as previsoes feitas no Hiring Assessment Report:

| Previsao Original | Confidence | Behavioral Prediction Card ID |
|-------------------|-----------|-------------------------------|
| ___ | ___ | ___ |

### Etapa 2: Coletar Dados Reais

**Fontes de dados:**
- Avaliacao de desempenho formal (se disponivel)
- Entrevista com gestor direto (30-45 min)
- Entrevista com o contratado (30-45 min)
- Feedback de pares (quando disponivel)
- Metricas objetivas de desempenho

**Perguntas-chave para o gestor:**
1. Como voce descreveria o desempenho geral nos primeiros 6 meses?
2. Quais foram as maiores forcas demonstradas?
3. Quais foram os maiores desafios ou surpresas?
4. O perfil descrito no assessment corresponde ao que voce observa?
5. Ha algo que o assessment NAO previu e que foi relevante?

**Perguntas-chave para o contratado:**
1. Como foi sua experiencia de adaptacao?
2. O que te energiza e o que te drena neste papel?
3. O ambiente de trabalho corresponde ao que foi discutido?
4. Quais desafios voce enfrentou que nao esperava?

### Etapa 3: Comparar Previsoes com Realidade

Para cada previsao original, documentar:

```yaml
prediction_validation:
  - prediction: "Descricao da previsao original"
    original_confidence: 0.XX
    actual_outcome: "(Confirmada / Parcialmente Confirmada / Nao Confirmada / Impossivel Avaliar)"
    evidence: "O que aconteceu na pratica"
    deviation_analysis: "Se desviou, por que?"
```

### Etapa 4: Calcular Acuracia do Assessment

```yaml
accuracy_metrics:
  total_predictions: ___
  confirmed: ___
  partially_confirmed: ___
  not_confirmed: ___
  not_evaluable: ___
  accuracy_rate: ___% (confirmadas + parciais / total avaliavel)
```

### Etapa 5: Analise de Desvios

Para previsoes nao confirmadas, investigar:

1. **Erro no assessment?** Os dados estavam errados ou foram mal interpretados?
2. **Mudanca de contexto?** O papel ou ambiente mudou desde o assessment?
3. **Fator nao mapeado?** Algo relevante nao foi capturado pelo assessment?
4. **Desenvolvimento rapido?** O contratado se desenvolveu mais rapido que o previsto?
5. **Contexto cultural?** Fatores culturais nao foram considerados adequadamente?

### Etapa 6: Feedback Loop para Melhoria

Registrar aprendizados para calibracao do processo:

```yaml
improvement_insights:
  - area: "Aspecto do assessment que funcionou bem"
    action: "Manter e replicar"
  - area: "Aspecto que falhou ou pode melhorar"
    action: "Ajustar conforme descricao"
    quality_improvement_id: "QI-___"
```

## Output

- Relatorio de validacao pos-contratacao
- Score de acuracia do assessment
- Lista de insights de melhoria (input para RalphLoop)
- Recomendacoes para o contratado (desenvolvimento adicional se necessario)

## Quality Gates

- [ ] Todas as previsoes originais foram comparadas com dados reais
- [ ] Gestor e contratado foram entrevistados
- [ ] Desvios foram analisados com causa raiz identificada
- [ ] Insights de melhoria registrados para futuras sessoes
- [ ] Confidencialidade preservada — dados de validacao nao sao usados para avaliacao de desempenho punitiva
- [ ] Feedback construtivo oferecido ao contratado

## Nota sobre Etica

A validacao pos-contratacao e uma ferramenta de CALIBRACAO DO PROCESSO, nao de julgamento do contratado. Os resultados devem ser usados para melhorar assessments futuros. Nunca usar dados de validacao para justificar desligamento ou penalizacao retroativa.
