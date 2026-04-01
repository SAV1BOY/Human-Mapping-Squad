---
type: task
squad: human-mapping
version: "2.0.0"
agent: operations-agent
workflow: operations-workflow
---

# Task: Onboarding de Novo Assessor

## Objetivo

Realizar o onboarding completo de um novo assessor (agente humano ou AI) no squad de human-mapping, garantindo que ele conheça a metodologia, ferramentas e padrões de qualidade do squad.

## Pré-condições

- Novo assessor aprovado pelo squad lead
- Acesso aos repositórios e ferramentas do squad concedido
- Disponibilidade de um assessor sênior para mentoria

## Passos

1. Preparar kit de onboarding:
   - Documento de visão e missão do squad (`README.md`)
   - Arquitetura do sistema (`ARCHITECTURE.md`)
   - Configurações do squad (`config.yaml`)
   - Guia de voz e tom (`voice/`)
2. Conduzir sessão de orientação inicial:
   - Apresentar o fluxo completo de assessment (intake -> calibração -> assessment -> audit -> síntese -> review)
   - Explicar os frameworks utilizados e suas interrelações
   - Demonstrar como os scripts automatizam partes do processo
   - Apresentar os padrões de qualidade e limiares de confiança
3. Treinamento teórico nos frameworks (sequência recomendada):
   - Big Five / OCEAN (base de tudo)
   - Hogan (tradução para trabalho)
   - MBTI / Jung (tipos e funções cognitivas)
   - CliftonStrengths e VIA (forças)
   - Belbin (papéis de equipe)
   - RIASEC / Holland (interesses profissionais)
   - Kolbe (modo de ação)
4. Treinamento prático:
   - Observar 2-3 sessões conduzidas por assessor sênior
   - Conduzir 1 sessão supervisionada com feedback em tempo real
   - Conduzir 2 sessões com revisão posterior
5. Avaliação de competência:
   - Acurácia mínima de 70% nas sessões supervisionadas
   - Domínio dos scripts e ferramentas do squad
   - Compreensão dos padrões de qualidade
6. Certificar novo assessor e registrar no squad roster

## Outputs

- `onboarding-plan`: Plano personalizado de onboarding
- `training-log`: Registro de treinamentos concluídos
- `competency-assessment`: Avaliação de competência do novo assessor
- `certification`: Certificação de conclusão do onboarding

## Checklist de Conclusão

- [ ] Kit de onboarding entregue
- [ ] Sessão de orientação conduzida
- [ ] Treinamento teórico concluído (7 frameworks)
- [ ] Observação de sessões realizada
- [ ] Sessão supervisionada conduzida
- [ ] Sessões com revisão posterior concluídas
- [ ] Competência avaliada e aprovada
- [ ] Assessor certificado e registrado no roster

## Próxima Task

Nenhuma — esta é uma task terminal de onboarding.

## Subtask Breakdown
1. **Preparar e entregar kit** — Agente: `operations-agent`. Input: materiais do squad. Output: kit de onboarding entregue. Gate: README, ARCHITECTURE, config e voice entregues.
2. **Conduzir orientação** — Agente: `operations-agent`. Input: fluxo completo do assessment. Output: sessão de orientação concluída. Gate: novo assessor demonstra compreensão do fluxo.
3. **Treinamento teórico** — Agente: `operations-agent`. Input: 7 frameworks. Output: `training-log` com 7 módulos. Gate: avaliação teórica >= 70% por framework.
4. **Treinamento prático** — Agente: `operations-agent`. Input: sessões reais. Output: 3 sessões observadas + 1 supervisionada + 2 revisadas. Gate: todas concluídas.
5. **Certificar assessor** — Agente: `operations-agent`. Input: avaliação de competência. Output: `certification`. Gate: acurácia >= 70% nas sessões supervisionadas.

## Quality Gate
- [ ] 7 frameworks treinados com avaliação >= 70%
- [ ] Acurácia >= 70% nas sessões supervisionadas
- Threshold: competência em scripts e ferramentas demonstrada
- Se FAIL: estender período de supervisão com +2 sessões assistidas

## Rework Trigger
- Acurácia < 70% nas sessões → retreinamento nos frameworks com gap
- Não domina scripts → sessão adicional de treinamento técnico
