# Fase 00 — Intake (Coleta Inicial)

## Objetivo
Coletar todas as informações iniciais necessárias para iniciar o mapeamento completo
de persona, incluindo dados demográficos, contexto profissional, objetivos do cliente
e quaisquer avaliações prévias disponíveis.

## Inputs
- Solicitação do cliente ou stakeholder
- Questionário de intake preenchido
- Resultados de avaliações prévias (se disponíveis)
- Contexto organizacional (se aplicável)

## Processo
1. Enviar questionário de intake ao cliente
2. Coletar e revisar respostas do questionário
3. Identificar avaliações prévias e verificar validade temporal
4. Definir escopo do mapeamento (quais frameworks serão utilizados)
5. Alinhar expectativas sobre entregas e cronograma
6. Registrar todas as informações no sistema de registros

## Outputs
- Ficha de intake completa e validada
- Lista de avaliações a serem aplicadas
- Cronograma preliminar do projeto
- Registro inicial no persona-registry

## Checklist
- [ ] Questionário de intake enviado e recebido
- [ ] Dados demográficos e contexto registrados
- [ ] Avaliações prévias coletadas e verificadas
- [ ] Escopo do mapeamento definido e aprovado
- [ ] Cronograma acordado com o cliente
- [ ] Registro criado no persona-registry

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] Objetivo do mapeamento definido e documentado
- [ ] Contexto profissional/organizacional registrado
- [ ] Profundidade do mapeamento (depth level) selecionada

### NO-GO (não avançar)
- Objetivo vago ou ausente → Ação: agendar nova sessão de alinhamento com stakeholder
- Dados mínimos de contexto insuficientes → Ação: enviar questionário complementar

### Entregáveis Obrigatórios
- `session-brief` — preenchido e validado
- `goal-definition-sheet` — preenchido e validado

### Arquivos Relacionados
- `templates/intake/session-brief.md`
- `templates/intake/goal-definition-sheet.md`
- `checklists/intake-quality.md`
- `workflows/01-goal-and-context-definition.md`

## Próxima Fase
`01-calibration.md` — Calibração dos instrumentos e metodologia
