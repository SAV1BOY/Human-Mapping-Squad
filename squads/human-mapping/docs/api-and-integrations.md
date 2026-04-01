# API e Integracoes

## Visao Geral

O Human Mapping Squad pode se integrar com diversos sistemas
para automatizar fluxos, importar dados e exportar resultados.
Este guia cobre as integracoes mais comuns.

## ATS — Applicant Tracking Systems

### Integracao Suportada
- Importar dados de candidatos automaticamente
- Anexar relatorios de assessment ao perfil do candidato
- Atualizar status baseado em resultados de assessment

### Plataformas Comuns
- **Gupy**: API REST, webhook para novos candidatos
- **Greenhouse**: API v2, integracao nativa com assessments
- **Lever**: API REST, candidatos e oportunidades
- **Workable**: API, avaliacoes integradas

### Fluxo Tipico
1. Candidato avanca para etapa de assessment no ATS
2. Webhook dispara processo de mapeamento
3. Dados do candidato importados automaticamente
4. Resultado do assessment devolvido ao ATS via API

## LMS — Learning Management Systems

### Casos de Uso
- Assessment de entrada para personalizar trilha de aprendizagem
- Avaliacao de competencias pos-treinamento
- Dashboard de desenvolvimento individual

### Plataformas
- **Moodle**: plugin LTI, API REST
- **Totara**: API nativa para competencias
- **Degreed**: API de skills, integracao bidirecional

## HRIS — Human Resource Information Systems

### Integracao
- Sincronizar dados demograficos e organizacionais
- Alimentar modulos de talent management
- Compliance: reter registros de assessment no sistema oficial

### Plataformas
- **TOTVS Protheus**: integracao via API REST
- **SAP SuccessFactors**: API OData, modulo de talent
- **Workday**: API REST, modulo de talent optimization

## Plataformas de Coaching

### Integracoes
- Compartilhar perfil mapeado com coach designado
- Importar notas de sessao de coaching
- Rastrear progresso em desenvolvimento

### Fluxo
1. Assessment completo gera perfil
2. Perfil compartilhado com plataforma de coaching (com consentimento)
3. Coach acessa sumario executivo e recomendacoes
4. Progresso em coaching retroalimenta o perfil

## Formato de Dados

### Exportacao
- JSON para integracoes programaticas
- CSV para analise em planilha
- PDF para relatorios humanos
- YAML para configuracao e templates

### Importacao
- JSON/CSV com schema definido
- Mapeamento de campos configuravel
- Validacao automatica de dados importados
- Log de erros para dados rejeitados

## Autenticacao

- OAuth 2.0 para integracoes de terceiros
- API keys para servicos internos
- JWT para sessoes de usuario
- Webhook signatures para verificacao de origem
