# Contrato de Handoff — C-Level Squad

## Visao Geral

Este contrato regula a troca de dados entre Human-Mapping Squad e C-Level Squad.
O foco e fornecer perfis executivos e dados de composicao de equipe que apoiem
decisoes de contratacao, promocao e reestruturacao no nivel C-Level.

## O que Human-Mapping Entrega

- **Perfis executivos completos**: personalidade, estilo de lideranca, pontos cegos
- **Dados de composicao de equipe**: diversidade cognitiva, lacunas, redundancias
- **Analise de complementaridade**: como candidatos se encaixam na equipe existente
- **Indicadores de risco**: burnout, desalinhamento cultural, potencial de conflito

## O que C-Level Entrega

- **Necessidades de contratacao**: posicoes abertas, perfil ideal, urgencia
- **Contexto cultural**: valores da empresa, estilo de gestao predominante
- **Historico de equipe**: saidas recentes, conflitos, dinamicas existentes
- **Restricoes do processo**: timeline, orcamento, stakeholders envolvidos

## Formato de Dados

- Formato: JSON conforme schema `executive-profile-v3.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `role_context`, `confidence_score`, `team_fit_index`
- Campos opcionais: `onboarding_recommendations`, `risk_flags`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Para decisoes de contratacao C-Level, recomendado minimo de **0.7**
- Assessments entre 0.5-0.7 devem incluir caveat explicito

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria contendo:
  - Tempo de interacao com avaliado
  - Frameworks utilizados vs disponiveis
  - Fatores contextuais que podem afetar resultados
  - Contradicoes entre instrumentos diferentes

## Nivel de Privacidade

- **Nivel 4** — Dados altamente sensiveis (nivel executivo)
- Acesso restrito a decisores diretos do processo
- Consentimento explicito do avaliado para compartilhamento
- Retencao maxima: 18 meses ou fim do processo seletivo

## Referencia de Template de Handoff

- Template: `templates/handoff/c-level-handoff-template.json`
- Versao atual: 3.0
- Inclui secao especifica para `team_composition_analysis`

## Loop de Feedback

- C-Level Squad deve reportar resultado da decisao (contratou/nao contratou)
- Follow-up obrigatorio aos 6 meses para validar precisao do perfil
- Formato: `feedback/c-level-outcome-form.json`
- Metricas: precisao do fit cultural, performance real vs prevista
- Calibracao semestral entre squads com analise de acertos e erros
