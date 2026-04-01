# Contrato de Handoff — Sales Squad

## Visao Geral

Contrato de troca de dados entre Human-Mapping Squad e Sales Squad.
O objetivo e fornecer perfis de closers e estilos de comunicacao que
otimizem alocacao de vendedores e desenvolvimento comercial.

## O que Human-Mapping Entrega

- **Perfis de closers**: estilo de persuasao, tolerancia a rejeicao, resiliencia
- **Estilos de comunicacao**: dominante, influente, analitico, estavel
- **Gatilhos motivacionais**: o que energiza e o que drena cada vendedor
- **Mapeamento de pontos fortes**: prospeccao, negociacao, fechamento, pos-venda
- **Indicadores de burnout comercial**: sinais precoces de esgotamento

## O que Sales Squad Entrega

- **Dados de performance**: metricas de conversao, ticket medio, ciclo de venda
- **Feedback de campo**: como o vendedor performa em diferentes contextos
- **Historico de resultados**: tendencias de performance ao longo do tempo
- **Contexto de mercado**: complexidade do produto, perfil de cliente

## Formato de Dados

- Formato: JSON conforme schema `closer-profile-v2.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `communication_style`, `confidence_score`
- Campos opcionais: `team_pairing_suggestions`, `development_priorities`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Recomendacoes de realocacao requerem minimo de **0.6**
- Perfis abaixo de 0.5 podem ser compartilhados como "hipotese inicial"

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria:
  - Assessment de vendedor em periodo atipico (baixa/alta temporada)
  - Influencia do produto/mercado nos resultados comportamentais
  - Diferenca entre estilo natural e estilo adaptado
  - Limitacoes de auto-relato em profissionais de vendas (vies de desejabilidade)

## Nivel de Privacidade

- **Nivel 2** — Dados profissionais de desenvolvimento
- Gestores de vendas tem acesso ao perfil agregado
- Dados individuais detalhados requerem autorizacao
- Retencao maxima: 12 meses com atualizacao recomendada

## Referencia de Template de Handoff

- Template: `templates/handoff/sales-handoff-template.json`
- Versao atual: 2.0
- Inclui campo `performance_correlation` para cruzamento com metricas

## Loop de Feedback

- Sales Squad reporta correlacao entre perfil e performance real
- Feedback mensal com metricas de conversao por perfil
- Formato: `feedback/sales-performance-feedback.json`
- Metricas: correlacao perfil-resultado, utilidade para alocacao
- Calibracao mensal para ajustar modelos preditivos
