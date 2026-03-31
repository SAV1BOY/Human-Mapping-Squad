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
