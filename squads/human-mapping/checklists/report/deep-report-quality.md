---
type: checklist
level: layer
layer: report
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade do Relatorio Profundo

## Proposito
Verificar que o relatorio profundo contem evidencia por conclusao, com rastreabilidade completa entre dados brutos, analise e recomendacoes.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Cada conclusao possui pelo menos uma evidencia rastreavel — Evidencia: `indice de conclusoes com referencia a dados fonte`
- [ ] Dados brutos de cada framework estao referenciados — Evidencia: `secao de dados por framework com scores e interpretacao`
- [ ] Cadeia logica de cada conclusao e explicita (dado -> inferencia -> conclusao) — Evidencia: `cadeia logica documentada por conclusao principal`
- [ ] Nivel de confianca informado por secao do relatorio — Evidencia: `score de confianca por secao`
- [ ] Contradicoes encontradas estao documentadas com resolucao — Evidencia: `secao de contradicoes com status`
- [ ] Relatorio cobre todas as camadas avaliadas — Evidencia: `checklist de camadas com status de cobertura`
- [ ] Nuances e complexidades do perfil estao preservadas — Evidencia: `secoes que abordam paradoxos e complexidades`
- [ ] Relatorio nao faz afirmacoes absolutas sem evidencia — Evidencia: `revisao de linguagem: ausencia de termos absolutos sem suporte`
- [ ] Limitacoes da avaliacao estao documentadas — Evidencia: `secao de limitacoes`

### Desejaveis (aumentam confianca)
- [ ] Graficos ou visualizacoes complementam o texto
- [ ] Comparacao com populacao de referencia esta presente
- [ ] Evolucao temporal (se disponivel) esta documentada
- [ ] Glossario de termos tecnicos esta incluido

## Evidencia Necessaria
- Indice de conclusoes com rastreabilidade
- Dados brutos referenciados por framework
- Cadeia logica por conclusao
- Score de confianca por secao
- Secao de contradicoes e limitacoes
- Checklist de cobertura de camadas

## Acao se Falhar
- Se conclusao nao tem evidencia: remover conclusao ou coletar evidencia adicional
- Se cadeia logica nao e explicita: documentar passo a passo do raciocinio
- Se camadas nao estao cobertas: completar secoes faltantes ou justificar exclusao
- Se limitacoes nao estao documentadas: adicionar secao de limitacoes antes de finalizar

## Agente Responsavel
- **Agente principal**: Agente de Relatorio
- **Agentes de suporte**: Agente de Sintese, Agente de Contradicao
- **Aprovador final**: Agente de Qualidade
