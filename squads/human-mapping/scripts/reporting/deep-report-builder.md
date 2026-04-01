---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Deep Report Builder

## Proposito

Construir o relatorio profundo e abrangente do perfil persona, documentando todas as camadas de analise com evidencias, scores de confianca e analise de contradicoes.

## Input

1. **Saidas de todas as camadas (all layer outputs)**: Resultados individuais de cada camada de analise
2. **Mapa de contradicoes (contradiction map)**: Contradicoes identificadas entre camadas ou conclusoes
3. **Mapa de confianca (confidence map)**: Scores por conclusao, por camada e consolidado

## Processo

### Passo 1: Organizar por Camada

- Ordenar camadas conforme a sequencia logica do mapeamento
- Manter a identidade de cada camada preservada, sem omitir nenhuma
- Incluir metadados de cada camada (fonte, metodo, data de processamento)

### Passo 2: Incluir Evidencias por Conclusao

Para cada conclusao apresentada:
- Vincular a evidencia especifica que a sustenta e citar a fonte original
- Indicar se a evidencia e direta, inferida ou correlacional

### Passo 3: Incluir Scores de Confianca

- Score por conclusao individual, agregado por camada e geral do perfil
- Justificativa para cada nivel atribuido
- Indicadores visuais (alto/medio/baixo) para leitura rapida

### Passo 4: Incluir Analise de Contradicoes

- Listar todas as contradicoes identificadas entre camadas
- Descrever natureza, severidade e impacto de cada uma
- Apresentar hipoteses explicativas e metodo de reconciliacao aplicado

### Passo 5: Incluir Notas de Reconciliacao

Para cada contradicao reconciliada, documentar:
- Decisao tomada, justificativa e evidencias que fundamentaram a resolucao
- Nivel de confianca pos-reconciliacao e recomendacoes para investigacao futura

### Passo 6: Aplicar Template e Perfil de Voz

Aplicar `deep-persona-report-template`: secoes padronizadas, indices, referencias cruzadas e formatacao consistente para evidencias.

Aplicar `voice/tone-profiles/precise-analyst.md`:
- Tom analitico, preciso e fundamentado para publico especializado
- Clareza na distincao entre fatos, inferencias e hipoteses
- Rigor na apresentacao de incertezas e limitacoes

## Output

**Relatorio profundo completo** com todas as camadas documentadas:
- Analise detalhada por camada com evidencias vinculadas
- Scores de confianca em todos os niveis (conclusao, camada, perfil)
- Analise completa de contradicoes com notas de reconciliacao
- Formatacao e voz conforme templates e perfil precise-analyst

## Uso

```
Sequencia:
  1. Receber todas as saidas de camada + contradiction map + confidence map
  2. Executar deep-report-builder
  3. Encaminhar output para report-writer para revisao final
Dependencias:
  - Todas as saidas de camada (outputs)
  - contradiction-map, confidence-map (inputs)
  - deep-persona-report-template
  - voice/tone-profiles/precise-analyst.md
```

## Especificacao de I/O

### Input
- Formato: YAML/Markdown
- Campos obrigatorios: todas as saidas de camada, contradiction-map, confidence-map
- Exemplo: `{layers: {traits: {...}, types: {...}, ...}, contradiction-map: [...], confidence-map: {overall: 72}}`

### Output
- Formato: Markdown formatado (relatorio completo multi-secao)
- Campos: sumario executivo, perfil de personalidade, traducao trabalho, estilo cognitivo, mapa motivacional, inventario de forcas, dinamica de equipe, fit de carreira, modo de acao, analise integrada, mapa de confianca

### Thresholds
- min_sections: 10
- min_confidence_for_section: 50 (abaixo = omitir ou marcar como hipotese)
- evidence_required: true (cada afirmacao com evidencia vinculada)

### Tratamento de Erros
- Input invalido: retornar erro `INCOMPLETE_LAYER_DATA` com camadas ausentes
- Dados insuficientes: gerar relatorio com secoes disponiveis e nota de limitacoes expandida
