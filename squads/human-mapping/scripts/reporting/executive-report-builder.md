---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Executive Report Builder

## Proposito

Construir o relatorio executivo de 1 pagina (snapshot executivo) a partir da sintese consolidada do perfil mapeado, transformando dados complexos em um resumo conciso e orientado a decisao.

## Input

1. **Saida do synthesis-architect**: Sintese consolidada com o perfil integrado e reconciliado
2. **Mapa de confianca (confidence map)**: Scores de confianca por categoria e indicadores de robustez

## Processo

### Passo 1: Extrair Achados-Chave por Categoria

Extrair os 2-3 achados mais relevantes da sintese para cada categoria:
- **Quem sao (Identidade)**: Tracos dominantes, valores centrais, autoconceito
- **Como agem (Comportamento)**: Padroes de acao, estilos de decisao, habitos
- **O que os move (Motivacao)**: Drivers internos, necessidades, aspiracoes
- **Onde se destacam (Excelencia)**: Forcas distintivas, competencias-chave
- **Riscos e pontos cegos**: Vulnerabilidades, padroes limitantes, areas criticas

### Passo 2: Aplicar Modelo de Brief Executivo

Aplicar `executive-brief-model` para estruturar os achados:
- Priorizar impacto sobre detalhe
- Limitar cada secao a 2-3 frases de alta densidade informacional
- Garantir que cada afirmacao seja acionavel ou estrategicamente relevante

### Passo 3: Formatar com Template

Aplicar `executive-snapshot-template`: layout de 1 pagina, hierarquia visual clara, formatacao padronizada do squad.

### Passo 4: Incluir Resumo de Confianca

Inserir ao final do relatorio:
- Score geral de confianca do perfil
- Indicadores por categoria (alto/medio/baixo)
- Sinalizacao de conclusoes que requerem validacao adicional

### Passo 5: Aplicar Perfil de Voz e Tom

Aplicar `voice/tone-profiles/executive-advisor.md`:
- Tom confiante porem calibrado, linguagem executiva sem jargao tecnico
- Equilibrio entre assertividade e nuance para decisores de alto nivel

## Output

**Relatorio executivo formatado** pronto para revisao pelo `report-writer`:
- Snapshot de 1 pagina com achados-chave por categoria
- Resumo de confianca integrado
- Tom alinhado ao perfil executive-advisor
- Formatacao conforme executive-snapshot-template

## Uso

```
Sequencia:
  1. Receber saida do synthesis-architect + confidence map
  2. Executar executive-report-builder
  3. Encaminhar output para report-writer para revisao final
Dependencias:
  - synthesis-architect (output), confidence-map (input)
  - executive-brief-model, executive-snapshot-template
  - voice/tone-profiles/executive-advisor.md
```

## Especificacao de I/O

### Input
- Formato: YAML/Markdown
- Campos obrigatorios: saida do synthesis-architect (perfil integrado), confidence-map
- Exemplo: `{synthesis: {central-themes: [...], strengths: [...], risks: [...]}, confidence: {overall: 75, by_category: {...}}}`

### Output
- Formato: Markdown formatado (1 pagina)
- Campos: resumo em 1 frase, top 3 forcas, top 3 areas de atencao, perfil relampago, recomendacao-chave, resumo de confianca

### Thresholds
- min_frameworks_per_point: 2 (cada afirmacao suportada por >= 2 frameworks)
- max_sections: 5
- max_sentences_per_section: 3
- min_confidence_for_inclusion: 50

### Tratamento de Erros
- Input invalido: retornar erro `MISSING_SYNTHESIS_DATA`
- Dados insuficientes: gerar snapshot parcial com sections disponiveis e disclaimer
