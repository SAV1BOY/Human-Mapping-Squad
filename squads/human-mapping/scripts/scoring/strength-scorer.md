---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Strength Scorer

## Propósito

Classificar e pontuar as forças do respondente, mapeando-as para frameworks de referência (CliftonStrengths, VIA) e distinguindo entre talentos naturais e competências desenvolvidas.

## Input

- `strength-responses`: Respostas às perguntas de forças (incluindo STAR)
- `trait-scores`: Scores OCEAN para correlação
- `motivation-profile`: Perfil motivacional para cruzamento
- `type-result`: Tipo inferido para validação

## Processo (step by step algorithm)

1. **Extrair indicadores de forças das respostas**
   - Para respostas abertas (STAR), identificar keywords e temas:
     - Atividades de flow -> indicam talento natural
     - Elogios recorrentes -> indicam força reconhecida
     - Facilidade percebida -> indica talento vs esforço
   - Para respostas estruturadas, calcular scores diretos

2. **Mapear para CliftonStrengths (34 temas)**
   - Agrupar indicadores por domínio:
     - Execução: Achiever, Arranger, Belief, Consistency, Deliberative, Discipline, Focus, Responsibility, Restorative
     - Influência: Activator, Command, Communication, Competition, Maximizer, Self-Assurance, Significance, WOO
     - Relacionamento: Adaptability, Connectedness, Developer, Empathy, Harmony, Includer, Individualization, Positivity, Relator
     - Pensamento Estratégico: Analytical, Context, Futuristic, Ideation, Input, Intellection, Learner, Strategic
   - Calcular score de afinidade para os temas com mais evidências

3. **Cruzar com dados de personalidade**
   - Validar que forças identificadas são consistentes com traços:
     - Alta Extroversão + Amabilidade -> forças de Relacionamento e Influência
     - Alta Abertura + Maestria -> forças de Pensamento Estratégico
     - Alta Conscienciosidade -> forças de Execução
   - Aumentar confiança quando há convergência

4. **Distinguir talento natural vs competência desenvolvida**
   - Talento natural: alta facilidade + prazer + flow + sem treinamento formal
   - Competência desenvolvida: alta habilidade + esforço + treinamento formal
   - Registrar classificação para cada força

5. **Identificar forças subutilizadas**
   - Forças com alto potencial (score alto) mas baixa aplicação reportada
   - Oportunidades de desenvolvimento que alavancam talentos existentes

6. **Gerar ranking final**
   - Ordenar forças por score de afinidade
   - Selecionar Top 5-10 (conforme profundidade)
   - Incluir domínio, classificação (talento/competência) e confiança

## Output

- `top-strengths`: Top 5-10 forças com scores e domínios
- `strength-domains`: Distribuição por domínio CliftonStrengths
- `talent-vs-skill`: Classificação talento natural vs competência
- `underused-strengths`: Forças subutilizadas identificadas
- `strength-confidence`: Confiança por força

## Uso

Chamado por `tasks/assessment/run-strengths-layer.md` para classificar as forças do respondente.

## Especificação de I/O

### Input
- Formato: YAML/JSON
- Campos obrigatórios: `strength-responses`, `trait-scores`, `motivation-profile`, `type-result`
- Exemplo: `{strength-responses: [{type: "STAR", text: "Quando liderei o projeto...", keywords: ["liderança", "inovação"]}]}`

### Output
- Formato: YAML
- Campos: `top-strengths`, `strength-domains`, `talent-vs-skill`, `underused-strengths`, `strength-confidence`

### Thresholds
- top_strengths_fast: 5 (modo /fast)
- top_strengths_deep: 10 (modo /deep)
- match_strong: 80% (match forte com CliftonStrengths)
- match_moderate: 60% (match moderado)
- match_discard: 60% (abaixo = descartar)

### Tratamento de Erros
- Input inválido: retornar erro `INVALID_STRENGTH_DATA`
- Dados insuficientes: reduzir para Top 3 com maior evidência e flag `limited-data`
