---
type: task
squad: human-mapping
version: "2.0.0"
agent: audit-agent
workflow: audit-workflow
---

# Task: Verificar Scores de Confiança

## Objetivo

Verificar e validar os scores de confiança de todas as camadas e dimensões, garantindo que apenas resultados com confiança adequada sejam incluídos nos relatórios finais.

## Pré-condições

- Reconciliação de frameworks concluída (`reconcile-frameworks.md`)
- Scores ajustados e confiança recalculada disponíveis
- Mínimos de confiança por tipo de output definidos no baseline

## Passos

1. Compilar scores de confiança de todas as camadas:
   - Traços (por dimensão OCEAN)
   - Workplace/Hogan (por escala HPI, HDS, MVPI)
   - Tipos (por eixo de preferência)
   - Motivação (por motivador)
   - Forças (por força identificada)
   - Belbin (por papel)
   - RIASEC (por tipo)
   - Kolbe (por modo de ação)
2. Executar `scripts/scoring/confidence-calculator.md` para validação final
3. Comparar confiança de cada dimensão com os mínimos estabelecidos no baseline
4. Classificar cada dimensão como:
   - **Verde**: Confiança >= 70, incluir sem ressalvas
   - **Amarelo**: Confiança 50-69, incluir com nota de cautela
   - **Vermelho**: Confiança < 50, excluir ou mencionar como hipótese
5. Calcular confiança agregada do perfil completo
6. Verificar se a confiança agregada atende ao mínimo para cada tipo de output solicitado
7. Se confiança insuficiente para output solicitado, propor alternativas:
   - Reduzir escopo do relatório
   - Solicitar sessão adicional para camadas fracas
8. Gerar mapa visual de confiança para inclusão no relatório

## Outputs

- `confidence-map`: Mapa completo de confiança por dimensão
- `dimension-status`: Status (verde/amarelo/vermelho) por dimensão
- `aggregate-confidence`: Confiança agregada do perfil
- `output-eligibility`: Quais outputs podem ser gerados com a confiança atual
- `confidence-gaps`: Gaps de confiança e recomendações

## Checklist de Conclusão

- [ ] Confiança de todas as camadas compilada
- [ ] Confidence calculator executado para validação
- [ ] Dimensões classificadas por status
- [ ] Confiança agregada calculada
- [ ] Elegibilidade de outputs verificada
- [ ] Gaps identificados e alternativas propostas
- [ ] Session record atualizado

## Próxima Task

`tasks/audit/run-quality-check.md` — Rodar verificação geral de qualidade
