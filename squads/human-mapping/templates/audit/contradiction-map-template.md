---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [audit-agent, synthesis-agent]
related_files:
  - frameworks/cross-framework-reconciliation.md
  - frameworks/confidence-scoring-model.md
  - templates/audit/confidence-map-template.md
  - templates/reports/executive-snapshot-template.md
  - templates/reports/deep-persona-report-template.md
---
# Contradiction Map — Fillable Template

> Instrucoes: Documente TODAS as contradicoes identificadas entre frameworks e layers. Para cada contradicao, classifique a severidade usando a escala S1-S4 (de `frameworks/cross-framework-reconciliation.md`), analise possiveis explicacoes, e determine o impacto na confianca.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico da sessao | HMS-YYYY-MMDD-NNN | _______________ |
| Profundidade | Nivel de profundidade executado | Escolha: /fast / /start / /deep | _______________ |
| Data | Data do assessment | YYYY-MM-DD | _______________ |
| Total de frameworks utilizados | Quantidade de frameworks no assessment | Inteiro | ___ |

---

## Escala de Severidade (S1-S4)

> Referencia: `frameworks/cross-framework-reconciliation.md`

| Nivel | Nome | Definicao | Impacto no Confidence | Acao Requerida |
|---|---|---|---|---|
| **S1** | Baixa | Frameworks medem construtos DIFERENTES com baixa sobreposicao esperada. Divergencia e normal e esperada. | -0.05 | Documentar; nenhuma acao adicional |
| **S2** | Media | Frameworks medem construtos RELACIONADOS com concordancia moderada esperada. Divergencia requer explicacao. | -0.10 | Documentar + explicacao obrigatoria |
| **S3** | Alta | Frameworks medem o MESMO construto com concordancia forte esperada. Divergencia e anomala. | -0.15 | Documentar + explicacao + revisao pelo chief |
| **S4** | Critica | MESMO framework contradiz a si mesmo internamente. Possivel erro de medicao ou resposta inconsistente. | -0.20 | Documentar + investigacao obrigatoria + considerar retestagem |

**REGRA DE DECISAO:**
- S1-S2: Contradicoes podem ser resolvidas pelo agente com explicacao documentada
- S3: Requer revisao pelo chief-agent antes de prosseguir
- S4: Bloqueia finalizacao do report ate investigacao completa

---

## Tabela de Contradicoes

> Copie o bloco abaixo para cada contradicao detectada. Numere sequencialmente (C-001, C-002, ...).

### Contradicao #1

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| ID | Identificador unico da contradicao | C-NNN | C-001 |
| Framework A | Primeiro framework envolvido | Nome do framework + construto especifico | _______________ |
| Framework B | Segundo framework envolvido | Nome do framework + construto especifico | _______________ |
| Achado em A | O que o Framework A indica | Score/tipo + interpretacao em 1 frase | _______________ |
| Achado em B | O que o Framework B indica | Score/tipo + interpretacao em 1 frase | _______________ |
| Natureza | Descricao da contradicao em 1-2 frases | Max 30 words. O que contradiz o que? | _______________ |
| Severidade | Nivel S1-S4 conforme escala acima | S1 / S2 / S3 / S4 | ___ |
| Impacto no confidence | Reducao no score de confianca | Decimal negativo conforme tabela: S1=-0.05, S2=-0.10, S3=-0.15, S4=-0.20 | -___ |

**Possiveis explicacoes** (marcar todas as aplicaveis):
- [ ] Trait genuino — A pessoa realmente possui ambos os tracos (ex: introvertido socialmente competente)
- [ ] Adaptacao — Comportamento adaptado ao contexto profissional vs. pessoal
- [ ] Contexto — Frameworks medem em contextos/situacoes diferentes
- [ ] Phase — Mudanca ao longo do tempo (desenvolvimento pessoal, maturidade)
- [ ] Erro de medicao — Problema com um dos instrumentos (validade, administracao)
- [ ] Outra: _______________

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Explicacao mais provavel | Explicacao selecionada acima com justificativa | 1-2 frases. Max 40 words. | _______________ |
| Evidencia para explicacao | Dados que suportam a explicacao escolhida | Referencia a scores, facetas, ou dados contextuais | _______________ |
| Status | Estado atual da resolucao | Aberta / Parcialmente resolvida / Resolvida | _______________ |
| Layer(s) afetada(s) | Quais layers do assessment sao impactadas | Lista (ex: Traits, Types/Styles) | _______________ |

**CRITERIO DE RESOLUCAO:** Uma contradicao e considerada "Resolvida" quando TODOS os seguintes criterios sao atendidos:
1. Explicacao documentada com evidencia
2. Confidence score ajustado conforme impacto S1-S4
3. Revisao pelo chief (obrigatorio para S3-S4)

---

### Contradicao #2

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| ID | Identificador unico | C-NNN | C-002 |
| Framework A | Primeiro framework | Nome + construto | _______________ |
| Framework B | Segundo framework | Nome + construto | _______________ |
| Achado em A | Indicacao do Framework A | Score/tipo + 1 frase | _______________ |
| Achado em B | Indicacao do Framework B | Score/tipo + 1 frase | _______________ |
| Natureza | Descricao da contradicao | Max 30 words | _______________ |
| Severidade | S1 / S2 / S3 / S4 | ___ |
| Impacto no confidence | -0.05 / -0.10 / -0.15 / -0.20 | -___ |

**Possiveis explicacoes:**
- [ ] Trait genuino
- [ ] Adaptacao
- [ ] Contexto
- [ ] Phase
- [ ] Erro de medicao
- [ ] Outra: _______________

| Campo | Valor |
|---|---|
| Explicacao mais provavel | _______________ |
| Evidencia | _______________ |
| Status | Aberta / Parcialmente resolvida / Resolvida |
| Layer(s) afetada(s) | _______________ |

---

### Contradicao #3

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| ID | Identificador unico | C-NNN | C-003 |
| Framework A | Primeiro framework | Nome + construto | _______________ |
| Framework B | Segundo framework | Nome + construto | _______________ |
| Achado em A | Indicacao do Framework A | Score/tipo + 1 frase | _______________ |
| Achado em B | Indicacao do Framework B | Score/tipo + 1 frase | _______________ |
| Natureza | Descricao da contradicao | Max 30 words | _______________ |
| Severidade | S1 / S2 / S3 / S4 | ___ |
| Impacto no confidence | -0.05 / -0.10 / -0.15 / -0.20 | -___ |

**Possiveis explicacoes:**
- [ ] Trait genuino
- [ ] Adaptacao
- [ ] Contexto
- [ ] Phase
- [ ] Erro de medicao
- [ ] Outra: _______________

| Campo | Valor |
|---|---|
| Explicacao mais provavel | _______________ |
| Evidencia | _______________ |
| Status | Aberta / Parcialmente resolvida / Resolvida |
| Layer(s) afetada(s) | _______________ |

> **NOTA:** Adicionar blocos adicionais (C-004, C-005, ...) conforme necessario, seguindo o mesmo formato.

---

## Tabela Resumo de Contradicoes

| ID | Framework A | Framework B | Severidade | Explicacao | Status | Impacto |
|---|---|---|---|---|---|---|
| C-001 | _______________ | _______________ | S_ | _______________ | _______________ | -___ |
| C-002 | _______________ | _______________ | S_ | _______________ | _______________ | -___ |
| C-003 | _______________ | _______________ | S_ | _______________ | _______________ | -___ |

---

## Analise de Padroes

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Contradicoes por layer | Em qual layer as contradicoes se concentram? | Lista com contagem (ex: "Traits: 2, Types: 1") | _______________ |
| Framework mais divergente | Qual framework mais frequentemente aparece em contradicoes? | Nome do framework + contagem | _______________ |
| Padrao de adaptacao contextual? | As contradicoes sugerem que a pessoa age diferente em contextos diferentes? | Sim (descrever) / Nao | _______________ |
| Padrao de transicao pessoal? | As contradicoes sugerem mudanca recente na pessoa? | Sim (descrever) / Nao | _______________ |

---

## Impacto Agregado na Confianca

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Total de contradicoes | Quantidade total detectada | Inteiro | ___ |
| Contradicoes S3-S4 | Quantidade de criticas/altas | Inteiro | ___ |
| Contradicoes resolvidas | Quantidade com resolucao documentada | Inteiro (frac do total) | ___/___ |
| Reducao total no confidence | Soma de todos os impactos S1-S4 | Decimal negativo | -___ |
| Layers mais afetadas | Layers com maior concentracao de contradicoes | Lista ordenada | _______________ |

**REGRA DE DECISAO:**
- Se reducao total > -0.30: Report requer secao especial de ressalvas
- Se qualquer S4 aberta: Report NAO pode ser finalizado
- Se todas resolvidas e reducao < -0.15: Impacto considerado gerenciavel

---

## Recomendacoes

**REGRA:** Marcar TODAS as aplicaveis. Ao menos 1 deve ser marcada.

- [ ] Nenhuma acao necessaria — todas as contradicoes sao S1 e explicaveis
- [ ] Investigacao adicional necessaria para contradicoes S2+ especificas: _______________
- [ ] Retestagem recomendada em frameworks: _______________
- [ ] Entrevista de validacao com o respondente recomendada (indicada se >= 2 contradicoes S3+)
- [ ] Incluir ressalvas no report final (obrigatorio se qualquer S3+ nao resolvida)
- [ ] Escalacao ao chief-agent (obrigatorio se qualquer S4 detectada)

---

## QUALITY CRITERIA

Um contradiction map preenchido corretamente atende a TODOS os seguintes criterios:

1. **Completude:** Toda contradicao detectada esta documentada; nenhuma omitida
2. **Severidade correta:** Classificacao S1-S4 segue definicoes da escala (nao e subjetiva)
3. **Impacto calculado:** Todo impacto no confidence segue tabela fixa (S1=-0.05, S2=-0.10, S3=-0.15, S4=-0.20)
4. **Resolucao documentada:** Cada contradicao tem explicacao + evidencia + status
5. **Padroes analisados:** Secao de padroes preenchida (mesmo se "nenhum padrao identificado")
6. **Recomendacoes coerentes:** Recomendacoes sao consistentes com severidade e status

---

## EXEMPLO PREENCHIDO — Contradicao Big Five Extraversion vs MBTI

### Contradicao #1 (EXEMPLO)

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| ID | Identificador unico | C-NNN | C-001 |
| Framework A | Primeiro framework | Nome + construto | Big Five — Extraversion |
| Framework B | Segundo framework | Nome + construto | MBTI — E/I Preference |
| Achado em A | Indicacao do Framework A | Score/tipo + 1 frase | Extraversion percentil 28 — indica introversao clara, baixa gregariousness e baixa busca por estimulacao social |
| Achado em B | Indicacao do Framework B | Score/tipo + 1 frase | MBTI tipo ENFP — indica preferencia por Extroversion, energia obtida de interacao com pessoas e ideias externas |
| Natureza | Descricao da contradicao | Max 30 words | Big Five indica introversao forte (percentil 28) enquanto MBTI classifica como Extrovertido (ENFP). Construtos sobrepostos medem direcao de energia de formas diferentes. |
| Severidade | S1 / S2 / S3 / S4 | S3 |
| Impacto no confidence | Decimal negativo | -0.15 |

**Possiveis explicacoes:**
- [x] Trait genuino — A pessoa realmente possui ambos os tracos (ex: introvertido socialmente competente)
- [ ] Adaptacao
- [x] Contexto — Frameworks medem em contextos/situacoes diferentes
- [ ] Phase
- [ ] Erro de medicao
- [ ] Outra

| Campo | Valor |
|---|---|
| Explicacao mais provavel | Trait genuino + Contexto: Respondente possui baixa gregariousness (Big Five faceta) mas alta orientacao a ideias externas (MBTI Ne). A Extraversion do Big Five enfatiza socialidade; o E/I do MBTI enfatiza direcao da atencao cognitiva. |
| Evidencia | Faceta Gregariousness = percentil 18 (muito baixa), mas faceta Ideas (Openness) = percentil 89. MBTI N forte (Intuicao) explica classificacao como E via preferencia por brainstorming externo, nao socialidade. |
| Status | Resolvida |
| Layer(s) afetada(s) | Traits, Types/Styles |

**Resumo do exemplo na tabela:**

| ID | Framework A | Framework B | Severidade | Explicacao | Status | Impacto |
|---|---|---|---|---|---|---|
| C-001 | Big Five Extraversion | MBTI E/I | S3 | Construtos sobrepostos mas nao identicos; gregariousness vs direcao cognitiva | Resolvida | -0.15 |
