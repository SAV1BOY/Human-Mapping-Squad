---
type: template
squad: human-mapping
version: "4.0.0"
used_by: [report-agent, synthesis-agent]
related_files:
  - frameworks/confidence-scoring-model.md
  - frameworks/cross-framework-reconciliation.md
  - templates/layers/trait-map-template.md
  - templates/layers/motivation-map-template.md
  - templates/audit/contradiction-map-template.md
  - templates/audit/confidence-map-template.md
---
# Executive Snapshot — Fillable Template

> Instrucoes: Resuma o perfil completo do respondente em uma unica pagina. Use linguagem clara e direta. Este documento deve ser compreensivel por qualquer stakeholder em menos de 5 minutos.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Data do assessment | Data em que o assessment foi conduzido | YYYY-MM-DD | _______________ |
| Contexto | Finalidade do assessment | Escolha: Pessoal / Profissional / Lideranca / Hiring / Team | _______________ |
| Profundidade | Nivel de profundidade executado | Escolha: /fast / /start / /deep | _______________ |
| Confidence geral | Score agregado do confidence-map | Decimal 0.00-1.00 (2 casas) | ___/1.0 |

---

## Quem Esta Pessoa E (Traits & Types)

**DEFINICAO:** 3 bullets descrevendo a essencia da personalidade — tracos dominantes e tipologia.

| Field | Description | Format | Max Length | Source |
|---|---|---|---|---|
| Bullet 1 | Traco mais saliente do perfil Big Five | "[Trait Framework]: [Finding with percentile/score]. [Behavioral implication]." | 25 words | `templates/layers/trait-map-template.md` — Big Five section |
| Bullet 2 | Segundo traco ou tipologia dominante | "[Type Framework]: [Specific finding]. [Behavioral implication]." | 25 words | trait-map or type/style map |
| Bullet 3 | Combinacao notavel ou traco diferenciador | "[Framework A + Framework B]: [Convergent pattern]. [Implication]." | 25 words | Cross-framework synthesis |

**FORMATO POR BULLET:** "[Trait/Type Framework]: [Specific finding with score]. [Behavioral implication]." Max 25 words per bullet.

- [Bullet 1: Traco mais saliente]
- [Bullet 2: Segundo traco ou tipologia]
- [Bullet 3: Combinacao notavel ou traco diferenciador]

> **EXEMPLO PREENCHIDO:**
> - Big Five Conscientiousness (percentil 88): Cumpre prazos consistentemente e organiza trabalho em sistemas. Confiavel para projetos complexos com multiplas dependencias.
> - Big Five Extraversion (percentil 55) com faceta Assertividade alta: Comunica-se com clareza em reunioes sem dominar. Equilibra escuta e direcao em equipes.
> - MBTI INTJ convergente com Big Five Openness (percentil 82): Pensamento estrategico orientado a inovacao. Excelente para planejamento de longo prazo.

---

## Como Esta Pessoa Age (Behaviors & Style)

**DEFINICAO:** 3 bullets descrevendo comportamentos observaveis no contexto de trabalho.

| Field | Description | Format | Max Length | Source |
|---|---|---|---|---|
| Bullet 1 | Estilo de comunicacao ou decisao | "[Style Framework]: [Specific pattern]. [Workplace implication]." | 25 words | type/style map |
| Bullet 2 | Modo de acao e ritmo de trabalho | "[Action Framework]: [Specific pattern]. [Workplace implication]." | 25 words | mode-of-action map (e.g. Kolbe) |
| Bullet 3 | Estilo interpessoal e dinamica de equipe | "[Team Framework]: [Specific pattern]. [Workplace implication]." | 25 words | team-role map (e.g. Belbin) |

**FORMATO POR BULLET:** "[Style Framework]: [Specific pattern]. [Workplace implication]." Max 25 words per bullet.

- [Bullet 1: Estilo de comunicacao/decisao]
- [Bullet 2: Modo de acao e ritmo de trabalho]
- [Bullet 3: Estilo interpessoal e dinamica de equipe]

> **EXEMPLO PREENCHIDO:**
> - DISC Style Di: Comunicacao direta e orientada a resultados, prefere emails concisos a reunioes. Acelera decisoes em ambientes de alta pressao.
> - Kolbe A Follow Thru (8): Trabalha sequencialmente, cria checklists e processos. Risco de lentidao em contextos que exigem pivots rapidos.
> - Belbin Monitor-Avaliador: Analisa opcoes criticamente antes de apoiar decisoes. Valioso em decisoes de alto risco, percebido como cauteloso.

---

## O Que Move Esta Pessoa (Motivation & Values)

**DEFINICAO:** 3 bullets descrevendo motivacoes intrinsecas e valores centrais.

| Field | Description | Format | Max Length | Source |
|---|---|---|---|---|
| Bullet 1 | Motivacao primaria identificada | "[Motivation Framework]: [Core driver]. [What energizes]." | 25 words | `templates/layers/motivation-map-template.md` |
| Bullet 2 | Valor central ou secundaria | "[Value Framework]: [Core driver]. [What energizes]." | 25 words | motivation-map |
| Bullet 3 | Energiza vs. drena | "[Framework]: [What energizes]. [What drains]." | 25 words | motivation-map |

**FORMATO POR BULLET:** "[Motivation Framework]: [Core driver]. [What energizes/drains]." Max 25 words per bullet.

- [Bullet 1: Motivacao primaria]
- [Bullet 2: Valor central]
- [Bullet 3: O que energiza vs. o que drena]

> **EXEMPLO PREENCHIDO:**
> - SDT Autonomia: Busca projetos onde define metodo e ritmo. Engajamento cai drasticamente sob microgerenciamento.
> - Drive Framework Maestria: Investe tempo extra em aperfeicoar habilidades. Responde bem a desafios de complexidade crescente.
> - Energizado por deep work tecnico; drenado por politica organizacional. Produtividade pico em sprints focados, precisa protecao contra reunioes.

---

## Onde Esta Pessoa Se Destaca (Strengths & Fit)

**DEFINICAO:** 2 bullets sobre pontos fortes convergentes e areas de melhor encaixe.

| Field | Description | Format | Max Length | Source |
|---|---|---|---|---|
| Bullet 1 | Top strength com framework de origem e contexto ideal | "[Strength Framework]: [Top strength]. [Best-fit context]." | 25 words | VIA, CliftonStrengths, or strength-map |
| Bullet 2 | Ambiente ou papel de melhor encaixe | "[Strength Framework]: [Strength cluster]. [Best-fit role/environment]." | 25 words | strength-map + career-fit |

- [Bullet 1: Top strength e contexto onde brilha]
- [Bullet 2: Ambiente/papel de melhor fit]

---

## Riscos e Pontos de Atencao

**DEFINICAO:** 2 bullets sobre derailers, shadow strengths e areas de cautela.

| Field | Description | Format | Max Length | Source |
|---|---|---|---|---|
| Bullet 1 | Risco principal | "[Risk source]: [Specific risk]. [Trigger condition]. [Suggested mitigation]." | 30 words | trait-map shadow, derailer analysis |
| Bullet 2 | Ponto de atencao secundario | "[Risk source]: [Specific risk]. [Trigger condition]. [Suggested mitigation]." | 30 words | cross-framework analysis |

**FORMATO POR BULLET:** "[Risk source]: [Specific risk]. [Trigger condition]." Max 30 words per bullet.

**REGRA CONDICIONAL:** Incluir 3o bullet se houver qualquer contradicao de severidade S3 ou S4 nao resolvida (ver `templates/audit/contradiction-map-template.md`).

- [Bullet 1: Risco principal]
- [Bullet 2: Ponto de atencao secundario]
- [Bullet 3 — CONDICIONAL: Somente se S3/S4 ativa] Contradicao nao resolvida entre [Framework A] e [Framework B] requer investigacao adicional.

**DECISAO:** Se nao ha derailers identificados, escrever: "Nenhum risco significativo identificado neste nivel de profundidade. Recomenda-se avaliacao /deep para analise completa."

---

## Resumo de Confianca

**DEFINICAO:** Tabela de confidence por aspecto avaliado.
**FORMATO:** Score decimal (0.00-1.00). Status segue `frameworks/confidence-scoring-model.md`.
**REGRA DE CLASSIFICACAO:**
- **Verde** = Score >= 0.70 (Alta/Muito Alta confianca) — resultado confiavel, usar livremente
- **Amarelo** = Score 0.50-0.69 (Moderada confianca) — usar com ressalvas no report
- **Vermelho** = Score < 0.50 (Baixa/Insuficiente) — layer considerada inconclusiva, requer ressalva obrigatoria

| Aspecto | Confidence | Status | Nota (se Amarelo/Vermelho) |
|---|---|---|---|
| Traits | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Types/Styles | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Motivation | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| Strengths | ___/1.0 | Verde/Amarelo/Vermelho | _______________ |
| **Geral** | **___/1.0** | **Verde/Amarelo/Vermelho** | _______________ |

**REGRA CONDICIONAL:** Adicionar linha para cada layer adicional avaliada (Team Role, Career Fit, etc.) se profundidade = /deep.

## Ressalvas

**DEFINICAO:** Limitacoes que afetam a interpretacao do snapshot.
**REGRA:** Obrigatorio incluir ao menos 1 ressalva se qualquer aspecto estiver Vermelho. Opcional para Amarelo.
**FORMATO:** Cada ressalva = 1 frase, max 20 words. Estrutura: "[Layer afetada] [limitacao] [recomendacao]."

- [Ressalva — ex: "Layer de Motivacao baseada em apenas 1 framework; recomenda-se validacao adicional"]

---

**Assessor:** _______________
**Session ID:** _______________
**Report gerado em:** YYYY-MM-DD

> Nota: Este e um resumo executivo. Para detalhes completos, consulte o Deep Persona Report (`templates/reports/deep-persona-report-template.md`). Resultados devem ser interpretados em conjunto com outros dados e observacoes contextuais.

---

## QUALITY CRITERIA

Um executive snapshot preenchido corretamente atende a TODOS os seguintes criterios:

1. **Completude:** Todos os campos obrigatorios preenchidos; nenhum placeholder "___" restante
2. **Concisao:** Nenhum bullet excede 25 words (30 para Riscos); snapshot inteiro cabe em 1 pagina
3. **Rastreabilidade:** Todo bullet cita framework de origem; todo score tem base de evidencia
4. **Consistencia:** Dados do snapshot sao consistentes com trait-map, motivation-map e confidence-map
5. **Confianca:** Tabela de confianca preenchida; ressalvas incluidas para Vermelho; condicional S3/S4 aplicado
6. **Acionabilidade:** Stakeholder consegue tomar decisao informada apenas com este documento

---

## EXEMPLO COMPLETO PREENCHIDO

**Nome:** Marina Costa Silva | **Data:** 2026-03-15 | **Contexto:** Profissional | **Profundidade:** /deep | **Confidence geral:** 0.78/1.0

**Quem Esta Pessoa E:**
- Big Five Conscientiousness (percentil 88): Cumpre prazos consistentemente, organiza trabalho em sistemas. Confiavel para projetos complexos com multiplas dependencias.
- Big Five Extraversion (percentil 28) com Assertividade moderada (percentil 52): Prefere trabalho individual mas se posiciona quando necessario. Eficaz em equipes pequenas.
- MBTI ISTJ convergente com Kolbe Fact Finder (7): Abordagem metodica baseada em dados. Ideal para analise, compliance e gestao de qualidade.

**Como Age:**
- DISC Style C: Comunicacao escrita e estruturada, produz documentos detalhados. Stakeholders apreciam clareza; pode parecer fria em contextos informais.
- Kolbe A Follow Thru (8): Trabalha sequencialmente com processos definidos. Alta previsibilidade de entrega; dificuldade em ambientes caoticos.
- Belbin Implementadora: Transforma planos em acoes concretas. Pilar de execucao da equipe.

**O Que Move:**
- SDT Autonomia + Drive Maestria: Busca profundidade tecnica e projetos com metodo proprio. Responde a oportunidades de especializacao.
- Schwartz Seguranca: Previsibilidade como valor central, prefere organizacoes estaveis. Risco de desengajamento em startups early-stage.
- Energizada por problemas estruturados; drenada por ambiguidade politica. Precisa de escopo claro para maximizar produtividade.

**Onde Se Destaca:**
- VIA Prudencia (#2) + Clifton Analytical (#1): Excelente em due diligence, auditoria e revisao de processos.
- Melhor fit em funcoes de analise em organizacoes estruturadas com progressao de carreira clara.

**Riscos:**
- Shadow Strength Perfeccionismo: Triggered por pressao de tempo com escopo ambiguo. Mitigar com definicao clara de "done" e timeboxing.
- Trait Rigidez (Openness baixa + Follow Thru alto): Triggered por reorganizacoes frequentes. Mitigar com comunicacao antecipada e tempo de adaptacao.

| Aspecto | Confidence | Status | Nota |
|---|---|---|---|
| Traits | 0.85/1.0 | Verde | — |
| Types/Styles | 0.75/1.0 | Verde | — |
| Motivation | 0.62/1.0 | Amarelo | Apenas 1 framework (SDT); sugere-se complementar |
| Strengths | 0.80/1.0 | Verde | — |
| **Geral** | **0.78/1.0** | **Verde** | — |

**Ressalvas:** Layer de Motivacao baseada em framework unico; confianca moderada neste aspecto.

**Assessor:** Agent-Synthesis-v2 | **Session ID:** HMS-2026-0315-042 | **Report gerado em:** 2026-03-15
