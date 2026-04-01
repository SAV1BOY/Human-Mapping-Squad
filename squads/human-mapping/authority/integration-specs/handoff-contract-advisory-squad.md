# Contrato de Handoff — Advisory Squad

## Visao Geral

Este contrato define o protocolo de troca de dados entre o Human-Mapping Squad
e o Advisory Squad. O objetivo e garantir que perfis de lideranca e avaliacoes
de sucessao alimentem decisoes estrategicas com dados confiaveis.

## O que Human-Mapping Entrega

- **Perfis de lideranca**: Big Five, MBTI, estilos de decisao, tolerancia a risco
- **Avaliacoes de sucessao**: prontidao de candidatos, gaps de competencia, potencial
- **Mapeamento de equipe executiva**: composicao, complementaridade, riscos de saida
- **Analise de fit cultural**: alinhamento entre lider e cultura organizacional

## O que Advisory Entrega

- **Contexto estrategico**: momento da empresa, desafios prioritarios, horizonte de planejamento
- **Prioridades organizacionais**: areas criticas, iniciativas em andamento
- **Restricoes politicas**: sensibilidades internas, historico de conflitos

## Formato de Dados

- Formato: JSON estruturado conforme schema `leadership-profile-v2.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `assessment_date`, `confidence_score`, `frameworks_used`
- Campos opcionais: `narrative_summary`, `development_recommendations`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Assessments abaixo de 0.5 devem ser sinalizados como "preliminar — requer validacao"
- Advisory deve ser notificado quando confianca esta entre 0.5 e 0.65

## Divulgacao de Limitacoes

- Todo handoff deve incluir secao `limitations` com:
  - Frameworks nao aplicados e motivo
  - Contradicoes nao resolvidas
  - Vieses potenciais identificados
  - Tamanho da amostra comportamental

## Nivel de Privacidade

- **Nivel 3** — Dados sensiveis de lideranca
- Acesso restrito a consultores senior do Advisory Squad
- Proibida redistribuicao sem autorizacao do avaliado
- Retencao maxima: 24 meses apos assessment

## Referencia de Template de Handoff

- Template: `templates/handoff/advisory-handoff-template.json`
- Versao atual: 2.1
- Campos de metadados: `handoff_timestamp`, `source_squad`, `target_squad`

## Loop de Feedback

- Advisory deve retornar feedback em ate 30 dias apos uso dos dados
- Formato: formulario padrao `feedback/advisory-feedback-form.json`
- Metricas de feedback: utilidade (1-5), precisao percebida (1-5), gaps identificados
- Reuniao trimestral de calibracao entre squads
- Feedback alimenta modelo de melhoria continua do Human-Mapping
