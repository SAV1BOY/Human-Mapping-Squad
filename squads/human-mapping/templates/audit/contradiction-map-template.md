---
type: template
squad: human-mapping
version: "3.0.0"
used_by: [audit-agent, synthesis-agent]
---
# Contradiction Map — Fillable Template

> Instrucoes: Documente todas as contradicoes entre frameworks e layers. Severidade segue a escala S1-S4 de `frameworks/cross-framework-reconciliation.md`. Impacto na confianca segue `frameworks/confidence-scoring-model.md`.

---

## Dados do Respondente

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| Nome | Nome completo do respondente | Texto, max 60 chars | _______________ |
| Session ID | Identificador unico | HMS-YYYY-MMDD-NNN | _______________ |
| Profundidade | Nivel de profundidade | Escolha: /fast / /start / /deep | _______________ |

---

## Escala de Severidade (Referencia: `frameworks/cross-framework-reconciliation.md`)

| Nivel | Nome | Criterio Quantitativo | Impacto na Confianca | Acao Requerida |
|---|---|---|---|---|
| **S1** | Leve | Desvio < 0.5 entre scores normalizados | -0.02 a -0.05 pontos | Documentar; nenhuma acao adicional |
| **S2** | Moderada | Desvio 0.5-1.0 entre scores normalizados | -0.05 a -0.10 pontos | Documentar + buscar explicacao contextual |
| **S3** | Severa | Desvio > 1.0 entre scores normalizados | -0.10 a -0.20 pontos | Investigacao obrigatoria; incluir ressalva no report |
| **S4** | Critica | Invalida conclusao de uma ou mais layers | -0.20 a -0.40 pontos (ou NO-GO) | Retestagem ou entrevista de validacao obrigatoria |

---

## Criterios de Resolucao

**DEFINICAO:** Uma contradicao e marcada como "Resolvida" quando TODOS os criterios abaixo sao atendidos:
1. **Investigacao documentada** — A causa raiz foi analisada e registrada no campo "Explicacao mais provavel"
2. **Explicacao plausivel** — A explicacao e consistente com pelo menos 1 fonte de evidencia externa (contexto, historico, teoria)
3. **Confidence ajustado** — O impacto na confianca foi calculado e aplicado no `templates/audit/confidence-map-template.md`

**Status possivel:**
- **Aberta** — Nenhum criterio atendido; investigacao pendente
- **Parcialmente resolvida** — Criterios 1 e 2 atendidos, mas confidence ainda nao ajustado
- **Resolvida** — Todos os 3 criterios atendidos

---

## Contradicoes Identificadas

### Contradicao #[N]

| Campo | Definicao | Formato | Valor |
|---|---|---|---|
| ID | Identificador sequencial | C-NNN | C-___ |
| Frameworks envolvidos | Os 2+ frameworks que divergem | "[Framework A] vs [Framework B]" | _______________ |
| Layer(s) afetada(s) | Quais layers do assessment sao impactadas | Lista de layers | _______________ |
| Natureza da contradicao | Descricao objetiva da divergencia | 1-2 frases: o que diz Framework A vs o que diz Framework B | _______________ |
| Severidade | Nivel S1-S4 conforme tabela acima | S1 / S2 / S3 / S4 + justificativa do nivel | _______________ |
| Possiveis explicacoes | Checkboxes de hipoteses | Marcar todas aplicaveis (ver abaixo) | |
| Explicacao mais provavel | Hipotese selecionada com justificativa | 2-3 frases com evidencia | _______________ |
| Status de resolucao | Estagio da investigacao | Aberta / Parcialmente resolvida / Resolvida | _______________ |
| Impacto na confianca | Pontos subtraidos do confidence score | -0.XX (dentro da faixa da severidade) | -___ pontos |

**Possiveis explicacoes (marcar todas aplicaveis):**
- [ ] **Trait genuino** — A pessoa realmente possui ambos os tracos (personalidade e complexa)
- [ ] **Adaptacao contextual** — Comportamento adaptado ao contexto profissional vs pessoal
- [ ] **Diferenca de construto** — Frameworks medem construtos diferentes apesar de nomes similares
- [ ] **Fase de transicao** — Mudanca ao longo do tempo (desenvolvimento pessoal)
- [ ] **Erro de medicao** — Problema com um dos instrumentos (dados insuficientes, resposta enviesada)
- [ ] **Outra:** _______________

> Copie esta secao inteira para cada contradicao adicional. Numere sequencialmente: C-001, C-002, C-003...

---

## Tabela Resumo de Contradicoes

| ID | Frameworks | Layer(s) | Severidade | Explicacao | Status | Impacto |
|---|---|---|---|---|---|---|
| C-001 | | | S_ | | | -0.__ |
| C-002 | | | S_ | | | -0.__ |
| C-003 | | | S_ | | | -0.__ |

---

## Analise de Padroes

| Pergunta | Definicao | Formato | Resposta |
|---|---|---|---|
| Concentracao por layer? | Contradicoes se acumulam em alguma layer? | Nome da layer + contagem | _______________ |
| Framework divergente? | Algum framework consistentemente diverge dos demais? | Nome do framework + frequencia | _______________ |
| Padrao de adaptacao? | Divergencias sugerem persona profissional vs pessoal? | Sim/Nao + evidencia em 1 frase | _______________ |
| Fase de transicao? | Divergencias sugerem mudanca pessoal recente? | Sim/Nao + evidencia em 1 frase | _______________ |

---

## Impacto Agregado na Confianca

| Metrica | Formato | Valor |
|---|---|---|
| Total de contradicoes | Inteiro | ___ |
| Contradicoes S3+S4 | Inteiro (estas exigem acao) | ___ |
| Contradicoes resolvidas | Inteiro / Total | ___/___ |
| Reducao total no confidence | Soma dos impactos individuais | -0.___ |
| Layers mais afetadas | Layers com maior impacto acumulado | _______________ |

**REGRA:** Se qualquer contradicao S4 estiver com status "Aberta", o assessment recebe flag NO-GO no confidence-map ate resolucao.

---

## Recomendacoes

**REGRA DE DECISAO:** Marcar com base na severidade maxima encontrada:
- **S1 apenas:** Marcar opcao 1
- **S2 presente:** Marcar opcoes 1 + 5
- **S3 presente:** Marcar opcoes 2 + 4 + 5
- **S4 presente:** Marcar opcoes 3 + 4 + 5

- [ ] Nenhuma acao necessaria — contradicoes menores e explicaveis
- [ ] Investigacao adicional necessaria para contradicoes especificas: _______________
- [ ] Retestagem recomendada em frameworks: _______________
- [ ] Entrevista de validacao com o respondente recomendada
- [ ] Incluir ressalvas no report final

---

## EXEMPLO PREENCHIDO — Contradicao Big Five E baixo + MBTI ENFP

### Contradicao #1

| Campo | Valor |
|---|---|
| ID | C-001 |
| Frameworks envolvidos | Big Five (NEO-PI-R) vs MBTI (Form M) |
| Layer(s) afetada(s) | Traits, Types/Styles |
| Natureza da contradicao | Big Five Extraversion no percentil 25 (baixo) indica preferencia por solitude e ambientes calmos. MBTI tipifica como ENFP, onde E (Extraversion) indica orientacao para o mundo externo e energizacao por interacao social. Direcoes opostas no mesmo construto. |
| Severidade | S3 (Severa) — Desvio > 1.0 padrao entre scores normalizados do mesmo construto. Percentil 25 em Big Five E corresponde a z=-0.67; ENFP com preferencia clara de E corresponde a z~+0.5. Delta = 1.17. |
| Explicacao mais provavel | Adaptacao contextual: respondente trabalha em funcao de vendas (MBTI reflete persona profissional extrovertida) mas naturalmente prefere solitude (Big Five captura tendencia basal). Evidencia: auto-relato de "exaustao apos eventos sociais longos" converge com Big Five baixo. |
| Status de resolucao | Resolvida |
| Impacto na confianca | -0.12 pontos |

**Possiveis explicacoes:**
- [ ] Trait genuino
- [x] **Adaptacao contextual** — Persona profissional extrovertida vs tendencia basal introvertida
- [x] **Diferenca de construto** — MBTI E/I mede orientacao de energia; Big Five E mede sociabilidade + assertividade + emocoes positivas
- [ ] Fase de transicao
- [ ] Erro de medicao

**Resolucao documentada:** Investigacao revelou que MBTI E pode refletir assertividade (faceta de E no Big Five em percentil 62, acima da media) e entusiasmo profissional, enquanto Big Five E global e puxado para baixo por Gregariousness (percentil 15) e Warmth (percentil 30). A contradicao e parcialmente um artefato de construtos diferentes — MBTI E nao requer alta sociabilidade. Confidence da layer Traits ajustado de 0.82 para 0.70; confidence de Types/Styles ajustado de 0.75 para 0.68.
