---
type: task
squad: human-mapping
version: "2.0.0"
agent: synthesis-agent
workflow: synthesis-workflow
---

# Task: Construir Snapshot Executivo

## Objetivo

Construir um snapshot executivo conciso e de alto impacto que resume o perfil integrado em formato digerível para tomadores de decisão, destacando os pontos mais relevantes em 1-2 páginas.

## Pré-condições

- Perfil integrado sintetizado (`synthesize-profile.md`)
- Temas centrais e recomendações iniciais disponíveis
- Contexto e objetivo da análise definidos

## Passos

1. Executar `scripts/reporting/executive-report-builder.md` com os dados do perfil integrado
2. Selecionar template de snapshot conforme contexto:
   - Autoconhecimento: foco em forças e áreas de desenvolvimento
   - Contratação: foco em fit com a vaga e riscos
   - Equipe: foco em papéis e complementaridade
   - Liderança: foco em estilo e descarriladores
3. Compor o snapshot com as seguintes seções:
   - **Resumo em uma frase**: Síntese do perfil em uma sentença impactante
   - **Top 3 Forças**: As três maiores forças com evidências
   - **Top 3 Áreas de Atenção**: As três principais áreas de cuidado
   - **Perfil Relâmpago**: Tipo + papel + motivador principal em formato visual
   - **Recomendação-Chave**: A recomendação mais importante para o contexto
4. Garantir que cada ponto tenha suporte de pelo menos 2 frameworks
5. Usar linguagem direta, sem jargões técnicos
6. Incluir indicador visual de confiança geral do perfil
7. Adicionar nota de rodapé com limitações e caveats relevantes
8. Revisar para garantir que não há contradições internas no snapshot
9. Formatar conforme template padrão do squad

## Outputs

- `executive-snapshot`: Documento formatado do snapshot executivo
- `snapshot-confidence`: Confiança geral do snapshot
- `key-recommendation`: Recomendação-chave destacada

## Checklist de Conclusão

- [ ] Report builder executado
- [ ] Template correto selecionado para o contexto
- [ ] Todas as seções compostas
- [ ] Cada ponto suportado por 2+ frameworks
- [ ] Linguagem acessível verificada
- [ ] Confiança geral indicada
- [ ] Limitações documentadas
- [ ] Formatação conforme template padrão

## Próxima Task

`tasks/synthesis/build-deep-report.md` — Construir relatório profundo (se profundidade /start ou /deep)

## Subtask Breakdown
1. **Executar executive-report-builder** — Agente: `synthesis-agent`. Input: perfil integrado + confidence map. Output: rascunho do snapshot. Gate: builder executado sem erros.
2. **Selecionar template por contexto** — Agente: `synthesis-agent`. Input: contexto da análise. Output: template aplicado. Gate: template correto para o contexto.
3. **Compor seções** — Agente: `synthesis-agent`. Input: temas + forças + áreas de atenção. Output: 5 seções do snapshot. Gate: cada seção com <= 3 frases.
4. **Validar suporte multi-framework** — Agente: `synthesis-agent`. Input: afirmações do snapshot. Output: checklist de suporte. Gate: cada ponto suportado por >= 2 frameworks.
5. **Revisar e formatar** — Agente: `synthesis-agent`. Input: rascunho completo. Output: `executive-snapshot` final. Gate: linguagem sem jargão, confiança indicada, limitações incluídas.

## Quality Gate
- [ ] Snapshot com todas as 5 seções obrigatórias
- [ ] Linguagem acessível (sem jargões técnicos)
- Threshold: confiança geral do snapshot >= 60
- Se FAIL: adicionar caveats explícitos nas seções de menor confiança

## Rework Trigger
- Contradição interna no snapshot → revisar com dados do perfil integrado
- Confiança do snapshot < 50 → reduzir escopo para seções de alta confiança apenas
