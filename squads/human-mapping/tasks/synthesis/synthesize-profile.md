---
type: task
squad: human-mapping
version: "2.0.0"
agent: synthesis-agent
workflow: synthesis-workflow
---

# Task: Sintetizar Perfil Integrado

## Objetivo

Sintetizar todos os resultados das camadas de assessment em um perfil humano integrado e coerente, conectando traços, tipos, motivações, forças, papéis e fit de carreira em uma narrativa unificada.

## Pré-condições

- Auditoria completa e quality check aprovado
- Todos os scores reconciliados e confiança verificada
- Flag de prontidão para síntese ativo

## Passos

1. Carregar todos os dados processados do session record:
   - Scores de traços (OCEAN) e facetas
   - Tradução Hogan (HPI, HDS, MVPI)
   - Tipo e funções cognitivas
   - Perfil motivacional
   - Top forças e forças subutilizadas
   - Papéis Belbin
   - Código RIASEC e fit de carreira
   - Perfil Kolbe
2. Identificar os 3-5 temas centrais que emergem do cruzamento dos dados:
   - Ex: "Líder inovador com tendência à sobrecarga" (alta abertura + alto QS + shaper + risco de burnout)
3. Construir narrativa integrativa que conecta os temas centrais
4. Mapear pontos fortes do perfil integrado (convergências positivas)
5. Mapear áreas de atenção (convergências de risco ou tensões)
6. Identificar paradoxos produtivos (características aparentemente contraditórias que geram vantagem)
7. Gerar recomendações iniciais baseadas no perfil integrado
8. Vincular cada afirmação do perfil às evidências dos frameworks que a suportam
9. Aplicar template de interpretação adequado ao contexto (pessoal/profissional/liderança/equipe)
10. Validar que o perfil é internamente consistente

## Outputs

- `integrated-profile`: Perfil humano integrado completo
- `central-themes`: Temas centrais identificados
- `strengths-map`: Mapa de pontos fortes integrados
- `attention-areas`: Áreas de atenção com evidências
- `productive-paradoxes`: Paradoxos produtivos identificados
- `initial-recommendations`: Recomendações iniciais

## Checklist de Conclusão

- [ ] Todos os dados carregados e organizados
- [ ] Temas centrais identificados
- [ ] Narrativa integrativa construída
- [ ] Pontos fortes mapeados
- [ ] Áreas de atenção documentadas
- [ ] Paradoxos produtivos identificados
- [ ] Evidências vinculadas a cada afirmação
- [ ] Perfil validado internamente

## Próxima Task

`tasks/synthesis/build-executive-snapshot.md` — Construir snapshot executivo

## Subtask Breakdown
1. **Carregar dados processados** — Agente: `synthesis-agent`. Input: session record completo. Output: dados organizados por camada. Gate: 8 camadas carregadas.
2. **Identificar temas centrais** — Agente: `synthesis-agent`. Input: dados cruzados. Output: 3-5 `central-themes`. Gate: cada tema suportado por >= 2 frameworks.
3. **Construir narrativa integrativa** — Agente: `synthesis-agent`. Input: temas + evidências. Output: narrativa coerente. Gate: narrativa conecta todos os temas sem contradições.
4. **Mapear forças e áreas de atenção** — Agente: `synthesis-agent`. Input: perfil integrado. Output: `strengths-map` + `attention-areas`. Gate: cada item com evidência vinculada.
5. **Validar consistência interna** — Agente: `synthesis-agent`. Input: perfil completo. Output: perfil validado. Gate: zero contradições internas no perfil final.

## Quality Gate
- [ ] 3-5 temas centrais identificados e documentados
- [ ] Cada afirmação vinculada a evidências de >= 2 frameworks
- Threshold: perfil internamente consistente (zero contradições não-explicadas)
- Se FAIL: retornar ao audit para reconciliação adicional

## Rework Trigger
- Contradição interna no perfil → retornar a `reconcile-frameworks`
- Tema central suportado por apenas 1 framework → rebaixar para "observação"
