# Card: Convergência Cross-Framework

## Objetivo

Documentar e visualizar pontos onde múltiplos frameworks de assessment concordam, aumentando a confiança na interpretação e identificando insights robustos.

## Estrutura do Card

```yaml
convergence_card:
  respondente: "[Nome ou código]"
  data_analise: "[DD/MM/AAAA]"

  convergencias:
    - achado: "[Descrição do achado convergente]"
      frameworks_concordantes:
        - nome: "[Framework 1]"
          evidencia: "[Dado específico que aponta para este achado]"
        - nome: "[Framework 2]"
          evidencia: "[Dado específico que aponta para este achado]"
        - nome: "[Framework 3 — se aplicável]"
          evidencia: "[Dado específico]"
      forca_convergencia: "[Forte / Moderada / Fraca]"
      boost_confianca: "[+15% / +10% / +5%]"
      confianca_final: "[Alta / Média / Baixa]"
      implicacao_pratica: "[O que isso significa para o respondente]"
```

## Regras de Classificação

### Força de Convergência

| Nível | Critério | Boost de Confiança |
|-------|----------|-------------------|
| **Forte** | 3+ frameworks concordam sem ambiguidade | +15% sobre a confiança base |
| **Moderada** | 2 frameworks concordam claramente OU 3+ com alguma nuance | +10% |
| **Fraca** | 2 frameworks com concordância parcial ou indireta | +5% |

### Tipos de Convergência

1. **Convergência Direta**: Frameworks medem construtos similares e concordam
   - Ex: Extroversão alta (Big Five) + perfil D/I alto (DISC) + Communication no top-5 (Clifton)

2. **Convergência Complementar**: Frameworks medem construtos diferentes que se reforçam
   - Ex: Eneatipo 5 (recolhimento) + Introversão (Big Five) + Quick Start baixo (Kolbe)

3. **Convergência Contextual**: Concordância emerge quando se considera o contexto
   - Ex: Conscienciosidade alta + Eneatipo 1 — convergem no contexto de padrões elevados

## Convergências Comuns e Seus Significados

### Perfil "Líder Natural"
| Framework | Indicador |
|-----------|-----------|
| Big Five | Extroversão alta + Conscienciosidade alta |
| DISC | Perfil D ou DI |
| CliftonStrengths | Command / Strategic / Achiever no top-5 |
| Eneatipo | 3 ou 8 |
| Significado | Tendência consistente a assumir liderança e buscar resultados |

### Perfil "Pensador Profundo"
| Framework | Indicador |
|-----------|-----------|
| Big Five | Abertura alta + Introversão |
| DISC | Perfil C ou CS |
| CliftonStrengths | Analytical / Intellection / Strategic |
| Kolbe | Fact Finder alto |
| Significado | Preferência consistente por análise profunda antes de ação |

### Perfil "Conector Social"
| Framework | Indicador |
|-----------|-----------|
| Big Five | Amabilidade alta + Extroversão alta |
| DISC | Perfil I ou IS |
| CliftonStrengths | Woo / Empathy / Harmony |
| Eneatipo | 2 ou 7 |
| Significado | Orientação consistente para pessoas e relacionamentos |

## Quando a Convergência NÃO Aumenta Confiança

- **Redundância metodológica**: Frameworks que medem exatamente o mesmo construto com métodos similares — concordância é esperada, não informativa
- **Efeito halo**: Respondente com alta desejabilidade social pode distorcer múltiplos frameworks na mesma direção
- **Viés do facilitador**: Interpretações subjetivas podem "forçar" convergência onde ela não existe objetivamente

## Visualização Sugerida

```
[Achado Central]
    ├── Framework A: evidência ████████ (forte)
    ├── Framework B: evidência ██████ (moderada)
    └── Framework C: evidência ████████ (forte)

    Convergência: FORTE | Boost: +15% | Confiança Final: ALTA
```

## Integração com Outros Cards

| Card | Relação |
|------|---------|
| Contradiction Card | Convergências e contradições são complementares — mapear ambos |
| Confidence Card | Boost de convergência alimenta o score final de confiança |
| Session Summary | Convergências fortes devem aparecer nos achados principais |
| Risk Flag Card | Ausência de convergência pode ser um flag de risco |
