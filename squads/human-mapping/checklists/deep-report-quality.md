---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: per-domain
---
# Checklist: Qualidade do Laudo Profundo

## Proposito
Assegurar que o laudo profundo contem evidencia detalhada por conclusao, permitindo rastreabilidade completa dos resultados e servindo como referencia tecnica aprofundada do mapeamento.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Laudo profundo foi gerado a partir da sintese aprovada — Evidencia: `referencia a sintese de origem`
- [ ] Cada conclusao possui evidencia especifica que a sustenta — Evidencia: `vinculacao conclusao-evidencia documentada`
- [ ] Evidencias incluem dados brutos ou referencias a dados brutos — Evidencia: `referencias a dados originais presentes`
- [ ] Todas as camadas avaliadas possuem secao dedicada — Evidencia: `secao por camada presente`
- [ ] Metodologia utilizada em cada camada esta descrita — Evidencia: `descricao metodologica por camada`
- [ ] Score de confianca por camada esta incluido — Evidencia: `scores individuais por camada`
- [ ] Contradicoes e suas reconciliacoes estao documentadas — Evidencia: `secao de contradicoes presente`
- [ ] Limitacoes da avaliacao estao explicitadas — Evidencia: `secao de limitacoes presente`
- [ ] Frameworks utilizados estao referenciados — Evidencia: `lista de frameworks com referencias`

### Desejaveis (aumentam confianca)
- [ ] Laudo inclui analise de sensibilidade dos resultados
- [ ] Hipoteses alternativas foram consideradas e descartadas com justificativa
- [ ] Dados brutos estao anexados ou referenciados para consulta
- [ ] Laudo inclui secao de perguntas abertas para investigacao futura
- [ ] Comparacao com avaliacoes anteriores (se disponivel) esta incluida
- [ ] Glossario tecnico esta presente

## Evidencia Necessaria
- Laudo profundo completo com referencia a sintese
- Vinculacao explicita de cada conclusao a sua evidencia
- Referencias a dados brutos ou originais
- Secao dedicada por camada avaliada
- Descricao metodologica por camada
- Scores de confianca individuais por camada
- Secao de contradicoes com reconciliacoes
- Secao de limitacoes da avaliacao
- Lista de frameworks utilizados

## Acao se Falhar
- Se conclusoes nao tem evidencia: vincular cada conclusao a dados especificos
- Se metodologia nao esta descrita: adicionar descricao metodologica por camada
- Se camadas estao faltando: incluir secao para cada camada avaliada
- Se contradicoes nao estao documentadas: incluir secao de contradicoes
- Se limitacoes nao estao explicitadas: adicionar secao de limitacoes
- Se frameworks nao estao referenciados: listar todos os frameworks utilizados
- Laudo profundo nao pode ser aprovado sem rastreabilidade conclusao-evidencia

## Agente Responsavel
- **Agente principal**: Agente de Relatorio Profundo
- **Agentes de suporte**: Agente de Sintese, Agente de Auditoria de Contradicoes
- **Aprovador final**: Agente de Qualidade
