---
type: component
squad: human-mapping
version: "2.0.0"
---

# Motivation Card

## Proposito

O Motivation Card captura os drivers motivacionais fundamentais de uma pessoa — o que a impulsiona, o que a paralisa e como ela se comporta quando suas necessidades nao sao atendidas. Este card integra dados de frameworks como Eneagrama (motivacoes centrais), SDI (Strength Deployment Inventory), Birkman (necessidades vs. comportamentos usuais) e MVPI do Hogan.

A motivacao e a camada mais profunda do mapeamento humano e frequentemente a menos visivel.

## Estrutura do Card

O card organiza motivacao em torno de dois eixos: o que atrai (energia positiva) e o que repele (energia negativa), incluindo o comportamento sob pressao quando motivacoes sao frustradas.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `framework` | string | Framework de origem (ex: "Eneagrama", "SDI", "Birkman", "MVPI") |
| `core_motivation` | text | O que fundamentalmente move esta pessoa — seu driver central |
| `core_fear` | text | O medo fundamental que esta pessoa tenta evitar |
| `under_pressure_behavior` | text | Como se comporta quando a motivacao central e ameacada |
| `what_energizes` | list | Atividades, contextos e interacoes que geram energia |
| `what_drains` | list | Atividades, contextos e interacoes que consomem energia |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `secondary_motivation` | text | Segundo driver motivacional mais forte |
| `values_hierarchy` | list | Hierarquia de valores pessoais identificada |
| `reward_sensitivity` | string | Tipo de recompensa mais eficaz (reconhecimento, autonomia, etc.) |
| `conflict_trigger` | text | O que tipicamente gera conflito para esta pessoa |
| `hidden_needs` | text | Necessidades que a pessoa nao expressa abertamente (Birkman) |
| `motivational_shift` | text | Como a motivacao muda sob estresse prolongado |
| `cultural_context` | text | Influencias culturais na expressao motivacional |

## Exemplo Preenchido

```yaml
framework: "Eneagrama + SDI"
core_motivation: >
  Necessidade de ser competente e compreender o mundo ao redor.
  Busca autonomia intelectual e teme ser considerado incapaz
  ou invasivamente demandado pelos outros.
core_fear: >
  Ser sobrecarregado por demandas externas e nao ter recursos
  internos suficientes para lidar com elas.
under_pressure_behavior: >
  Retrai-se socialmente, acumula informacao sem compartilhar,
  reduz comunicacao ao minimo. Pode parecer arrogante ou
  desinteressado, mas esta protegendo sua energia.
what_energizes:
  - "Resolver problemas complexos de forma autonoma"
  - "Ter tempo para pesquisa e reflexao profunda"
  - "Conversas intelectualmente estimulantes em grupos pequenos"
  - "Ser reconhecido pela expertise, nao pela sociabilidade"
what_drains:
  - "Reunioes longas sem objetivo claro"
  - "Demandas emocionais intensas e continuas"
  - "Ambientes com alta interrupcao e multitasking forcado"
  - "Expectativa de networking superficial"
hidden_needs: >
  Birkman revela necessidade oculta de aceitacao social que
  contradiz o comportamento observavel de isolamento.
```

## Regras de Preenchimento

1. A `core_motivation` deve ir alem do superficial — "quero crescer na carreira" nao e motivacao central. Buscar o driver subjacente.
2. O `core_fear` deve ser a contrapartida da motivacao — geralmente sao espelhos.
3. O `under_pressure_behavior` e critico para coaches e gestores. Descrever comportamentos observaveis, nao estados internos.
4. As listas `what_energizes` e `what_drains` devem ter no minimo 3 itens cada.
5. Quando houver dados do Birkman, sempre preencher `hidden_needs` — esta e a contribuicao unica deste framework.
6. A motivacao nunca deve ser apresentada como imutavel. Incluir contexto de desenvolvimento.
7. Cruzar dados de motivacao com Trait Cards para verificar coerencia (ex: alta Extroversao + "drenam interacoes sociais" indica contradição que precisa de investigacao).
8. Respeitar que motivacoes podem ser culturalmente mediadas — o que energiza em uma cultura pode drenar em outra.
9. Nunca julgar motivacoes como "boas" ou "ruins" — todas sao validas.
10. Se multiplos frameworks informam este card, citar cada um explicitamente.
