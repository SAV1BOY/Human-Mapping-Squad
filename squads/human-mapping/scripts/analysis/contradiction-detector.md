---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Contradiction Detector

## Propósito

Detectar automaticamente contradições entre os resultados de diferentes frameworks e camadas do assessment, classificando-as por severidade e fornecendo hipóteses de origem.

## Input

- `all-layer-results`: Resultados de todas as camadas de assessment
- `framework-mappings`: Mapeamentos esperados entre frameworks (de `lib/mappings/`)
- `tolerance-thresholds`: Limiares de tolerância por tipo de comparação

## Processo (step by step algorithm)

1. **Carregar mapeamentos esperados entre frameworks**
   - Mapeamentos definidos em `lib/mappings/cross-framework.yaml`
   - Cada mapeamento especifica:
     - Framework A (dimensão) <-> Framework B (dimensão)
     - Direção esperada (positiva, negativa, neutra)
     - Força esperada da correlação (forte, moderada, fraca)

2. **Executar comparações par-a-par**
   - Para cada par de frameworks mapeados:
     a. Extrair scores das dimensões correspondentes
     b. Calcular correlação observada
     c. Comparar com correlação esperada
     d. Se desvio > limiar de tolerância, registrar como contradição

3. **Comparações específicas a executar**
   - OCEAN Extroversão vs MBTI E/I (correlação positiva forte)
   - OCEAN Abertura vs MBTI S/N (correlação positiva moderada)
   - OCEAN Amabilidade vs MBTI T/F (correlação positiva moderada)
   - OCEAN Conscienciosidade vs MBTI J/P (correlação positiva moderada)
   - OCEAN -> HPI (mapeamentos de Hogan)
   - MBTI -> Belbin (padrões conhecidos)
   - Motivação vs MVPI Hogan
   - Forças vs OCEAN (correlações esperadas por domínio)
   - Kolbe QS vs OCEAN Abertura/Conscienciosidade

4. **Classificar contradições por severidade**
   - **Crítica** (desvio > 2x tolerância): Resultados diretamente opostos ao esperado
   - **Moderada** (desvio > 1.5x tolerância): Resultados significativamente diferentes
   - **Leve** (desvio > 1x tolerância): Variação acima do normal mas dentro do plausível

5. **Gerar hipóteses de origem para cada contradição**
   - Viés de desejabilidade social (dimensões tipicamente afetadas)
   - Complexidade genuína do perfil (pessoa com facetas contraditórias)
   - Erro de mensuração (baixa confiança em uma das camadas)
   - Contexto situacional (respondente responde diferente conforme frame)

6. **Calcular score de contradição geral**
   - Total ponderado: críticas * 3 + moderadas * 2 + leves * 1
   - Score alto indica necessidade de reconciliação intensiva

## Output

- `contradictions`: Lista de contradições com pares, desvios e severidade
- `contradiction-score`: Score geral de contradição da sessão
- `hypotheses`: Hipóteses de origem por contradição
- `reconciliation-priority`: Contradições priorizadas para reconciliação

## Uso

Chamado por `tasks/audit/audit-contradictions.md` como primeira etapa da auditoria pós-assessment.
