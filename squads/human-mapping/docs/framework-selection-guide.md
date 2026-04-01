# Guia de Seleção de Frameworks

## Visão Geral
Este guia orienta a escolha dos frameworks de avaliação mais adequados para cada
tipo de projeto, contexto e objetivo, considerando validade, custo e cobertura.

## Conteúdo

### Critérios de seleção
1. **Objetivo do projeto**: o que precisa ser avaliado?
2. **Validade psicométrica**: qual o rigor científico do instrumento?
3. **Cobertura**: quais dimensões o framework avalia?
4. **Disponibilidade**: o instrumento está acessível e licenciado?
5. **Custo-benefício**: o investimento justifica o ganho de informação?
6. **Complementaridade**: como se integra com outros frameworks já selecionados?

### Matriz de recomendação por objetivo
| Objetivo | Framework primário | Complementar |
|----------|-------------------|-------------|
| Perfil de personalidade | Big Five (NEO-PI-R) | MBTI, Eneagrama |
| Liderança | Hogan (HPI+HDS+MVPI) | CliftonStrengths |
| Composição de equipe | Belbin | DISC |
| Orientação vocacional | RIASEC | CliftonStrengths |
| Estilo de trabalho | Kolbe | DISC |
| Motivações e valores | Hogan MVPI | Eneagrama, Birkman |
| Comunicação | DISC | PCM, FIRO-B |

### Regras de ouro
- Sempre incluir pelo menos um framework baseado em traços (Big Five)
- Nunca usar apenas frameworks tipológicos para decisões críticas
- Documentar justificativa para cada framework selecionado
- Considerar o nível de confiança alvo antes de escolher

---

## Tabela de Decisão: Contexto → Frameworks Recomendados

Use esta tabela para selecionar frameworks com base no contexto específico do projeto:

| Contexto / Necessidade | Frameworks obrigatórios | Frameworks opcionais | Confiança esperada |
|------------------------|------------------------|---------------------|-------------------|
| Autoconhecimento geral | Big Five, Eneagrama | MBTI, CliftonStrengths | Alta (0.80+) |
| Seleção para cargo técnico | Big Five, Kolbe, DISC | Predictive Index | Alta (0.75+) |
| Seleção para cargo de liderança | Hogan (HPI+HDS+MVPI), Big Five | CliftonStrengths, DISC | Muito alta (0.85+) |
| Composição de equipe nova | Belbin, DISC, Big Five | CliftonStrengths | Alta (0.75+) |
| Resolução de conflito no time | DISC, FIRO-B, SDI | PCM, Eneagrama | Moderada (0.65+) |
| Orientação de carreira | RIASEC, CliftonStrengths, Big Five | Eneagrama, Reiss | Alta (0.75+) |
| Coaching executivo | Hogan (completo), Big Five, Eneagrama | MVPI, Kolbe | Muito alta (0.85+) |
| Desenvolvimento pessoal | VIA, CliftonStrengths, Eneagrama | Big Five | Moderada (0.70+) |
| Avaliação rápida (emergência) | Big Five, DISC | — | Moderada (0.60+) |

### Como usar a tabela
1. Identifique o contexto do projeto na primeira coluna
2. Inclua todos os frameworks obrigatórios no plano de avaliação
3. Adicione opcionais se houver tempo e dados disponíveis
4. Verifique se a confiança esperada atende ao threshold do projeto
5. Documente a justificativa de cada framework no plano de calibração

### Árvore de Decisão Rápida
```
O objetivo envolve liderança?
  SIM → Hogan (HPI+HDS+MVPI) + Big Five
  NÃO → O objetivo envolve equipe?
    SIM → Belbin + DISC + Big Five
    NÃO → O objetivo envolve carreira?
      SIM → RIASEC + CliftonStrengths + Big Five
      NÃO → Big Five + framework complementar por objetivo
```

> Para a árvore de decisão completa com todos os cenários e exceções, consulte
> `authority/decision-trees/framework-selection-decision-tree.md`.

## Referências
- `authority/framework-summaries/` — Resumos de cada framework
- `data/registries/framework-registry.yaml` — Catálogo de frameworks
- `docs/confidence-scoring-guide.md` — Sistema de confiança
- `authority/decision-trees/framework-selection-decision-tree.md` — Árvore completa
