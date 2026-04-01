---
type: checklist
level: macro
squad: human-mapping
version: "3.0.0"
gate: mandatory
---

# Checklist: Qualidade da Sessao Completa

## Proposito
Verificar que a sessao de mapeamento foi conduzida do inicio ao fim com todas as etapas cumpridas, thresholds atingidos e integridade garantida.

## Criterios de Aprovacao

### Obrigatorios — Todos devem passar

#### Intake e Calibracao
- [ ] Intake realizado e registrado antes do inicio — Evidencia: registro de intake com timestamp; campos objetivo, contexto e escopo preenchidos; ref: `intake/intake-quality.md`
- [ ] Calibracao do respondente aprovada — Evidencia: resultado da calibracao com status "aprovado"; score de consistencia >= 0.60; ref: `calibration/calibration-quality.md`

#### Execucao de Camadas
- [ ] Todas as camadas definidas no escopo foram completadas — Evidencia: lista de camadas com status "concluida" para cada uma; contagem concluidas = contagem planejadas; delta = 0
- [ ] Nenhuma camada ignorada ou parcialmente preenchida sem justificativa — Evidencia: campo "camadas_incompletas" vazio OU cada camada incompleta tem justificativa com >= 2 frases

#### Auditoria de Contradicoes
- [ ] Auditoria de contradicoes executada — Evidencia: relatorio de auditoria presente com lista de contradicoes identificadas (pode ser lista vazia); ref: `contradiction/contradiction-audit-quality.md`
- [ ] Contradicoes classificadas e reconciliadas — Evidencia: >= 80% das contradicoes com status "resolvida" ou "tensao valida"; 0 contradicoes de alta severidade em aberto

#### Confidence
- [ ] Confianca media da sessao >= 0.50 — Evidencia: media aritmetica dos confidence scores de todas as camadas >= 0.50; valor numerico documentado
- [ ] Nenhuma camada com confianca < 0.30 sem tratamento — Evidencia: camadas com confidence < 0.30 marcadas como "inconclusiva" no relatorio OU re-avaliadas com dados adicionais
- [ ] Confianca por camada documentada — Evidencia: tabela com confidence score para cada camada presente no relatorio

#### Relatorio Final
- [ ] Relatorio gerado com mapa de confianca — Evidencia: relatorio final presente com secao de confidence map mostrando score por camada e score global
- [ ] Teste Barnum passou — Evidencia: checklist `synthesis/barnum-prevention-quality.md` com status "PASSA"
- [ ] Coerencia narrativa verificada — Evidencia: checklist `synthesis/narrative-coherence-quality.md` com status "PASSA"

#### Integridade
- [ ] Tempo da sessao dentro do intervalo — Evidencia: duracao entre 45min e 180min; timestamps de inicio e fim registrados; desvios justificados
- [ ] Dados brutos preservados para auditoria — Evidencia: artefatos brutos arquivados com referencia/path documentado
- [ ] Aprovacao do Chief registrada — Evidencia: checklist `chief/chief-report-approval-quality.md` com status "APROVADO" e data

### Desejaveis — Aumentam confianca
- [ ] Respondente confirmou conforto durante a sessao (feedback qualitativo)
- [ ] Nenhum indicador de fadiga severa nas respostas finais (consistencia mantida)
- [ ] Sessao sem interrupcoes significativas (> 15min)
- [ ] Revisao por pares do relatorio realizada
- [ ] Feedback qualitativo do respondente coletado ao final

## Metricas Resumo da Sessao

| Metrica | Threshold Minimo | Valor |
|---------|-----------------|-------|
| Confianca media global | >= 0.50 | [valor] |
| Contradicoes resolvidas | >= 80% | [valor] |
| Camadas completas | 100% (ou justificadas) | [valor] |
| Teste Barnum | PASSA | [status] |
| Tempo total | 45-180 min | [valor] |

## Acao se Falhar
- Intake nao feito: reiniciar desde o intake
- Calibracao falhou: recalibrar antes de prosseguir
- Camadas incompletas: completar ou justificar exclusao
- Contradicoes nao auditadas: executar auditoria antes do relatorio
- Confianca < 0.50: investigar camadas fracas; considerar re-avaliacao
- Dados nao preservados: reconstruir a partir dos artefatos disponiveis
- Barnum falhou: retornar ao respondent-quality-auditor

## Agente Responsavel
- **Principal**: human-mapping-chief
- **Suporte**: calibration-agent, contradiction-auditor, synthesis-architect
- **Aprovador**: human-mapping-chief
