---
type: task
squad: human-mapping
version: "2.0.0"
agent: audit-agent
workflow: audit-workflow
---

# Task: Auditar Contradições entre Frameworks

## Objetivo

Identificar e documentar contradições entre os resultados dos diferentes frameworks aplicados durante o assessment, garantindo que inconsistências sejam tratadas antes da síntese do perfil.

## Pré-condições

- Todas as camadas de assessment concluídas
- Scores e resultados de todos os frameworks disponíveis no session record
- Baseline de confiança estabelecido

## Passos

1. Executar `scripts/analysis/contradiction-detector.md` com todos os dados do assessment
2. Verificar consistência entre pares de frameworks:
   - Big Five vs MBTI: ex: alta extroversão OCEAN mas tipo I no MBTI
   - Big Five vs Hogan: ex: alta amabilidade mas alto risco de "Skeptical" no HDS
   - MBTI vs Belbin: ex: INTJ mas papel primário Teamworker
   - Motivação vs RIASEC: ex: autonomia como top motivador mas código C dominante
   - Kolbe vs MBTI: ex: alto Quick Start mas tipo ISTJ
3. Classificar cada contradição por severidade:
   - **Crítica**: Contradição direta que invalida um dos resultados
   - **Moderada**: Tensão que pode indicar complexidade do perfil
   - **Leve**: Variação normal dentro das margens de erro
4. Para contradições críticas, verificar se a origem pode ser:
   - Erro de scoring
   - Viés de desejabilidade social não corrigido
   - Complexidade genuína do perfil (pessoa com facetas contraditórias)
5. Gerar relatório de contradições com evidências
6. Priorizar contradições que precisam de reconciliação
7. Registrar achados no session record

## Outputs

- `contradiction-report`: Relatório completo de contradições
- `critical-contradictions`: Lista de contradições críticas
- `contradiction-origins`: Hipóteses de origem por contradição
- `reconciliation-priorities`: Prioridades para reconciliação

## Checklist de Conclusão

- [ ] Contradiction detector executado
- [ ] Todos os pares de frameworks verificados
- [ ] Contradições classificadas por severidade
- [ ] Origens hipotéticas documentadas
- [ ] Relatório de contradições gerado
- [ ] Prioridades de reconciliação definidas
- [ ] Session record atualizado

## Próxima Task

`tasks/audit/reconcile-frameworks.md` — Reconciliar conflitos entre frameworks
