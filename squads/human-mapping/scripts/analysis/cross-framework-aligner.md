---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Cross-Framework Aligner

## Propósito

Verificar e quantificar o alinhamento entre os resultados dos diferentes frameworks aplicados, gerando um mapa de convergência que suporta a síntese do perfil integrado.

## Input

- `all-layer-results`: Resultados de todas as camadas de assessment
- `contradiction-report`: Relatório de contradições (do contradiction-detector)
- `framework-mappings`: Mapeamentos esperados entre frameworks

## Processo (step by step algorithm)

1. **Construir matriz de alinhamento**
   - Linhas: dimensões avaliadas (traços, tipos, motivadores, forças, papéis, interesses, ação)
   - Colunas: frameworks utilizados (OCEAN, Hogan, MBTI, CliftonStrengths, Belbin, RIASEC, Kolbe)
   - Células: score normalizado (0-100) da dimensão no framework

2. **Calcular alinhamento por dimensão transversal**
   - Para cada tema/dimensão que cruza múltiplos frameworks:
     - Ex: "Sociabilidade" aparece em Extroversão (OCEAN), E/I (MBTI), Sociabilidade (HPI), WOO (Clifton), Resource Investigator (Belbin)
     - Calcular coeficiente de concordância entre todos os indicadores
     - Se concordância > 0.7: alinhamento forte (alta confiança)
     - Se concordância 0.4-0.7: alinhamento moderado
     - Se concordância < 0.4: desalinhamento (investigar)

3. **Identificar clusters de convergência**
   - Agrupar dimensões que convergem consistentemente
   - Ex: Alta abertura + INTJ + Ideation (Clifton) + Plant (Belbin) + alto QS (Kolbe) = cluster "Inovador"
   - Cada cluster é um tema central forte do perfil

4. **Identificar dimensões isoladas**
   - Resultados que aparecem em apenas um framework sem confirmação cruzada
   - Atribuir confiança menor a esses resultados
   - Sinalizar como "hipótese não confirmada"

5. **Gerar mapa de convergência visual**
   - Representação de quais frameworks concordam em quais dimensões
   - Cores por nível de alinhamento (verde, amarelo, vermelho)
   - Clusters destacados como temas centrais

6. **Calcular score geral de alinhamento**
   - Média ponderada dos coeficientes de concordância
   - Score alto = perfil consistente e confiável
   - Score baixo = perfil complexo ou dados inconsistentes

7. **Gerar recomendações para a síntese**
   - Quais temas são fortes o suficiente para o relatório
   - Quais precisam de caveats
   - Quais devem ser omitidos por confiança insuficiente

## Output

- `alignment-matrix`: Matriz completa de alinhamento
- `convergence-clusters`: Clusters de convergência identificados
- `isolated-dimensions`: Dimensões sem confirmação cruzada
- `alignment-score`: Score geral de alinhamento (0-100)
- `synthesis-recommendations`: Recomendações para a síntese

## Uso

Chamado por `tasks/audit/reconcile-frameworks.md` durante a reconciliação e por `tasks/synthesis/synthesize-profile.md` para construir o perfil integrado.
