---
type: task
squad: human-mapping
version: "2.0.0"
agent: synthesis-agent
workflow: synthesis-workflow
---

# Task: Construir Plano de Desenvolvimento

## Objetivo

Construir um plano de desenvolvimento personalizado baseado no perfil integrado, priorizando ações de alto impacto que alavancam forças e mitigam áreas de risco.

## Pré-condições

- Perfil integrado e relatório profundo concluídos
- Profundidade `/deep` ou objetivo que requer plano de desenvolvimento
- Áreas de atenção e forças subutilizadas identificadas

## Passos

1. Executar `scripts/reporting/development-plan-builder.md` com perfil integrado
2. Executar `scripts/analysis/development-priority-ranker.md` para priorizar áreas
3. Definir prioridades de desenvolvimento usando matriz de impacto x esforço:
   - **Quick wins**: Alto impacto, baixo esforço (alavancar forças subutilizadas)
   - **Projetos-chave**: Alto impacto, alto esforço (desenvolver competências críticas)
   - **Manutenção**: Baixo impacto, baixo esforço (manter forças consolidadas)
   - **Avaliar**: Baixo impacto, alto esforço (questionar se vale investir)
4. Para cada prioridade de desenvolvimento, definir:
   - Objetivo específico e mensurável
   - Ações concretas recomendadas (3-5 por prioridade)
   - Prazo sugerido (curto: 1-3 meses, médio: 3-6 meses, longo: 6-12 meses)
   - Métricas de progresso
   - Recursos sugeridos (livros, cursos, práticas)
5. Incluir seção de alavancagem de forças:
   - Como aplicar mais as top forças no contexto atual
   - Oportunidades de usar forças em novas áreas
6. Incluir seção de mitigação de riscos:
   - Estratégias para gerenciar descarriladores (HDS)
   - Gatilhos de alerta e planos de contingência
7. Para contexto de liderança, incluir plano específico de desenvolvimento de liderança
8. Gerar timeline visual do plano

## Outputs

- `development-plan`: Plano completo de desenvolvimento
- `priority-matrix`: Matriz de prioridades impacto x esforço
- `action-items`: Lista de ações concretas com prazos
- `progress-metrics`: Métricas de acompanhamento
- `development-timeline`: Timeline visual do plano

## Checklist de Conclusão

- [ ] Priority ranker executado
- [ ] Matriz de impacto x esforço construída
- [ ] Ações concretas definidas por prioridade
- [ ] Prazos e métricas estabelecidos
- [ ] Alavancagem de forças documentada
- [ ] Mitigação de riscos incluída
- [ ] Timeline visual gerada
- [ ] Plano formatado conforme template

## Próxima Task

`tasks/synthesis/build-specialized-report.md` — Construir relatório especializado (se aplicável)

## Subtask Breakdown
1. **Executar development-plan-builder + priority-ranker** — Agente: `synthesis-agent`. Input: perfil integrado + áreas de atenção. Output: matriz impacto x esforço. Gate: ranker executado.
2. **Definir prioridades** — Agente: `synthesis-agent`. Input: matriz. Output: quick wins + projetos-chave classificados. Gate: 8-12 itens priorizados.
3. **Detalhar ações** — Agente: `synthesis-agent`. Input: prioridades. Output: 3-5 ações por prioridade com prazos e métricas. Gate: cada ação com objetivo mensurável.
4. **Incluir alavancagem e mitigação** — Agente: `synthesis-agent`. Input: forças + HDS risks. Output: seções de alavancagem e mitigação. Gate: top forças e top riscos cobertos.
5. **Gerar timeline** — Agente: `synthesis-agent`. Input: ações + prazos. Output: `development-timeline`. Gate: timeline cobre curto, médio e longo prazo.

## Quality Gate
- [ ] Matriz impacto x esforço com >= 8 itens posicionados
- [ ] Ações concretas com prazos e métricas definidos
- Threshold: >= 2 quick wins identificados
- Se FAIL: reordenar prioridades para garantir ao menos 1 quick win

## Rework Trigger
- Nenhum quick win → reavaliar forças subutilizadas como candidatas
- Plano com > 15 itens → priorizar e reduzir escopo
