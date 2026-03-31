---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: mandatory
---
# Checklist: Qualidade da Sessao Completa

## Proposito
Verificar que a sessao de mapeamento humano foi conduzida do inicio ao fim com todas as etapas obrigatorias cumpridas, garantindo integridade e confiabilidade do resultado final.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Intake foi realizado e registrado antes do inicio da sessao — Evidencia: `registro de intake com timestamp`
- [ ] Calibracao do respondente foi aprovada conforme checklist de calibracao — Evidencia: `resultado da calibracao com status aprovado`
- [ ] Todas as camadas de avaliacao definidas no escopo foram completadas — Evidencia: `lista de camadas com status de conclusao`
- [ ] Nenhuma camada foi ignorada ou parcialmente preenchida sem justificativa — Evidencia: `log de completude por camada`
- [ ] Auditoria de contradicoes foi executada sobre os resultados — Evidencia: `relatorio de auditoria de contradicoes`
- [ ] Contradicoes identificadas foram classificadas e reconciliadas — Evidencia: `registro de reconciliacao`
- [ ] Relatorio final foi gerado com score de confianca por camada — Evidencia: `relatorio com mapa de confianca`
- [ ] Score de confianca global da sessao atinge o limiar minimo definido — Evidencia: `score >= limiar configurado`
- [ ] Tempo total da sessao esta dentro do intervalo aceitavel — Evidencia: `timestamp inicio e fim`
- [ ] Dados brutos da sessao foram preservados para auditoria futura — Evidencia: `artefatos brutos arquivados`

### Desejaveis (aumentam confianca)
- [ ] Respondente confirmou que se sentiu confortavel durante a sessao
- [ ] Nenhum indicador de fadiga severa foi detectado nas respostas finais
- [ ] Sessao foi conduzida sem interrupcoes significativas
- [ ] Feedback qualitativo do respondente foi coletado ao final
- [ ] Revisao por pares do relatorio foi realizada

## Evidencia Necessaria
- Registro completo de intake com objetivo, contexto e escopo
- Resultado da calibracao com metricas de consistencia
- Status de conclusao de cada camada avaliada
- Relatorio de auditoria de contradicoes com classificacao
- Relatorio final com scores de confianca por camada e global
- Timestamps de inicio e fim da sessao
- Artefatos brutos arquivados

## Acao se Falhar
- Se intake nao foi feito: sessao deve ser reiniciada desde o intake
- Se calibracao falhou: respondente deve ser recalibrado antes de prosseguir
- Se camadas estao incompletas: completar as camadas faltantes ou justificar exclusao
- Se contradicoes nao foram auditadas: executar auditoria antes de gerar relatorio
- Se confianca esta abaixo do limiar: investigar camadas com baixa confianca e considerar re-avaliacao
- Se dados brutos nao foram preservados: reconstruir a partir dos artefatos disponiveis

## Agente Responsavel
- **Agente principal**: Orquestrador de Sessao
- **Agentes de suporte**: Agente de Calibracao, Agente de Auditoria, Agente de Sintese
- **Aprovador final**: Agente de Qualidade
