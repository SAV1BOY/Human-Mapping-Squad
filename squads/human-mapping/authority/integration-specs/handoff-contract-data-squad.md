# Contrato de Handoff — Data Squad

## Visao Geral

Contrato de troca de dados entre Human-Mapping Squad e Data Squad.
O objetivo e fornecer metricas de assessment para analise estatistica
e receber validacao que melhore a precisao dos modelos de mapeamento.

## O que Human-Mapping Entrega

- **Metricas de assessment**: scores brutos, percentis, indices compostos
- **Dados de confiabilidade**: consistencia interna, test-retest quando disponivel
- **Metadados de sessao**: duracao, numero de itens, taxa de completude
- **Indicadores de qualidade**: flags de vies, itens inconsistentes, outliers
- **Dados longitudinais**: historico de assessments quando disponivel

## O que Data Squad Entrega

- **Validacao estatistica**: analise de confiabilidade, validade convergente/divergente
- **Deteccao de anomalias**: padroes atipicos, dados suspeitos
- **Normas atualizadas**: benchmarks populacionais, normas por segmento
- **Modelos preditivos**: correlacoes entre tracos e outcomes organizacionais
- **Analise de vies**: deteccao de vieses sistematicos nos instrumentos

## Formato de Dados

- Formato: JSON conforme schema `assessment-metrics-v3.json`
- Encoding: UTF-8
- Campos obrigatorios: `assessment_id`, `metrics_array`, `quality_flags`, `confidence_score`
- Campos opcionais: `longitudinal_data`, `cross_framework_correlations`
- Dados devem ser anonimizados antes do handoff (campo `anonymized: true`)

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Dados para treinamento de modelos preditivos requerem minimo de **0.7**
- Dados abaixo de 0.5 podem ser enviados para analise de qualidade

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria:
  - Tamanho da amostra e representatividade
  - Instrumentos com propriedades psicometricas desconhecidas
  - Contexto de aplicacao que pode afetar validade
  - Dados faltantes e estrategia de tratamento utilizada

## Nivel de Privacidade

- **Nivel 1** — Dados anonimizados para analise
- Obrigatoria anonimizacao completa antes do handoff
- Proibida re-identificacao de individuos
- Retencao: sem limite para dados anonimizados agregados

## Referencia de Template de Handoff

- Template: `templates/handoff/data-handoff-template.json`
- Versao atual: 3.1
- Inclui schema de validacao automatica para consistencia de dados

## Loop de Feedback

- Data Squad retorna relatorios de validacao em ate 15 dias uteis
- Alertas imediatos para anomalias criticas detectadas
- Formato: `feedback/data-validation-report.json`
- Metricas: confiabilidade dos instrumentos, validade preditiva, taxa de anomalias
- Reuniao mensal para revisao de modelos e ajuste de parametros
