---
type: checklist
level: layer
layer: chief
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Aprovacao de Atualizacoes Metodologicas pelo Chief

## Proposito
Garantir que toda atualizacao metodologica (novos frameworks, mudancas em rubrics, ajustes em scripts, novas patterns) seja aprovada pelo Chief com evidencia adequada, validacao e plano de rollback. Mudancas metodologicas impactam todos os assessments futuros — o rigor de aprovacao deve ser proporcional ao impacto.

## Criterios Obrigatorios

### Evidencia e Justificativa
- [ ] A atualizacao tem justificativa documentada baseada em evidencia (dados de sessoes, pesquisa, feedback) — Evidencia: `___`
- [ ] O problema que a atualizacao resolve esta claramente descrito com exemplos concretos — Evidencia: `___`
- [ ] A fonte da mudanca e rastreavel (sessao especifica, RalphLoop, pesquisa externa) — Referencia: `___`
- [ ] Alternativas a atualizacao foram consideradas e documentadas — Evidencia: `___`

### Validacao
- [ ] A atualizacao foi testada em pelo menos 2 casos reais ou simulados antes da aprovacao — Casos: `___`
- [ ] Os resultados dos testes mostram melhoria mensuravel (confidence score, acuracia, completude) — Metricas: `___`
- [ ] A atualizacao nao introduz contradicoes com metodologias existentes — Verificacao: `___`
- [ ] Pelo menos um agente alem do propositor revisou e concordou com a mudanca — Revisor: `___`

### Impacto e Escopo
- [ ] O escopo da atualizacao esta claramente delimitado (quais arquivos, quais processos, quais pipelines) — Escopo: `___`
- [ ] O impacto em assessments futuros foi avaliado (quantos sessoes/relatorios serao afetados) — Impacto: `___`
- [ ] Sessoes em andamento nao serao comprometidas pela mudanca — Confirmacao: `___`
- [ ] A atualizacao e retrocompativel ou ha plano de migracao para dados existentes — Status: `___`

### Plano de Rollback
- [ ] Existe plano de rollback documentado caso a atualizacao gere efeitos negativos — Plano: `___`
- [ ] Os arquivos originais (pre-mudanca) estao preservados ou versionados — Localizacao: `___`
- [ ] Criterios para acionar o rollback estao definidos (ex: confidence cai > 0.10 em 3+ sessoes) — Criterios: `___`
- [ ] O rollback pode ser executado em menos de 30 minutos — Confirmacao: `___`

### Comunicacao
- [ ] Todos os agentes afetados foram notificados sobre a mudanca — Lista: `___`
- [ ] O changelog do squad foi atualizado com descricao da mudanca — Data: `___`
- [ ] A documentacao associada (rubrics, templates, scripts) foi atualizada simultaneamente — Arquivos: `___`

## Niveis de Aprovacao

| Tipo de Mudanca | Nivel de Aprovacao | Validacao Minima |
|----------------|-------------------|-----------------|
| Correcao de erro em template | Chief review | 1 caso teste |
| Novo pattern na biblioteca | Chief review + 1 revisor | 2 casos reais |
| Mudanca em rubric de scoring | Chief review + 2 revisores | 3 casos reais |
| Novo framework integrado | Chief review + validacao completa | 5 casos reais + pesquisa |
| Mudanca em script de analise | Chief review + teste automatizado | 3 casos + comparacao antes/depois |
| Mudanca estrutural no pipeline | Chief review + todos os agentes | 5 casos + periodo de teste de 30 dias |

## Decisao do Chief

- [ ] **APROVADO** — Implementar imediatamente
- [ ] **APROVADO COM CONDICOES** — Implementar apos atender condicoes: `___`
- [ ] **DEVOLVIDO** — Necessita mais evidencia ou validacao: `___`
- [ ] **REJEITADO** — Justificativa: `___`

**Data da decisao:** ___
**Chief:** ___

## Monitoramento Pos-Implementacao

- [ ] Revisao de impacto agendada para 30 dias apos implementacao — Data: `___`
- [ ] Metricas de monitoramento definidas — Metricas: `___`
- [ ] Responsavel pelo monitoramento designado — Responsavel: `___`
