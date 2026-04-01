---
type: task
squad: human-mapping
version: "2.0.0"
agent: review-agent
workflow: review-workflow
---

# Task: Revisar Acurácia do Perfil com Feedback

## Objetivo

Revisar a acurácia do perfil gerado coletando feedback direto do respondente ou solicitante, ajustando resultados quando necessário e alimentando o sistema de aprendizado contínuo.

## Pré-condições

- Relatórios gerados e entregues ao respondente/solicitante
- Respondente disponível para sessão de feedback
- Session record completo com todos os dados de assessment

## Passos

1. Apresentar ao respondente um resumo dos principais achados do perfil
2. Solicitar feedback estruturado por dimensão:
   - "Numa escala de 1-5, quão preciso você considera este resultado?"
   - "O que ressoou mais com você?"
   - "O que não parece refletir quem você é?"
3. Registrar feedback por dimensão com score de acurácia percebida
4. Para dimensões com score < 3:
   - Solicitar explicação do respondente sobre a discrepância
   - Verificar se a discrepância pode ser explicada por viés de autoconhecimento
   - Registrar como ponto de investigação para revisão metodológica
5. Calcular taxa de acurácia geral da sessão:
   - Média ponderada dos scores de feedback por dimensão
   - Ponderar por confiança da camada (camadas com mais confiança têm mais peso)
6. Identificar padrões de discrepância:
   - Dimensões sistematicamente mal avaliadas em múltiplas sessões
   - Contextos onde a acurácia tende a ser menor
7. Registrar feedback no session record e na base de aprendizado
8. Gerar relatório de acurácia da sessão
9. Se acurácia < 60%, considerar revisão do perfil

## Outputs

- `accuracy-report`: Relatório de acurácia por dimensão
- `accuracy-score`: Score geral de acurácia percebida
- `discrepancy-notes`: Notas sobre discrepâncias identificadas
- `learning-data`: Dados para alimentar sistema de aprendizado

## Checklist de Conclusão

- [ ] Feedback coletado por dimensão
- [ ] Discrepâncias investigadas
- [ ] Taxa de acurácia calculada
- [ ] Padrões de discrepância identificados
- [ ] Dados registrados na base de aprendizado
- [ ] Relatório de acurácia gerado
- [ ] Session record finalizado

## Próxima Task

`tasks/review/update-methodology.md` — Atualizar metodologia (se necessário)

## Subtask Breakdown
1. **Apresentar achados-chave** — Agente: `review-agent`. Input: perfil integrado. Output: resumo apresentado ao respondente. Gate: resumo cobre dimensões principais.
2. **Coletar feedback estruturado** — Agente: `review-agent`. Input: escala 1-5 por dimensão. Output: scores de acurácia por dimensão. Gate: feedback coletado para >= 80% das dimensões.
3. **Investigar discrepâncias** — Agente: `review-agent`. Input: dimensões com score < 3. Output: `discrepancy-notes`. Gate: cada discrepância com explicação documentada.
4. **Calcular taxa de acurácia** — Agente: `review-agent`. Input: scores ponderados. Output: `accuracy-score`. Gate: score no range 0-100.
5. **Registrar na base de aprendizado** — Agente: `review-agent`. Input: feedback + padrões. Output: `learning-data`. Gate: dados persistidos na base.

## Quality Gate
- [ ] Feedback coletado por dimensão com scores 1-5
- [ ] Taxa de acurácia geral >= 60%
- Threshold: acurácia >= 60% para validar perfil; < 60% requer revisão
- Se FAIL: revisar perfil incorporando feedback antes de finalizar

## Rework Trigger
- Acurácia < 60% → retornar a `synthesize-profile` com dados de feedback
- Discrepância recorrente em dimensão → escalar para `calibrate-scoring`
