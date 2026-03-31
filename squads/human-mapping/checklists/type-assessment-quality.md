---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: per-domain
---
# Checklist: Qualidade da Avaliacao de Tipos

## Proposito
Garantir que os tipos psicologicos foram inferidos com evidencia robusta e que a separacao entre tracos dimensionais e tipos categoricos foi feita de forma explicita e fundamentada.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Tipo principal foi identificado com base em evidencia suficiente — Evidencia: `tipo identificado com score de confianca`
- [ ] Framework de tipologia utilizado foi documentado — Evidencia: `nome do framework registrado (ex: MBTI, Eneagrama)`
- [ ] Separacao explicita entre traco e tipo foi realizada — Evidencia: `documento de distincao traco vs tipo`
- [ ] Tipo nao foi atribuido apenas por auto-identificacao do respondente — Evidencia: `fontes de inferencia multiplas`
- [ ] Funcoes cognitivas ou equivalentes foram analisadas (quando aplicavel) — Evidencia: `analise de funcoes registrada`
- [ ] Confianca na tipagem foi quantificada — Evidencia: `score de confianca do tipo >= limiar`
- [ ] Tipo alternativo mais provavel foi considerado — Evidencia: `segundo tipo candidato documentado`
- [ ] Evidencia comportamental sustenta o tipo atribuido — Evidencia: `exemplos comportamentais vinculados`

### Desejaveis (aumentam confianca)
- [ ] Mais de um framework de tipologia foi utilizado para validacao cruzada
- [ ] Respondente reconheceu-se na descricao do tipo identificado
- [ ] Analise de subtipo ou variante foi incluida
- [ ] Contexto situacional foi considerado na tipagem
- [ ] Limitacoes conhecidas do framework foram documentadas

## Evidencia Necessaria
- Tipo identificado com framework utilizado e score de confianca
- Documento explicando a separacao entre tracos e tipos nesta avaliacao
- Lista de fontes de inferencia (nao apenas auto-relato)
- Analise de funcoes cognitivas ou mecanismo equivalente
- Tipo alternativo mais provavel com justificativa
- Exemplos comportamentais que sustentam o tipo

## Acao se Falhar
- Se tipo foi atribuido sem evidencia: coletar mais dados antes de confirmar
- Se separacao traco vs tipo nao foi feita: documentar explicitamente a distincao
- Se confianca esta baixa: considerar tipo como tentativo e sinalizar no relatorio
- Se tipo alternativo nao foi considerado: avaliar segundo candidato mais provavel
- Se apenas auto-identificacao foi usada: buscar evidencia comportamental adicional
- Tipo com confianca abaixo do limiar deve ser apresentado como hipotese, nao conclusao

## Agente Responsavel
- **Agente principal**: Agente de Tipologia
- **Agentes de suporte**: Agente de Tracos de Personalidade, Agente de Cross-Framework
- **Aprovador final**: Agente de Qualidade
