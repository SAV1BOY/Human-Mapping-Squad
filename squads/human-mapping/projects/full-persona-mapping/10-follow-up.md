# Fase 10: Follow-Up Pós-Entrega de Relatório

## Objetivo

Acompanhar o respondente após a entrega do relatório de mapeamento completo, garantindo que os insights foram compreendidos, internalizados e estão sendo aplicados.

## Quando Executar

- **Follow-up inicial:** 2-4 semanas após a devolutiva
- **Follow-up de progresso:** 2-3 meses após a devolutiva
- **Follow-up de consolidação:** 6 meses após (opcional, conforme necessidade)

## Checklist do Follow-Up Inicial (2-4 semanas)

### Preparação
- [ ] Revisar o Session Summary Card da sessão original
- [ ] Identificar os 3 achados principais que foram comunicados
- [ ] Revisar prioridades de desenvolvimento definidas
- [ ] Verificar se houve handoff para coach ou outro profissional
- [ ] Preparar perguntas específicas baseadas no perfil

### Perguntas-Guia para o Respondente
1. **Compreensão:** "Dos insights que discutimos, quais fizeram mais sentido para você?"
2. **Surpresas:** "Houve algo no relatório que te surpreendeu ou que você discordou?"
3. **Aplicação:** "Você já percebeu algum desses padrões no seu dia a dia desde a sessão?"
4. **Ação:** "Das ações que definimos, quais você conseguiu iniciar?"
5. **Dúvidas:** "Surgiu alguma dúvida ou reflexão nova após a devolutiva?"

### O Que Observar
- O respondente usa a linguagem dos frameworks naturalmente? (sinal de internalização)
- Há exemplos concretos de aplicação? (sinal de transferência)
- O respondente demonstra resistência a algum achado? (possível ponto cego ativo)
- As prioridades de desenvolvimento ainda fazem sentido no contexto atual?

## Checklist do Follow-Up de Progresso (2-3 meses)

### Avaliação de Progresso

| Área de Desenvolvimento | Status | Evidência | Ajuste Necessário |
|------------------------|--------|-----------|-------------------|
| [Prioridade 1] | [Iniciado/Em progresso/Estagnado/Concluído] | [__] | [__] |
| [Prioridade 2] | [Iniciado/Em progresso/Estagnado/Concluído] | [__] | [__] |
| [Prioridade 3] | [Iniciado/Em progresso/Estagnado/Concluído] | [__] | [__] |

### Perguntas de Aprofundamento
1. "O que mudou na forma como você se percebe desde o mapeamento?"
2. "Outros ao seu redor notaram alguma mudança?"
3. "Quais padrões se confirmaram na prática? Algum se mostrou diferente?"
4. "O que está sendo mais difícil de mudar? O que você aprendeu sobre essa dificuldade?"

### Recalibrações Possíveis
- Prioridades podem mudar — contexto profissional ou pessoal evolui
- Novos padrões podem emergir que não eram visíveis na sessão original
- Nível de autoconhecimento pode ter mudado (rever Self-Awareness Score)
- Contradições não resolvidas podem ter se esclarecido com a experiência

## Documentação do Follow-Up

```yaml
follow_up_record:
  sessao_original: "[ID]"
  tipo_follow_up: "[Inicial / Progresso / Consolidação]"
  data: "[DD/MM/AAAA]"
  formato: "[Presencial / Videochamada / Escrito]"
  duracao_minutos: "[__]"

  insights_internalizados:
    - "[Qual insight foi absorvido e evidência]"

  resistencias_observadas:
    - "[Qual achado ainda gera resistência e hipótese sobre o porquê]"

  progresso_desenvolvimento:
    - area: "[__]"
      status: "[__]"
      nota: "[__]"

  ajustes_no_plano:
    - "[Mudança feita e justificativa]"

  proximos_passos:
    - "[Ação com responsável e prazo]"

  necessita_reavaliacao: "[Sim / Não]"
  justificativa_reavaliacao: "[Se sim, por quê]"
```

## Critérios para Recomendar Reavaliação Completa

- Mudança significativa de contexto (novo cargo, nova empresa, evento de vida)
- Respondente relata que "não se reconhece mais" no perfil
- Contradições persistentes que sugerem avaliação original pode ter sido imprecisa
- Passaram-se 18+ meses desde o mapeamento original
- Coach ou gestor reporta comportamentos muito diferentes do perfil

## Encerramento do Ciclo

O ciclo de mapeamento se encerra quando:
1. Respondente internalizou os principais insights
2. Plano de desenvolvimento está em andamento com autonomia
3. Handoff para coach ou gestor foi completado (se aplicável)
4. Documentação está completa e arquivada
5. Respondente sabe como solicitar reavaliação futura se necessário

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] Respondente confirmou recebimento do relatório
- [ ] Follow-up inicial (2-4 semanas) realizado e documentado
- [ ] Prioridades de desenvolvimento revisadas com respondente

### NO-GO (não avançar)
- Respondente não confirmou recebimento → Ação: reenviar e agendar contato
- Resistência significativa aos achados → Ação: sessão adicional de devolutiva

### Entregáveis Obrigatórios
- `follow_up_record` (YAML) — preenchido e validado

### Arquivos Relacionados
- `checklists/report/actionability-quality.md`
- `workflows/19-follow-up-reassessment-flow.md`
- `templates/operational/session-log-template.md`
