---
type: task
squad: human-mapping
version: "2.0.0"
agent: audit-agent
workflow: audit-workflow
---

# Task: Reconciliar Conflitos entre Frameworks

## Objetivo

Resolver as contradições identificadas na auditoria, determinando qual interpretação prevalece em cada caso e documentando a lógica de reconciliação para transparência.

## Pré-condições

- Auditoria de contradições concluída (`audit-contradictions.md`)
- Relatório de contradições com prioridades disponível
- Dados brutos de todas as camadas acessíveis

## Passos

1. Carregar relatório de contradições e ordenar por prioridade
2. Para cada contradição crítica, aplicar protocolo de reconciliação:
   a. Verificar qual framework tem maior confiança naquela dimensão
   b. Verificar qual resultado é mais consistente com o restante do perfil
   c. Verificar se há dados brutos que suportam uma interpretação sobre a outra
   d. Considerar o contexto da sessão (viés detectado, estilo de resposta)
3. Executar `scripts/analysis/cross-framework-aligner.md` para verificar alinhamentos
4. Aplicar regras de precedência quando necessário:
   - Dados comportamentais (respostas STAR) > autodeclaração
   - Framework com mais datapoints > framework com menos
   - Resultado consistente com 3+ frameworks > resultado isolado
5. Para contradições que refletem complexidade genuína, documentar como "tensão produtiva":
   - Ex: pessoa introvertida que assume papel de liderança social por competência desenvolvida
   - Não eliminar a contradição, mas explicar o mecanismo
6. Ajustar scores quando a reconciliação indica erro de mensuração
7. Recalcular confiança das dimensões afetadas
8. Gerar relatório de reconciliação com decisões e justificativas

## Outputs

- `reconciliation-report`: Relatório com decisões e justificativas
- `adjusted-scores`: Scores ajustados pós-reconciliação
- `productive-tensions`: Tensões produtivas documentadas
- `updated-confidence`: Confiança recalculada

## Checklist de Conclusão

- [ ] Todas as contradições críticas tratadas
- [ ] Protocolo de reconciliação aplicado
- [ ] Cross-framework aligner executado
- [ ] Tensões produtivas documentadas
- [ ] Scores ajustados quando necessário
- [ ] Confiança recalculada
- [ ] Relatório de reconciliação gerado

## Próxima Task

`tasks/audit/verify-confidence-levels.md` — Verificar scores de confiança

## Subtask Breakdown
1. **Carregar contradições priorizadas** — Agente: `audit-agent`. Input: contradiction report. Output: lista ordenada. Gate: prioridades carregadas.
2. **Aplicar protocolo de reconciliação** — Agente: `audit-agent`. Input: contradição + dados brutos + confiança. Output: decisão por contradição. Gate: protocolo aplicado a cada crítica.
3. **Executar cross-framework-aligner** — Agente: `audit-agent`. Input: layer results + contradições. Output: alinhamentos verificados. Gate: clusters de convergência identificados.
4. **Documentar tensões produtivas** — Agente: `audit-agent`. Input: contradições de complexidade genuína. Output: `productive-tensions`. Gate: cada tensão com explicação do mecanismo.
5. **Recalcular confiança** — Agente: `audit-agent`. Input: scores ajustados. Output: `updated-confidence`. Gate: confiança recalculada para dimensões afetadas.

## Quality Gate
- [ ] Todas as contradições críticas reconciliadas com justificativa
- [ ] Scores ajustados onde necessário
- Threshold: confiança pós-reconciliação >= 55 para dimensões ajustadas
- Se FAIL: rebaixar dimensões com confiança < 55 para "hipótese"

## Rework Trigger
- Reconciliação gera nova contradição → iterar até estabilizar
- Confiança pós-ajuste < 40 → retornar camada afetada para reassessment
