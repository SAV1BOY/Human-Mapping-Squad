---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: per-domain
---
# Checklist: Qualidade do Laudo Executivo

## Proposito
Garantir que o laudo executivo e claro, acionavel e livre de jargao tecnico, permitindo que qualquer leitor compreenda os resultados e saiba o que fazer com eles.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Laudo executivo foi gerado a partir da sintese aprovada — Evidencia: `referencia a sintese de origem`
- [ ] Extensao esta dentro do limite definido para formato executivo — Evidencia: `contagem de palavras/paginas dentro do limite`
- [ ] Linguagem e acessivel a nao-especialistas — Evidencia: `revisao de linguagem sem jargao`
- [ ] Nenhum termo tecnico foi usado sem explicacao — Evidencia: `glossario incluso ou termos explicados inline`
- [ ] Conclusoes principais estao destacadas no inicio — Evidencia: `sumario executivo presente`
- [ ] Recomendacoes sao acionaveis e especificas — Evidencia: `cada recomendacao tem acao concreta`
- [ ] Score de confianca global esta visivel — Evidencia: `score apresentado de forma clara`
- [ ] Laudo nao contem afirmacoes absolutas sem ressalvas — Evidencia: `linguagem probabilistica utilizada`
- [ ] Formato e estrutura seguem o template padrao — Evidencia: `aderencia ao template verificada`

### Desejaveis (aumentam confianca)
- [ ] Laudo inclui visualizacoes ou graficos para facilitar compreensao
- [ ] Pontos fortes e areas de desenvolvimento estao equilibrados
- [ ] Tom do laudo e respeitoso e construtivo
- [ ] Laudo pode ser lido de forma independente (sem necessidade de contexto adicional)
- [ ] Respondente revisou e aprovou o laudo antes da entrega final

## Evidencia Necessaria
- Laudo executivo gerado com referencia a sintese
- Verificacao de extensao dentro dos limites
- Resultado da revisao de linguagem
- Sumario executivo com conclusoes principais
- Lista de recomendacoes com acoes concretas
- Score de confianca global visivel no documento
- Verificacao de aderencia ao template padrao

## Acao se Falhar
- Se laudo contem jargao: simplificar linguagem e explicar termos necessarios
- Se recomendacoes nao sao acionaveis: reescrever com acoes concretas e especificas
- Se extensao excede o limite: sintetizar mantendo as informacoes mais relevantes
- Se afirmacoes sao absolutas: adicionar ressalvas e linguagem probabilistica
- Se sumario executivo esta ausente: criar sumario com destaques principais
- Se formato nao segue template: reorganizar conforme estrutura padrao
- Laudo nao pode ser entregue com jargao nao explicado ou recomendacoes vagas

## Agente Responsavel
- **Agente principal**: Agente de Relatorio Executivo
- **Agentes de suporte**: Agente de Sintese
- **Aprovador final**: Agente de Qualidade
