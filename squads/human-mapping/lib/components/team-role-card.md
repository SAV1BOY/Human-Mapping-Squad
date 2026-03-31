---
type: component
squad: human-mapping
version: "2.0.0"
---

# Team Role Card

## Proposito

O Team Role Card documenta o papel que uma pessoa naturalmente assume em contextos de equipe, baseado em frameworks como Belbin Team Roles, Kolbe Action Modes ou derivado de convergencia entre multiplos assessments. Este card e essencial para composicao de equipes equilibradas e para que cada membro compreenda sua contribuicao unica e suas limitacoes previsiveis.

O conceito central e que equipes de alta performance nao precisam de pessoas perfeitas — precisam de papeis complementares.

## Estrutura do Card

O card foca na dinamica relacional: o que a pessoa contribui, o que pode falhar, quem a complementa e com quem pode haver friccao natural.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `role_name` | string | Nome do papel (ex: "Plant", "Implementer", "Coordinator") |
| `category` | string | Categoria do papel (Acao, Social, Cerebral — no modelo Belbin) |
| `contribution_style` | text | Como esta pessoa tipicamente contribui para o trabalho da equipe |
| `allowable_weakness` | text | Fraqueza previsivel e aceitavel associada a este papel |
| `complementary_roles` | list | Papeis que complementam este — necessarios para equilibrio |
| `conflict_with` | list | Papeis com os quais tende a gerar friccao natural |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `source_framework` | string | Framework de origem (ex: "Belbin", "Kolbe") |
| `secondary_role` | string | Segundo papel mais forte, se aplicavel |
| `avoided_role` | string | Papel que a pessoa evita naturalmente |
| `team_size_preference` | string | Tamanho ideal de equipe para este papel funcionar |
| `leadership_style` | text | Como este papel se manifesta em posicoes de lideranca |
| `remote_adaptation` | text | Como o papel se adapta em contextos de trabalho remoto |
| `kolbe_profile` | string | Perfil Kolbe associado (ex: "7-3-8-2") |

## Exemplo Preenchido

```yaml
role_name: "Plant"
category: "Cerebral"
contribution_style: >
  Gera ideias originais e abordagens nao-convencionais para
  problemas complexos. Funciona melhor quando tem liberdade
  para pensar de forma divergente sem restricoes imediatas
  de viabilidade. Traz inovacao para a equipe.
allowable_weakness: >
  Pode ignorar detalhes praticos e ter dificuldade em
  comunicar ideias de forma acessivel. Tende a se desengajar
  quando o trabalho se torna rotineiro ou excessivamente
  estruturado. Pode parecer "no mundo da lua".
complementary_roles:
  - "Implementer — transforma ideias em planos de acao"
  - "Monitor Evaluator — avalia viabilidade das ideias"
  - "Completer Finisher — garante execucao ate o final"
conflict_with:
  - "Shaper — pode perceber ideias como perda de tempo"
  - "Outro Plant — competicao por espaco criativo"
source_framework: "Belbin Team Roles"
secondary_role: "Resource Investigator"
avoided_role: "Completer Finisher"
leadership_style: >
  Lidera por visao e inspiracao, nao por controle. Funciona
  melhor como lider tecnico ou de inovacao do que como
  gestor operacional.
```

## Regras de Preenchimento

1. O `role_name` deve usar a nomenclatura oficial do framework de origem.
2. A `category` segue a classificacao do framework (Belbin: Acao, Social, Cerebral).
3. O `contribution_style` deve ser descrito em termos de valor para a equipe, nao apenas comportamento individual.
4. A `allowable_weakness` e um conceito central de Belbin — nao e um defeito a corrigir, mas uma consequencia natural do papel.
5. `complementary_roles` deve incluir explicacao breve de por que cada papel complementa.
6. `conflict_with` nao significa incompatibilidade — significa que a friccao e previsivel e gerenciavel.
7. Uma pessoa pode ter ate 3 papeis fortes — documentar principal e secundario.
8. Quando os dados vierem do Kolbe, traduzir os Action Modes para linguagem de papel em equipe.
9. Considerar o contexto remoto vs. presencial — alguns papeis se expressam diferente em cada formato.
10. Nunca usar o papel como justificativa para evitar desenvolvimento — "sou Plant, nao faco detalhes" nao e aceitavel.
