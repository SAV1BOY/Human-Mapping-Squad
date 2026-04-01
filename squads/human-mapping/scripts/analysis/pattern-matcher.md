---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Pattern Matcher

## Propósito

Identificar padrões conhecidos no perfil do respondente, comparando os resultados com a biblioteca de padrões documentados em `lib/patterns/`, para enriquecer a interpretação e detectar perfis típicos.

## Input

- `integrated-scores`: Scores integrados de todas as camadas
- `convergence-clusters`: Clusters de convergência identificados pelo aligner
- `context`: Contexto da análise (pessoal, profissional, liderança, etc.)
- `patterns-library`: Biblioteca de padrões carregada de `lib/patterns/`

## Processo (step by step algorithm)

1. **Carregar biblioteca de padrões**
   - Ler padrões de `lib/patterns/personality-patterns.yaml`
   - Ler padrões de `lib/patterns/leadership-patterns.yaml`
   - Ler padrões de `lib/patterns/team-patterns.yaml`
   - Ler padrões de `lib/patterns/career-patterns.yaml`
   - Cada padrão contém: nome, descrição, condições (regras de match), frequência, implicações

2. **Executar matching de padrões de personalidade**
   - Para cada padrão na biblioteca, verificar se as condições são atendidas:
     - Ex: Padrão "Perfeccionista Funcional": Alta C (>70), Alta N faceta ansiedade (>60), Alta Maestria
     - Ex: Padrão "Líder Natural": Alta E (>65), Alta A (>55), Coordinator (Belbin), ESF_ (MBTI)
   - Calcular score de match (0-100) baseado em quantas condições são atendidas e com que intensidade

3. **Executar matching de padrões de contexto**
   - Filtrar padrões relevantes ao contexto da análise
   - Se liderança: priorizar padrões de liderança
   - Se equipe: priorizar padrões de dinâmica de equipe
   - Se carreira: priorizar padrões de fit profissional

4. **Classificar matches por relevância**
   - Match forte (>80% das condições): Padrão altamente provável
   - Match moderado (60-80%): Padrão possível, mencionar com caveat
   - Match fraco (<60%): Desconsiderar

5. **Verificar padrões de risco**
   - Padrões de burnout: alta conscienciosidade + alto neuroticismo + alta maestria
   - Padrões de descarrilamento: HDS alto em 2+ escalas
   - Padrões de desmotivação: ambiente incompatível com top motivadores
   - Padrões de subdesempenho: forças subutilizadas + baixo engajamento

6. **Gerar insights por padrão identificado**
   - Descrição do padrão em linguagem acessível
   - Implicações práticas para o contexto
   - Recomendações associadas
   - Frequência do padrão na população geral

7. **Priorizar padrões para o relatório**
   - Top 3-5 padrões mais relevantes e confiáveis
   - Padrões de risco sempre incluídos (independente do ranking)

## Output

- `matched-patterns`: Lista de padrões identificados com score de match
- `risk-patterns`: Padrões de risco detectados
- `pattern-insights`: Insights por padrão em linguagem acessível
- `pattern-recommendations`: Recomendações derivadas dos padrões

## Uso

Chamado por `tasks/audit/run-quality-check.md` para verificação e por `tasks/synthesis/synthesize-profile.md` para enriquecer o perfil integrado.

## Especificação de I/O

### Input
- Formato: YAML
- Campos obrigatórios: `integrated-scores`, `convergence-clusters`, `context`
- Campos opcionais: `patterns-library` (padrão: `lib/patterns/`)
- Exemplo: `{integrated-scores: {O: 72, C: 85, N: 65}, context: "lideranca", convergence-clusters: ["inovador"]}`

### Output
- Formato: YAML
- Campos: `matched-patterns`, `risk-patterns`, `pattern-insights`, `pattern-recommendations`

### Thresholds
- strong_match: 80% das condições atendidas
- moderate_match: 60% das condições
- discard_match: 60% (abaixo = descartar)
- max_patterns_report: 5 (top 3-5 para relatório)
- risk_always_include: true (padrões de risco sempre incluídos)

### Tratamento de Erros
- Input inválido: retornar erro `INVALID_SCORES`
- Dados insuficientes: executar matching parcial e flag `limited-matching`
- Biblioteca de padrões ausente: retornar lista vazia com warning `PATTERNS_LIBRARY_NOT_FOUND`
