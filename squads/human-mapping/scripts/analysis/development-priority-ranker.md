---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Development Priority Ranker

## Propósito

Rankear as prioridades de desenvolvimento do respondente com base no perfil integrado, utilizando uma matriz de impacto vs esforço e considerando o contexto específico da análise.

## Input

- `integrated-profile`: Perfil integrado completo
- `attention-areas`: Áreas de atenção identificadas na síntese
- `underused-strengths`: Forças subutilizadas
- `risk-patterns`: Padrões de risco detectados
- `context`: Contexto da análise e objetivo do respondente
- `hds-risks`: Descarriladores Hogan identificados

## Processo (step by step algorithm)

1. **Compilar lista de áreas de desenvolvimento potenciais**
   - Forças subutilizadas (oportunidade de alavancagem)
   - Áreas de atenção (competências a desenvolver)
   - Descarriladores HDS (riscos a mitigar)
   - Gaps identificados vs requisitos do contexto
   - Padrões de risco a endereçar

2. **Calcular score de impacto para cada área** (0-100)
   - Relevância para o objetivo do respondente: peso 40%
   - Frequência de impacto no dia a dia: peso 25%
   - Severidade se não endereçado: peso 20%
   - Potencial de crescimento: peso 15%
   - Para contexto de contratação: impacto na performance da vaga
   - Para contexto de liderança: impacto na eficácia de liderança
   - Para contexto de equipe: impacto na dinâmica do time

3. **Calcular score de esforço para cada área** (0-100)
   - Proximidade com forças existentes (menor esforço se já tem base): peso 30%
   - Complexidade da mudança comportamental necessária: peso 30%
   - Disponibilidade de recursos e suporte: peso 20%
   - Tempo estimado para resultado visível: peso 20%

4. **Posicionar na matriz impacto x esforço**
   - **Quick Wins** (impacto > 60, esforço < 40): Prioridade 1
   - **Projetos-Chave** (impacto > 60, esforço >= 40): Prioridade 2
   - **Manutenção** (impacto <= 60, esforço < 40): Prioridade 3
   - **Avaliar** (impacto <= 60, esforço >= 40): Prioridade 4

5. **Aplicar override para riscos críticos**
   - Descarriladores HDS com severidade alta: elevar para Prioridade 1 independente do esforço
   - Padrões de burnout detectados: elevar para Prioridade 1

6. **Gerar ranking final ordenado**
   - Ordenar por prioridade (1 a 4)
   - Dentro da mesma prioridade, ordenar por impacto (decrescente)
   - Limitar a 8-12 itens no plano final

7. **Associar ações concretas por prioridade**
   - Para cada item, sugerir 3-5 ações específicas
   - Definir prazo sugerido (curto/médio/longo)
   - Indicar métricas de progresso

## Output

- `priority-ranking`: Ranking ordenado de prioridades de desenvolvimento
- `impact-effort-matrix`: Posicionamento de cada área na matriz
- `action-suggestions`: Ações sugeridas por prioridade
- `critical-overrides`: Riscos críticos que receberam override
- `timeline-estimate`: Estimativa de timeline por prioridade

## Uso

Chamado por `tasks/synthesis/build-development-plan.md` para gerar o plano de desenvolvimento priorizado.
