# Changelog Detalhado — Human-Mapping Squad

## Proposito

Registro detalhado de todas as mudancas significativas na metodologia,
processos, frameworks e ferramentas do Human-Mapping Squad. Inclui
contexto de decisao, impacto esperado e breaking changes.

---

## v3.2.0 — 2026-04-01

### Novos Arquivos e Capacidades
- **Contratos de handoff inter-squad**: 7 contratos formalizando troca de dados
  com Advisory, C-Level, Sales, Brand, Storytelling, Movement e Data Squads
- **Referencia de psicometria expandida**: vieses de resposta, normatizacao,
  estabilidade longitudinal
- **Referencia de dinamicas de equipe**: padroes toxicos, equipes remotas,
  fusoes e reconstituicao
- **Anti-patterns de assessment**: catalogo de falhas comuns e prevencao
- **Pattern de identidade cultural hibrida**: assessment de pessoas biculturais
- **Caso de falha documentado**: estudo de caso de assessment que errou
- **Workshop de analise de falhas**: kit para aprender com erros

### Melhorias em Documentacao
- Pipeline de recuperacao de falhas documentado por estagio
- Guia de retrospectiva pos-assessment com metricas de precisao
- Tutorial de interpretacao de contradicoes entre frameworks

### Expansao de Frases
- Rapport: frases para contexto brasileiro, alta pressao e respondentes resistentes
- Encerramento: frases para resumo, expectativas, follow-up e reacoes emocionais
- Reframing: frases para reframing de fraquezas, contradicoes e scores baixos

### Impacto
- Formalizacao de interfaces inter-squad melhora consistencia de entrega
- Base de conhecimento de falhas reduz erros repetidos
- Material de referencia suporta avaliadores em formacao

---

## v3.1.0 — 2026-02-15

### Mudancas de Metodologia
- Adocao de confianca minima 0.5 como padrao para todos os handoffs
- Introduzido requisito de minimo 2 frameworks por assessment
- Implementacao de feedback loops obrigatorios com squads parceiros

### Breaking Changes
- Schema de perfil executivo atualizado de v2 para v3
  - Campo `team_fit_index` agora obrigatorio
  - Campo `risk_flags` renomeado para `risk_indicators`
- Template de devolutiva reestruturado para incluir secao de limitacoes

### Impacto
- Assessments com framework unico nao sao mais aceitos para handoff
- Squads parceiros precisam atualizar integracao para novo schema

---

## v3.0.0 — 2025-11-01

### Breaking Changes Maiores
- Migracao completa para pipeline de 5 estagios
- Novo sistema de scoring com calibracao inter-avaliador
- Reformulacao do modelo de confianca (0.0-1.0 em vez de categorias)

### Novas Capacidades
- Assessment de equipe (alem de individual)
- Integracao com ferramentas de feedback 360
- Dashboard de metricas de qualidade do pipeline

### Metodologia
- Introducao do cruzamento obrigatorio Big Five + MBTI + DISC
- Protocolo de contradicoes formalizado
- Guia de reframing para devolutivas

### Impacto
- Todos os templates anteriores precisam ser migrados
- Treinamento obrigatorio para avaliadores no novo pipeline
- Retrocompatibilidade mantida por 6 meses (ate maio 2026)

---

## v2.5.0 — 2025-08-01

### Melhorias
- Frases de rapport expandidas com calibracao cultural brasileira
- Templates de relatorio padronizados por tipo de assessment
- Primeiros workflows automatizados para scoring

### Correcoes
- Corrigido vies de ancoragem no template de interpretacao
- Ajustados benchmarks de Conscienciosidade para contexto brasileiro
- Corrigido calculo de score composto que ignorava pesos

---

## v2.0.0 — 2025-04-01

### Lancamento Inicial Estruturado
- Primeira versao com arquitetura de squad definida
- Frameworks de assessment documentados (Big Five, MBTI, DISC, Eneagrama)
- Pipeline basico de coleta-analise-devolutiva
- Biblioteca de frases para sessoes
- Templates de relatorio v1

### Decisoes Arquiteturais
- Escolha de JSON como formato padrao de dados
- Definicao de niveis de privacidade (1-4)
- Separacao entre dados de assessment e dados interpretativos

---

## Convencoes deste Changelog

- **Breaking Change**: mudanca que requer acao dos consumidores de dados
- **Nova Capacidade**: funcionalidade que nao existia antes
- **Melhoria**: aprimoramento de algo existente
- **Correcao**: fix de bug ou erro metodologico
- Versoes seguem semver: MAJOR.MINOR.PATCH
- MAJOR: breaking changes; MINOR: novas capacidades; PATCH: correcoes
