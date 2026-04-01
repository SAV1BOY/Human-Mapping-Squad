---
type: task
squad: human-mapping
version: "2.0.0"
agent: review-agent
workflow: review-workflow
---

# Task: Atualizar Metodologia

## Objetivo

Atualizar a metodologia de assessment com base nos aprendizados acumulados de sessões anteriores, feedback de acurácia e novas evidências científicas, garantindo melhoria contínua do processo.

## Pré-condições

- Dados de acurácia de múltiplas sessões disponíveis
- Padrões de discrepância identificados na revisão
- Trigger: acurácia média caindo abaixo de 75% ou acúmulo de 10+ sessões sem revisão

## Passos

1. Compilar dados de acurácia das últimas N sessões (mínimo 10)
2. Analisar padrões de discrepância:
   - Quais dimensões têm acurácia consistentemente baixa?
   - Quais contextos (contratação, equipe, etc.) têm mais problemas?
   - Quais frameworks geram mais contradições?
3. Identificar possíveis causas-raiz:
   - Perguntas ambíguas ou culturalmente enviesadas
   - Algoritmos de scoring com calibração inadequada
   - Mapeamentos entre frameworks imprecisos
   - Viés de desejabilidade social subcorrigido
4. Propor ajustes metodológicos:
   - Revisão de perguntas problemáticas no banco de perguntas
   - Recalibração de algoritmos de scoring
   - Ajuste nos mapeamentos cross-framework
   - Refinamento dos fatores de correção de viés
5. Documentar cada mudança proposta com:
   - Evidência que suporta a mudança
   - Impacto esperado
   - Risco de regressão
6. Submeter propostas para revisão do squad lead
7. Após aprovação, implementar mudanças nos scripts e bancos de perguntas
8. Atualizar documentação de metodologia em `docs/methodology/`
9. Incrementar versão da metodologia no `config.yaml`

## Outputs

- `methodology-review`: Documento de revisão metodológica
- `proposed-changes`: Lista de mudanças propostas com justificativas
- `implementation-plan`: Plano de implementação das mudanças
- `version-update`: Nova versão da metodologia

## Checklist de Conclusão

- [ ] Dados de acurácia compilados e analisados
- [ ] Padrões de discrepância mapeados
- [ ] Causas-raiz identificadas
- [ ] Ajustes propostos e documentados
- [ ] Propostas submetidas para aprovação
- [ ] Mudanças implementadas (após aprovação)
- [ ] Documentação atualizada
- [ ] Versão incrementada

## Próxima Task

`tasks/review/calibrate-scoring.md` — Calibrar scoring

## Subtask Breakdown
1. **Compilar dados de acurácia** — Agente: `review-agent`. Input: últimas N sessões (min 10). Output: análise estatística por dimensão. Gate: >= 10 sessões compiladas.
2. **Analisar padrões de discrepância** — Agente: `review-agent`. Input: dados compilados. Output: dimensões e contextos problemáticos. Gate: padrões identificados e documentados.
3. **Identificar causas-raiz** — Agente: `review-agent`. Input: padrões + scripts + bancos de perguntas. Output: causas-raiz com evidências. Gate: cada causa com evidência estatística.
4. **Propor e documentar ajustes** — Agente: `review-agent`. Input: causas-raiz. Output: `proposed-changes` com impacto esperado. Gate: cada mudança com evidência e risco documentados.
5. **Implementar e versionar** — Agente: `review-agent`. Input: propostas aprovadas. Output: scripts e docs atualizados + versão incrementada. Gate: aprovação do squad lead obtida.

## Quality Gate
- [ ] >= 10 sessões analisadas estatisticamente
- [ ] Causas-raiz documentadas com evidências
- Threshold: mudanças propostas devem melhorar acurácia em >= 5%
- Se FAIL: adiar mudanças e acumular mais dados

## Rework Trigger
- Mudança implementada piora acurácia → reverter e reanalisar
- Dados insuficientes (< 10 sessões) → adiar revisão e aguardar mais dados
