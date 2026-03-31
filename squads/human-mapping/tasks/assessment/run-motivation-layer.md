---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Camada de Motivação

## Objetivo

Executar a camada de motivação, identificando os motivadores intrínsecos e extrínsecos do respondente, hierarquia de necessidades e drivers de engajamento.

## Pré-condições

- Camadas anteriores (traços, workplace, tipos) concluídas
- Dados suficientes para contextualizar motivações
- Respondente ainda engajado na sessão

## Passos

1. Carregar banco de perguntas de motivação de `lib/questions/motivation/`
2. Aplicar perguntas cobrindo os principais drivers:
   - Autonomia — necessidade de controle e independência
   - Maestria — desejo de excelência e domínio técnico
   - Propósito — conexão com significado e impacto
   - Pertencimento — necessidade de conexão e comunidade
   - Reconhecimento — busca por validação e status
   - Segurança — necessidade de estabilidade e previsibilidade
   - Crescimento — desejo de evolução e novos desafios
3. Utilizar técnica de ranking forçado para hierarquizar motivadores
4. Aplicar cenários situacionais para validar hierarquia declarada:
   - "Se tivesse que escolher entre um projeto desafiador e uma promoção..."
   - "O que faria você sair de um emprego estável?"
5. Executar `scripts/scoring/motivation-scorer.md` para gerar perfil motivacional
6. Cruzar com dados de tipos (ex: ENTP tende a priorizar autonomia e novidade)
7. Cruzar com MVPI do Hogan para validação
8. Identificar possíveis desmotivadores (inverso dos top motivadores)
9. Calcular confiança da camada

## Outputs

- `motivation-profile`: Perfil completo com ranking de motivadores
- `intrinsic-drivers`: Top 3 motivadores intrínsecos
- `extrinsic-drivers`: Top 3 motivadores extrínsecos
- `demotivators`: Principais desmotivadores identificados
- `motivation-confidence`: Confiança da camada

## Checklist de Conclusão

- [ ] Perguntas de motivação aplicadas
- [ ] Ranking forçado realizado
- [ ] Cenários situacionais validados
- [ ] Scores calculados pelo motivation-scorer
- [ ] Cruzamento com tipos e MVPI realizado
- [ ] Desmotivadores identificados
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-strengths-layer.md` — Rodar camada de forças
