# Fase 11: Atualizacao de Memoria da Sessao

## Objetivo

Registrar os achados-chave da sessao de mapeamento na memoria persistente para permitir retomada futura via `/resume`. Este passo garante continuidade entre sessoes, preservando contexto, decisoes, contradicoes e proximos passos sem necessidade de reprocessar todos os dados.

## Quando Executar

- Ao final de cada sessao de mapeamento (obrigatorio)
- Apos qualquer sessao de devolutiva que gere novos insights
- Apos follow-up que altere o perfil ou o plano de desenvolvimento
- Antes de qualquer pausa prolongada (mais de 7 dias entre sessoes)

## Estrutura do Memory Update

### Bloco 1: Identificacao da Sessao

```yaml
session_id: ___
respondent_id: ___
date: ___
session_number: ___ de ___
pipeline_stage_completed: ___
next_pipeline_stage: ___
analyst: ___
```

### Bloco 2: Key Findings (Achados Principais)

Registrar os 5-7 achados mais importantes da sessao, cada um com:

```yaml
key_findings:
  - finding: "Descricao concisa do achado"
    layer: "Camada de origem (Traits, Types, Motivation, etc.)"
    confidence: 0.XX
    frameworks: ["framework1", "framework2"]
    status: "(Confirmado / Hipotese / Em Investigacao)"
```

### Bloco 3: Confidence Map

Estado atual da confianca por camada:

```yaml
confidence_map:
  traits: 0.XX
  types: 0.XX
  motivation: 0.XX
  strengths: 0.XX
  conation: 0.XX
  career: 0.XX
  overall: 0.XX
```

### Bloco 4: Contradicoes Ativas

Contradicoes que ainda nao foram resolvidas ou que requerem atencao:

```yaml
active_contradictions:
  - id: "CONT-XXX"
    description: "Descricao breve"
    severity: "(Low / Medium / High / Critical)"
    status: "(Unresolved / Partially Resolved / Under Investigation)"
    next_action: "O que fazer na proxima sessao"
```

### Bloco 5: Patterns Detectados

```yaml
patterns_detected:
  - pattern: "nome-do-pattern"
    confidence: 0.XX
    confirmed: (true / false)
```

### Bloco 6: Plano de Desenvolvimento (se iniciado)

```yaml
development_plan:
  status: "(Nao Iniciado / Em Construcao / Finalizado)"
  priorities:
    - area: "Descricao da area"
      urgency: "(Alta / Media / Baixa)"
  timeline: "___"
```

### Bloco 7: Contexto para Retomada

Notas em texto livre para o analista que retomar a sessao:

```yaml
resume_context: >
  Informacoes criticas que nao cabem nos campos estruturados.
  Incluir: humor do respondente, eventos de vida recentes,
  decisoes tomadas sobre abordagem, ajustes no pipeline,
  e qualquer insight subjetivo relevante.
```

### Bloco 8: Proximos Passos

```yaml
next_steps:
  - step: "Descricao do proximo passo"
    responsible: "(agente / analista / respondente)"
    deadline: "___"
    dependency: "___"
```

## Regras de Atualizacao

1. **Nunca sobrescrever** — cada update e um novo registro datado. Manter historico completo.
2. **Key findings devem ser acumulativos** — adicionar novos, nunca remover antigos (marcar como "Revisado" se mudou).
3. **Confidence map deve refletir o estado ATUAL** — ajustar para cima ou para baixo conforme novos dados.
4. **Contradicoes resolvidas** saem de `active_contradictions` e vao para um log de resolucao.
5. **O `resume_context` e o campo mais importante** — ser generoso em contexto narrativo. O proximo analista (ou voce mesmo semanas depois) vai agradecer.
6. **Validar completude antes de salvar** — todos os 8 blocos devem estar preenchidos, mesmo que parcialmente.

## Validacao do Memory Update

- [ ] Todos os 8 blocos preenchidos
- [ ] Key findings com confidence e status atualizados
- [ ] Contradicoes ativas refletem estado real (nenhuma esquecida)
- [ ] Proximos passos sao accionaveis e com responsavel definido
- [ ] Resume context inclui informacao suficiente para retomada sem perda de contexto

## Integracao com /resume

Quando o comando `/resume` for ativado, o sistema deve:
1. Carregar o memory update mais recente
2. Apresentar ao analista o estado atual do mapeamento
3. Listar proximos passos pendentes
4. Sinalizar contradicoes ativas e decisoes pendentes
5. Restaurar o contexto narrativo do `resume_context`
