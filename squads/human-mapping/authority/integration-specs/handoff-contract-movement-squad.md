# Contrato de Handoff — Movement Squad

## Visao Geral

Contrato de troca de dados entre Human-Mapping Squad e Movement Squad.
O foco e fornecer dados de motivacao e valores individuais que alimentem
a construcao de movimentos culturais autenticos e engajamento genuino.

## O que Human-Mapping Entrega

- **Mapeamento de motivacao**: drivers intrinsecos, proposito, fontes de energia
- **Hierarquia de valores**: o que importa mais, trade-offs aceitos
- **Identidade de grupo**: como a pessoa se ve em relacao a comunidades
- **Gatilhos de engajamento**: o que mobiliza e o que afasta
- **Nivel de ativismo natural**: disposicao para acao coletiva vs individual

## O que Movement Squad Entrega

- **Insights de identidade cultural**: valores do movimento, simbolos, rituais
- **Contexto comunitario**: dinamicas do grupo, liderancas informais
- **Historico de engajamento**: o que funcionou e o que nao funcionou antes
- **Narrativa do movimento**: missao, visao, causa central

## Formato de Dados

- Formato: JSON conforme schema `motivation-values-v2.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `core_values`, `motivation_drivers`, `confidence_score`
- Campos opcionais: `group_identity_index`, `activism_disposition`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Dados de valores para construcao de movimento requerem minimo de **0.6**
- Motivacoes com confianca abaixo de 0.5 sao sinalizadas como "exploratoria"

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria:
  - Valores declarados vs valores praticados (potencial dissonancia)
  - Influencia do contexto social nas respostas sobre valores
  - Risco de manipulacao se dados forem usados para engajamento forcado
  - Estabilidade temporal dos valores mapeados

## Nivel de Privacidade

- **Nivel 2** — Dados de valores e motivacao
- Dados agregados podem ser compartilhados sem identificacao
- Perfis individuais requerem consentimento
- Retencao maxima: 18 meses com reavaliacao recomendada anualmente

## Referencia de Template de Handoff

- Template: `templates/handoff/movement-handoff-template.json`
- Versao atual: 2.1
- Inclui campo `ethical_use_commitment` obrigatorio

## Loop de Feedback

- Movement Squad reporta como dados de motivacao influenciaram estrategias
- Feedback de participantes sobre alinhamento entre movimento e valores pessoais
- Formato: `feedback/movement-alignment-feedback.json`
- Metricas: autenticidade do engajamento (1-5), retencao de participantes
- Calibracao trimestral com foco em etica e uso responsavel dos dados
