---
type: component
squad: human-mapping
version: "2.0.0"
---

# Type Card

## Proposito

O Type Card representa o resultado de um assessment baseado em tipologia — frameworks que classificam pessoas em categorias discretas ao inves de escalas continuas. Exemplos incluem MBTI, DISC, Eneagrama e Birkman. O card captura o tipo atribuido, suas caracteristicas centrais e padroes de comportamento sob condicoes normais e de estresse.

## Estrutura do Card

O card organiza informacoes do tipo atribuido com foco em aplicabilidade pratica: como a pessoa se comunica, como reage sob pressao e qual o nivel de confianca na classificacao.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `framework` | string | Framework tipologico utilizado (ex: "MBTI", "DISC", "Eneagrama") |
| `type_assigned` | string | Tipo ou estilo atribuido (ex: "INTJ", "Di", "Tipo 5") |
| `confidence` | float (0-1.0) | Confianca na classificacao — especialmente relevante para tipos proximos ao limiar |
| `key_characteristics` | list | 3-5 caracteristicas comportamentais centrais deste tipo |
| `communication_preference` | text | Como esta pessoa prefere se comunicar e ser comunicada |
| `stress_pattern` | text | Como o comportamento muda sob pressao ou estresse prolongado |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `subtype` | string | Variacao dentro do tipo (ex: asa do Eneagrama, subtipo instintivo) |
| `adjacent_types` | list | Tipos proximos que a pessoa quase recebeu |
| `growth_direction` | string | Direcao de crescimento segundo o framework |
| `stress_direction` | string | Direcao de desintegracao sob estresse |
| `famous_examples` | list | Exemplos conhecidos do mesmo tipo (uso didatico) |
| `team_dynamics` | text | Como este tipo tipicamente interage em equipe |
| `natural_vs_adapted` | object | Diferenca entre estilo natural e estilo adaptado (ex: DISC) |
| `assessment_date` | date | Data da avaliacao |

## Exemplo Preenchido

```yaml
framework: "Eneagrama"
type_assigned: "Tipo 5 - O Investigador"
confidence: 0.79
key_characteristics:
  - "Necessidade intensa de compreender antes de agir"
  - "Preferencia por autonomia e espaco pessoal"
  - "Capacidade analitica profunda"
  - "Tendencia a minimizar necessidades emocionais"
communication_preference: >
  Prefere comunicacao escrita e estruturada. Valoriza dados e
  evidencias. Precisa de tempo para processar antes de responder.
  Reunioes sem pauta definida sao desgastantes.
stress_pattern: >
  Sob pressao, tende a se isolar e acumular informacoes sem
  compartilhar. Pode parecer distante ou desengajado. Em estresse
  extremo, move para comportamentos do Tipo 7 — dispersao e
  planejamento excessivo sem execucao.
subtype: "Subtipo social (5w6)"
growth_direction: "Integracao para Tipo 8 — assertividade e acao"
```

## Regras de Preenchimento

1. O `framework` deve ser explicitado — nunca assumir que o leitor sabe qual sistema esta sendo usado.
2. A `confidence` em tipologias tende a ser menor que em tracos dimensionais. Valores abaixo de 0.65 exigem flag de incerteza.
3. Quando a pessoa pontua proximo ao limiar entre dois tipos, listar ambos em `adjacent_types` e documentar.
4. O `stress_pattern` e obrigatorio porque e a informacao mais acionavel para gestores e coaches.
5. A `communication_preference` deve ser pratica — algo que um colega possa usar imediatamente.
6. Nunca tratar o tipo como identidade fixa. Incluir nota sobre fluidez quando relevante.
7. Para DISC e Birkman, sempre capturar `natural_vs_adapted` — a diferenca entre os dois e clinicamente relevante.
8. Evitar estereotipos — cada tipo tem expressoes saudaveis e nao-saudaveis.
9. Se o assessment oferecer subtipagem (ex: asas do Eneagrama), registrar mesmo que com baixa confianca.
10. Cross-reference com Trait Cards quando possivel para validar convergencia.
