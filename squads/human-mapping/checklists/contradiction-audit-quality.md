---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: mandatory
---
# Checklist: Qualidade da Auditoria de Contradicoes

## Proposito
Garantir que todas as contradicoes entre camadas de avaliacao foram sistematicamente detectadas, classificadas por severidade e reconciliadas com justificativa documentada.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Varredura sistematica de contradicoes foi executada entre todas as camadas — Evidencia: `log de varredura com camadas comparadas`
- [ ] Todas as contradicoes detectadas foram registradas — Evidencia: `lista de contradicoes com descricao`
- [ ] Cada contradicao foi classificada por severidade (baixa, media, alta, critica) — Evidencia: `classificacao de severidade por contradicao`
- [ ] Contradicoes de severidade alta e critica foram investigadas em profundidade — Evidencia: `analise detalhada por contradicao severa`
- [ ] Cada contradicao foi reconciliada com justificativa explicita — Evidencia: `justificativa de reconciliacao documentada`
- [ ] Reconciliacao resultou em ajuste nos resultados quando necessario — Evidencia: `registro de ajustes aplicados`
- [ ] Contradicoes irreconciliaveis foram sinalizadas no relatorio final — Evidencia: `flag de contradicao no relatorio`
- [ ] Impacto das contradicoes no score de confianca foi calculado — Evidencia: `ajuste de confianca registrado`
- [ ] Nenhuma contradicao critica ficou sem tratamento — Evidencia: `status de tratamento = completo para todas as criticas`

### Desejaveis (aumentam confianca)
- [ ] Padroes recorrentes de contradicao foram identificados
- [ ] Causa raiz das contradicoes principais foi investigada
- [ ] Contradicoes foram diferenciadas entre genuinas e aparentes
- [ ] Respondente foi consultado sobre contradicoes relevantes
- [ ] Registro de contradicoes inclui referencia as camadas de origem

## Evidencia Necessaria
- Log de varredura sistematica com todas as combinacoes de camadas verificadas
- Lista completa de contradicoes detectadas com descricao
- Classificacao de severidade para cada contradicao
- Analise detalhada de contradicoes de alta severidade
- Justificativa de reconciliacao para cada contradicao
- Registro de ajustes aplicados nos resultados
- Flags de contradicoes irreconciliaveis
- Calculo de impacto no score de confianca

## Acao se Falhar
- Se varredura nao foi feita: executar varredura sistematica completa
- Se contradicoes nao foram classificadas: aplicar criterio de severidade
- Se contradicoes criticas nao foram reconciliadas: investigar e reconciliar antes de finalizar
- Se impacto na confianca nao foi calculado: recalcular scores com ajuste
- Se contradicoes irreconciliaveis nao foram sinalizadas: incluir flags no relatorio
- Relatorio nao pode ser finalizado com contradicoes criticas sem tratamento

## Agente Responsavel
- **Agente principal**: Agente de Auditoria de Contradicoes
- **Agentes de suporte**: Todos os agentes de camada
- **Aprovador final**: Agente de Qualidade
