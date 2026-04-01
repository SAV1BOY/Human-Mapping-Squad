# Fase 07: Conexao com Pipeline de Sucessao

## Objetivo

Conectar os achados do assessment de lideranca ao processo de planejamento de sucessao da organizacao. Transformar dados de perfil individual em insumos para decisoes de desenvolvimento de bench, identificacao de gaps de lideranca e priorizacao de investimentos em talentos.

## Quando Executar

- Apos a conclusao do perfil de lideranca completo (Fase 06)
- Quando a organizacao solicitar input para revisao de talentos (talent review)
- Quando houver mudanca na estrutura de lideranca (saida, promocao, reestruturacao)

## Pre-Requisitos

- Perfil de lideranca completo com confidence minimo de 0.65
- Definicao clara da posicao-alvo de sucessao
- Autorizacao do respondente e do sponsor para uso dos dados neste contexto

## Etapas

### Etapa 1: Mapear Posicoes Criticas

Identificar quais posicoes de lideranca na organizacao sao criticas para sucessao:

| Posicao | Titular Atual | Risco de Vacancia | Impacto se Vacante | Prioridade |
|---------|--------------|-------------------|--------------------|-----------|
| ___ | ___ | (Alto / Medio / Baixo) | (Critico / Alto / Moderado) | ___ |

### Etapa 2: Definir Perfil da Posicao

Para cada posicao critica, derivar o perfil ideal:
- Quais traits sao essenciais vs. desejaveis?
- Quais competencias de lideranca sao non-negotiable?
- Quais derailers seriam inaceitaveis nesta posicao?
- Qual o contexto futuro da posicao (o que muda nos proximos 2-3 anos)?

### Etapa 3: Cross-Reference com Candidatos Mapeados

Para cada candidato com assessment de lideranca completo:

```yaml
candidate:
  name: ___
  current_role: ___
  target_position: ___
  fit_score: ___ (0.0 a 1.0)
  strengths_aligned:
    - ___
  gaps_identified:
    - gap: ___
      developable: (Sim / Parcial / Nao)
      timeline: ___
  derailer_risks:
    - ___
  readiness: "(Pronto agora / 6-12 meses / 12-24 meses / 24+ meses / Nao recomendado)"
```

### Etapa 4: Construir Matriz de Sucessao

| Posicao | Candidato 1 | Readiness | Candidato 2 | Readiness | Gap Critico |
|---------|-------------|-----------|-------------|-----------|-------------|
| ___ | ___ | ___ | ___ | ___ | ___ |

### Etapa 5: Plano de Aceleracao

Para cada candidato com readiness de 6-24 meses:
1. **Experiencias de desenvolvimento:** Projetos, rotacoes, exposicao a board
2. **Coaching focado:** Areas especificas derivadas do assessment
3. **Mentoria:** Pareamento com lider senior que complemente gaps
4. **Marcos de validacao:** Checkpoints para reavaliar readiness

### Etapa 6: Documentar Riscos e Contingencias

- O que acontece se o titular sair antes do candidato estar pronto?
- Ha candidato externo como opcao? Qual o perfil?
- Qual o custo de uma transicao mal planejada vs. investimento em desenvolvimento?

## Output

- Succession Assessment Template preenchido para cada posicao critica
- Plano de aceleracao individualizado para candidatos top
- Matriz de sucessao consolidada para apresentacao ao board/sponsor
- Timeline de revisao (proxima atualizacao recomendada)

## Quality Gates

- [ ] Perfil de posicao definido com criterios claros e ponderados
- [ ] Todos os candidatos tem assessment com confidence minimo de 0.65
- [ ] Fit score documentado com rastreabilidade de frameworks
- [ ] Gaps classificados como desenvolviveis ou nao-desenvolviveis
- [ ] Plano de aceleracao com acoes especificas e timeline
- [ ] Riscos documentados com plano de contingencia
- [ ] Confidencialidade preservada — dados compartilhados apenas com autorizacao

## Notas sobre Etica e Confidencialidade

Os dados de assessment de lideranca sao extremamente sensiveis no contexto de sucessao. Garantir que:
- O respondente saiba que seus dados serao usados para planejamento de sucessao
- O acesso seja restrito ao sponsor e ao comite de talentos
- Os dados nao sejam usados para decisoes de desligamento
- O feedback ao candidato seja construtivo, focado em desenvolvimento
