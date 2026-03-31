---
type: component
squad: human-mapping
version: "2.0.0"
---

# Contradiction Card

## Proposito

O Contradiction Card documenta inconsistencias detectadas entre resultados de diferentes frameworks ou entre diferentes camadas do perfil. Contradicoes nao sao necessariamente erros — podem revelar adaptacao, crescimento, contexto-dependencia ou, em alguns casos, problemas na qualidade dos dados. Este card e fundamental para a integridade do mapeamento.

A capacidade de detectar e interpretar contradicoes e o que diferencia um mapeamento mecanico de uma analise humana sofisticada.

## Estrutura do Card

O card estrutura a contradicao como um fenomeno a ser investigado, nao como um erro a ser corrigido, com espaco para multiplas explicacoes possiveis.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `frameworks_involved` | list | Frameworks que geraram os resultados conflitantes |
| `nature_of_conflict` | text | Descricao clara de qual e a contradicao e por que e relevante |
| `severity` | string | Gravidade da contradicao (Low, Medium, High, Critical) |
| `possible_explanations` | list | Hipoteses para explicar a contradicao (minimo 2) |
| `reconciliation_status` | string | Status: Unresolved, Partially Resolved, Resolved, Accepted as Valid |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `data_quality_flag` | boolean | Se a contradicao pode ser causada por dados de baixa qualidade |
| `context_dependency` | text | Se a contradicao se resolve quando considerados contextos diferentes |
| `recommended_action` | text | Proximos passos para investigar ou resolver |
| `historical_pattern` | text | Se esta contradicao apareceu em assessments anteriores |
| `coach_notes` | text | Observacoes do coach ou analista sobre a contradicao |
| `resolution_evidence` | text | Evidencia que suporta a resolucao escolhida |
| `impact_on_profile` | text | Como a contradicao afeta a confianca geral do perfil |

## Exemplo Preenchido

```yaml
frameworks_involved:
  - "Big Five (NEO-PI-R)"
  - "DISC"
  - "Birkman"
nature_of_conflict: >
  Big Five indica Extroversao no percentil 28 (introvertido),
  mas o perfil DISC mostra estilo adaptado "I" alto (influente,
  sociavel). Birkman confirma necessidade de tempo sozinho.
  Ha discrepancia entre comportamento observado e disposicao natural.
severity: "Medium"
possible_explanations:
  - "Adaptacao profissional: a pessoa desenvolveu comportamento extrovertido para atender demandas do cargo"
  - "Diferenca entre estilo natural (introvertido) e estilo adaptado (extrovertido no trabalho)"
  - "O assessment DISC capturou o self adaptado, enquanto Big Five capturou o self natural"
reconciliation_status: "Partially Resolved"
context_dependency: >
  A contradicao se dissolve quando distinguimos contexto
  profissional (DISC adaptado) de disposicao natural (Big Five).
  Birkman confirma esta interpretacao ao mostrar necessidade
  oculta de isolamento.
recommended_action: >
  Validar com o avaliado em sessao de devolutiva. Explorar
  nivel de energia apos interacoes sociais prolongadas no
  trabalho. Verificar se ha sinais de burnout por adaptacao
  excessiva.
impact_on_profile: >
  Reduz confianca na camada de Estilo de Comunicacao do
  perfil. Recomenda-se diferenciar explicitamente entre
  estilo "quando esta no trabalho" vs "quando esta relaxado".
```

## Regras de Preenchimento

1. Toda contradicao deve listar no minimo 2 `possible_explanations` — nunca assumir uma causa unica.
2. A `severity` deve considerar o impacto na tomada de decisao, nao apenas a magnitude da diferenca.
3. Contradicoes de severidade "Critical" exigem investigacao antes de finalizar o perfil.
4. O `reconciliation_status` "Accepted as Valid" e legitimo — algumas contradicoes sao reais e refletem complexidade humana.
5. Nunca descartar uma contradicao sem investigacao. Mesmo que pareca erro de dados, documentar.
6. Quando a contradicao envolve self-report vs. observacao, dar peso maior a dados comportamentais.
7. Verificar se a contradicao segue algum Pattern conhecido (ex: Hidden Introvert Pattern).
8. Contradicoes recorrentes em assessments diferentes ao longo do tempo sao mais significativas.
9. O `impact_on_profile` deve ser explicito sobre quais decisoes sao afetadas.
10. Usar o Contradiction Card como insumo para sessoes de devolutiva — contradicoes geram conversas ricas.
