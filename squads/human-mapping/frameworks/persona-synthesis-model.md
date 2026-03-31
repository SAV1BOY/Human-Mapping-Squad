---
framework: persona-synthesis-model
category: operational
squad: human-mapping
version: "2.0.0"
---

# Persona Synthesis Model

## Propósito

O Persona Synthesis Model é o framework de integração final que combina todas as camadas de assessment em um mapa unificado e coerente da pessoa. Cada instrumento mede uma faceta; a síntese monta o quebra-cabeça completo. Sem síntese, o resultado é uma coleção de dados desconectados. Com síntese, o resultado é um retrato holístico e acionável.

A síntese não é uma média dos instrumentos. É uma narrativa integrada onde cada camada tem um papel definido: traços são a base, tipos são a expressão, motivação é o motor, forças são o recurso, carreira é a direção e ação é a execução. Cada camada tem um peso diferente dependendo do contexto.

## Quando Usar

- Após todos os instrumentos terem sido aplicados e reconciliados
- Após o Cross-Framework Reconciliation ter resolvido conflitos
- Antes de montar o Executive Brief ou relatório completo
- Quando é necessário comunicar o "todo" da pessoa de forma coerente
- Em sessões de devolutiva para apresentar o perfil integrado

## Modelo / Estrutura

### Hierarquia de Integração

```
CAMADA 6: AÇÃO (como executa)
    Kolbe, padrões de execução observados
         ↑
CAMADA 5: CARREIRA (para onde vai)
    Holland, Schein, Super, direção vocacional
         ↑
CAMADA 4: FORÇAS (com que recursos)
    CliftonStrengths, VIA Strengths, competências observadas
         ↑
CAMADA 3: MOTIVAÇÃO (por que se move)
    Reiss, Schwartz, Eneagrama (motivação core), Birkman needs
         ↑
CAMADA 2: EXPRESSÃO (como se apresenta)
    MBTI, DISC, Birkman usual, Belbin, estilo interpessoal
         ↑
CAMADA 1: BASE (quem é)
    Big Five, Hogan, HEXACO, traços estáveis, identidade central
```

### Pesos por Camada (por Contexto)

| Camada | Contratação | Desenvolvimento | Liderança | Equipe | Carreira |
|--------|-------------|-----------------|-----------|--------|----------|
| Base (Traços) | 0.30 | 0.20 | 0.25 | 0.15 | 0.15 |
| Expressão (Tipos) | 0.20 | 0.15 | 0.20 | 0.25 | 0.10 |
| Motivação | 0.15 | 0.25 | 0.20 | 0.15 | 0.25 |
| Forças | 0.15 | 0.25 | 0.15 | 0.20 | 0.20 |
| Carreira | 0.10 | 0.05 | 0.05 | 0.05 | 0.25 |
| Ação | 0.10 | 0.10 | 0.15 | 0.20 | 0.05 |

### Template de Síntese

```markdown
# Síntese Integrada: [Nome da Pessoa]

## Essência (quem é esta pessoa em uma frase)
[Frase integrativa que captura a identidade central]

## Base (Traços)
- Traço dominante: [Big Five / Hogan principal]
- Padrão de personalidade: [descrição narrativa]
- Estabilidade emocional: [nível e impacto]
- Confidence desta camada: [0.0 - 1.0]

## Expressão (Tipos e Estilos)
- Tipo primário: [MBTI / DISC / Eneagrama]
- Estilo interpessoal: [como se apresenta aos outros]
- Adaptações identificadas: [onde se adapta vs identidade]
- Confidence desta camada: [0.0 - 1.0]

## Motor (Motivação)
- Motivadores primários: [top 3 drivers]
- Necessidades não negociáveis: [Birkman needs / Reiss]
- O que energiza: [atividades, contextos, relações]
- O que drena: [atividades, contextos, relações]
- Confidence desta camada: [0.0 - 1.0]

## Recursos (Forças)
- Top 5 forças: [CliftonStrengths / VIA]
- Domínio dominante: [Executing/Influencing/Relationship/Strategic]
- Como as forças se combinam: [padrão de uso]
- Forças em excesso (risco): [quando a força vira fraqueza]
- Confidence desta camada: [0.0 - 1.0]

## Direção (Carreira)
- Perfil vocacional: [Holland RIASEC]
- Âncoras de carreira: [Schein]
- Alinhamento atual: [grau de fit com posição atual]
- Confidence desta camada: [0.0 - 1.0]

## Execução (Ação)
- Modo de ação: [Kolbe / padrões observados]
- Como inicia: [Quick Start]
- Como mantém: [Follow Thru]
- Como coleta informação: [Fact Finder]
- Como implementa: [Implementor]
- Confidence desta camada: [0.0 - 1.0]

## Mapa de Contradições Resolvidas
[Lista de contradições encontradas e como foram reconciliadas]

## Confidence Global
Score composto: [0.0 - 1.0]
Camadas com maior confiança: [lista]
Camadas com menor confiança: [lista]
Recomendações para aumentar confiança: [lista]
```

## Como Aplicar (step by step)

### Step 1: Reunir Todos os Resultados
- Compilar resultados de todas as camadas aplicadas
- Incluir as reconciliações do Cross-Framework Reconciliation
- Incluir o Confidence Score de cada camada
- Incluir o mapa de Adaptation vs Identity

### Step 2: Começar pela Base (Camada 1)
- Redigir o perfil de traços como fundação
- Esta é a camada mais estável e empiricamente sólida
- Usar como "moldura" para tudo que vier depois

### Step 3: Adicionar Expressão (Camada 2)
- Como os traços base se EXPRESSAM no mundo?
- Onde há adaptação? Onde há identidade pura?
- Como a pessoa se comunica, se relaciona, toma decisões?

### Step 4: Identificar o Motor (Camada 3)
- O que MOVE esta pessoa? Por que ela faz o que faz?
- Quais são os drivers internos (Reiss, Eneagrama)?
- Quais são as necessidades (Birkman needs)?
- O motor explica os comportamentos das camadas 1 e 2?

### Step 5: Mapear Recursos (Camada 4)
- Quais são os talentos naturais (CliftonStrengths)?
- Quais forças de caráter (VIA)?
- Como a pessoa usa esses recursos? Usa bem? Subutiliza? Overuse?

### Step 6: Identificar Direção (Camada 5)
- Para onde o perfil aponta? Que tipo de trabalho/carreira se alinha?
- O cargo atual está alinhado com o perfil?
- Quais são as âncoras de carreira não negociáveis?

### Step 7: Entender Execução (Camada 6)
- COMO a pessoa coloca tudo em prática?
- Qual o modo natural de ação (Kolbe)?
- Onde modo de ação e identidade estão alinhados? Desalinhados?

### Step 8: Integrar na Narrativa
- Redigir a "Essência" em uma frase
- Verificar se as camadas se conectam logicamente
- Onde não se conectam, referenciar a reconciliação
- Revisar se a narrativa "soa" como uma pessoa real

### Step 9: Calibrar Confiança
- Atribuir confidence score a cada camada
- Calcular confidence global
- Destacar onde conclusões são firmes vs tentativas

## Critérios de Qualidade

| Critério | Indicador |
|----------|-----------|
| Coerência narrativa | As camadas se conectam numa história que faz sentido |
| Completude | Todas as camadas aplicadas estão representadas |
| Hierarquia respeitada | Traços como base, não tipos; motivação como motor, não forças |
| Nuance preservada | Contradições são explicadas, não eliminadas |
| Acionabilidade | A síntese gera insights para o objetivo do assessment |
| Confiança documentada | O leitor sabe onde a síntese é firme vs tentativa |

## Integração com Pipeline

### Input
- Resultados de todas as camadas
- Reconciliações do **Cross-Framework Reconciliation**
- Mapa de **Adaptation vs Identity Model**
- Confidence scores do **Confidence Scoring Model**

### Output
- Síntese integrada → **Executive Brief Model** (versão resumida)
- Base para → **Development Prioritization**
- Base para → **Workplace Behavior Map**

### Posição no Pipeline
```
[Todas as Camadas] → [Reconciliação] → [Persona Synthesis Model] → [Executive Brief]
                                                ↓                          ↓
                                    [Development Plan]        [Relatório Completo]
```

## Exemplos

### Exemplo: Síntese Resumida - "Ana, Product Manager"

**Essência**: Ana é uma pensadora estratégica com energia social seletiva, movida por impacto e autonomia, que executa de forma metódica mas inicia com ímpeto criativo.

- **Base**: Big Five: O alto (82), C moderado-alto (68), E moderado (52), A moderado (48), N baixo (25). Hogan: Ambition e Inquisitive elevados. Perfil estável e confiante.
- **Expressão**: MBTI ENTJ (preferência por estrutura e estratégia). DISC: D-C (diretiva e analítica). Birkman usual extrovertido, needs introvertido → adaptação Tipo B.
- **Motor**: Eneagrama Tipo 3 (asa 4). Reiss: Power alto, Independence alto, Curiosity alto. Motivada por realização com toque de individualidade criativa.
- **Recursos**: CliftonStrengths Top 5: Strategic, Ideation, Achiever, Command, Futuristic. Dominante em Strategic Thinking + Influencing.
- **Direção**: Holland: EIA (Enterprising-Investigative-Artistic). Schein: Empreendedorismo + Desafio Puro. Bem alinhada com PM Senior/Head de Produto.
- **Execução**: Kolbe: QS 7, FF 6, FT 5, IMP 3. Inicia com impulso criativo, pesquisa moderadamente, mantém razoavelmente, delega implementação física.
- **Confidence Global**: 0.82. Camada mais forte: Base (0.92). Camada mais fraca: Carreira (0.68, proxy only).
