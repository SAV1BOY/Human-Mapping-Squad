---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Team Composition Analyzer

## Proposito

Analisar a composicao de uma equipe a partir dos perfis individuais dos membros, calculando cobertura de papeis, indice de diversidade, scores de compatibilidade e identificando gaps criticos. Este script e o motor analitico por tras do Team Dynamics Report.

## Input

- `team-members`: Lista de IDs dos membros da equipe
- `individual-profiles`: Perfis completos de cada membro (Layer Summary Cards de todas as camadas)
- `team-goal`: Objetivo principal da equipe (para ponderar papeis criticos)
- `team-type`: Classificacao da equipe (inovacao, execucao, estrategia, atendimento)

## Algoritmo

### Passo 1: Extrair Dados Relevantes de Cada Membro

Para cada membro, extrair:
```yaml
member_extract:
  name: ___
  belbin_roles: {primary: ___, secondary: ___, tertiary: ___}
  big_five: {O: ___, C: ___, E: ___, A: ___, N: ___}
  disc: {natural: ___, adapted: ___}
  sdi_mvs: ___
  sdi_conflict: [stage1, stage2, stage3]
  enneagram: {type: ___, wing: ___}
  clifton_top5: [___, ___, ___, ___, ___]
  pcm_base: ___
```

### Passo 2: Calcular Cobertura Belbin

```
Para cada um dos 9 papeis Belbin:
  - Contar quantos membros tem o papel como primario ou secundario
  - Classificar forca: Forte (primario), Moderado (secundario), Fraco (terciario), Ausente

Calcular role_coverage_score:
  - Base: (papeis cobertos / 9)
  - Bonus: +0.05 se papeis criticos para team_type estao todos cobertos
  - Penalidade: -0.10 por cada papel critico ausente
  - Penalidade: -0.05 por redundancia excessiva (3+ membros no mesmo papel primario)
```

### Passo 3: Calcular Indice de Diversidade Cognitiva

```
Para Big Five Openness:
  - Calcular range: max(O) - min(O)
  - Calcular distribuicao: membros no terco inferior (0-33), medio (34-66), superior (67-100)

diversity_index:
  - range_score: range / 100 (normalizado)
  - distribution_score: penalizar se algum terco tem 0 membros
  - final: (range_score * 0.6) + (distribution_score * 0.4)
```

### Passo 4: Calcular Compatibilidade de Comunicacao

```
Para cada par de membros (n*(n-1)/2 pares):
  - Comparar DISC natural de ambos
  - Compatibilidade DISC:
    - Mesmo quadrante: 0.8
    - Quadrantes adjacentes: 0.6
    - Quadrantes opostos: 0.3
    - Ajustar +0.1 se PCM bases sao compativeis

  - Comparar SDI MVS:
    - Mesmo MVS: 0.7 (entendimento natural mas redundancia)
    - MVS complementares: 0.8 (diversidade produtiva)
    - MVS conflitantes sem mediador: 0.3

pair_compatibility = media(disc_compat, sdi_compat)

team_communication_score = media de todos os pair_compatibility
```

### Passo 5: Calcular Alinhamento Motivacional

```
Extrair SDI MVS e Enneagram de todos os membros:
  - Contar distribuicao de MVS (Red, Blue, Green, Hub)
  - Identificar combinacoes de risco:
    - Todos Red: competicao destrutiva (-0.20)
    - Todos Blue: paralisia por consenso (-0.15)
    - Red + Blue sem Hub: atrito frequente (-0.10)
    - Diversidade equilibrada: bonus (+0.10)

  - Verificar Enneagram:
    - Multiplos tipo 3: risco de competicao
    - Multiplos tipo 9: risco de passividade
    - Mix saudavel: tipos diferentes com niveis de saude adequados

motivation_alignment = base_score + adjustments
```

### Passo 6: Identificar Gaps e Riscos

```
gaps = []
risks = []

Se papel Belbin critico ausente:
  gaps.append({type: "role_gap", detail: papel, severity: "high"})

Se diversity_index < 0.3:
  gaps.append({type: "cognitive_homogeneity", severity: "medium"})

Se algum pair_compatibility < 0.3:
  risks.append({type: "pair_conflict", members: [m1, m2], severity: "high"})

Se todos os membros tem Neuroticismo > 60:
  risks.append({type: "collective_anxiety", severity: "medium"})

Se nenhum membro tem DISC D > 50:
  risks.append({type: "no_driver", severity: contextual})
```

### Passo 7: Calcular Score Geral

```
composition_score = (
  role_coverage_score * 0.30 +
  diversity_index * 0.20 +
  motivation_alignment * 0.25 +
  team_communication_score * 0.25
)

classification:
  0.0-0.4: "Composicao Fragil"
  0.4-0.6: "Composicao Adequada"
  0.6-0.8: "Composicao Forte"
  0.8-1.0: "Composicao Excelente"
```

## Output

```yaml
team_composition_analysis:
  team_name: ___
  date: ___
  members_count: ___
  scores:
    role_coverage: ___
    cognitive_diversity: ___
    motivation_alignment: ___
    communication_compatibility: ___
    overall: ___
  classification: ___
  gaps: [___]
  risks: [___]
  pair_synergies: [{pair: [m1, m2], score: ___, reason: ___}]
  pair_conflicts: [{pair: [m1, m2], score: ___, reason: ___, mitigation: ___}]
  recommendations: [___]
```

## Limitacoes

- O algoritmo nao substitui julgamento humano — scores devem ser interpretados em contexto
- Compatibilidade calculada nao considera historico real de interacao entre os membros
- Diversidade cognitiva e medida apenas por Openness — outras dimensoes tambem contribuem
- Equipes menores que 4 pessoas terao naturalmente gaps Belbin — ajustar expectativa

## Especificacao de I/O

### Input
- Formato: YAML
- Campos obrigatorios: `team-members`, `individual-profiles`, `team-goal`, `team-type`
- Exemplo: `{team-members: ["M1","M2","M3"], team-goal: "lancar produto", team-type: "inovacao"}`

### Output
- Formato: YAML
- Campos: `composition_score`, `role_coverage`, `cognitive_diversity`, `motivation_alignment`, `communication_compatibility`, `gaps`, `risks`, `recommendations`

### Thresholds
- excelente: 0.8 (score >= 0.8)
- forte: 0.6 (score 0.6-0.8)
- adequada: 0.4 (score 0.4-0.6)
- fragil: 0.4 (score < 0.4)
- min_team_size: 3 (abaixo = warning sobre gaps naturais)
- redundancy_penalty: 3 (>= 3 membros no mesmo papel primario)

### Tratamento de Erros
- Input invalido: retornar erro `INVALID_TEAM_DATA` com membro especifico
- Dados insuficientes: calcular com dimensoes disponiveis e listar dimensoes ausentes
