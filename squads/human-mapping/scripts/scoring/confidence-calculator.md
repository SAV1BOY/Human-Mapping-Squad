---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Confidence Calculator

## Propósito

Calcular o nível de confiança dos resultados por dimensão, camada e perfil agregado, considerando quantidade de dados, consistência, qualidade das respostas e concordância entre frameworks.

## Input

- `layer-data`: Dados da camada sendo avaliada (respostas, scores, metadata)
- `calibration-data`: Dados de calibração do respondente
- `quality-metrics`: Métricas de qualidade das respostas
- `cross-framework-data`: Dados de outras camadas para cruzamento (quando disponíveis)
- `mode`: Modo de cálculo (`layer`, `dimension`, `aggregate`)

## Processo (step by step algorithm)

1. **Calcular confiança base por quantidade de dados**
   - Número de perguntas respondidas vs mínimo recomendado:
     - >= 100% do mínimo: 25 pontos
     - 75-99% do mínimo: 18 pontos
     - 50-74% do mínimo: 10 pontos
     - < 50% do mínimo: 5 pontos

2. **Calcular confiança por qualidade das respostas**
   - Média do quality-score das respostas da camada:
     - Média >= 80: 25 pontos
     - Média 60-79: 18 pontos
     - Média 40-59: 10 pontos
     - Média < 40: 5 pontos

3. **Calcular confiança por consistência interna**
   - Verificar consistência entre perguntas que medem a mesma dimensão:
     - Alpha de Cronbach >= 0.8: 25 pontos
     - Alpha 0.6-0.79: 18 pontos
     - Alpha 0.4-0.59: 10 pontos
     - Alpha < 0.4: 5 pontos

4. **Calcular confiança por concordância cross-framework** (quando disponível)
   - Verificar se resultado é consistente com outras camadas:
     - Concordância com 3+ frameworks: 25 pontos
     - Concordância com 2 frameworks: 18 pontos
     - Concordância com 1 framework: 10 pontos
     - Nenhuma concordância: 5 pontos

5. **Aplicar modificadores**
   - Desejabilidade social alta: -10 pontos
   - Respostas muito rápidas (abaixo de 3s por pergunta): -5 pontos
   - Padrão suspeito detectado: -15 pontos
   - Sessão retomada após longo intervalo: -5 pontos

6. **Calcular score final de confiança**
   - Somar pontos dos 4 critérios (máximo 100)
   - Aplicar modificadores
   - Garantir range 0-100
   - Classificar: Alta (>=70), Média (50-69), Baixa (<50)

7. **Para modo `aggregate`**
   - Média ponderada da confiança de todas as camadas
   - Peso maior para camadas com mais perguntas

## Output

- `confidence-score`: Score de confiança (0-100)
- `confidence-level`: Classificação (alta, média, baixa)
- `confidence-breakdown`: Decomposição por critério
- `modifiers-applied`: Modificadores aplicados com justificativa
- `recommendations`: Recomendações para melhorar confiança (se baixa)

## Uso

Chamado por cada task de assessment ao final da camada, por tasks de audit para verificação, e por tasks de síntese para inclusão nos relatórios.
