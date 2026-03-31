---
type: rubric
squad: human-mapping
version: "2.0.0"
---

# Contradiction Severity Rubric

## Proposito

Fornecer criterios claros para avaliar a severidade de contradicoes encontradas durante
a analise de perfil, determinar o impacto no confidence score e definir acoes apropriadas
para cada nivel. Esta rubric complementa a Contradiction Taxonomy, adicionando criterios
operacionais de avaliacao.

## Escala de Avaliacao

| Nivel | Severidade | Range de Impacto | Cor |
|-------|-----------|-----------------|-----|
| 1 | Low | Nenhum impacto | Verde |
| 2 | Medium | Reduz confidence 0.05-0.10 | Amarelo |
| 3 | High | Reduz confidence 0.15-0.25 | Laranja |
| 4 | Critical | Reduz confidence 0.30+ ou invalida | Vermelho |

## Criterios por Nivel

### Level 1: Low — Facetas Diferentes do Mesmo Construto

**Definicao**: A contradicao ocorre entre subdimensoes ou facetas, nao entre
construtos principais. Reflete nuance e complexidade, nao erro nos dados.

**Criterios para classificar como Low**:
- Os dados conflitantes pertencem ao MESMO framework
- A contradicao ocorre no nivel de FACETA, nao de dominio
- Ha explicacao teorica plausivel dentro do framework
- O respondente provavelmente reconheceria a nuance como verdadeira

**Exemplos**:
- Big Five Extraversion: Warmth alta + Gregariousness baixa
  → Pessoa calorosa em interacoes intimas mas evita grandes grupos
- CliftonStrengths: Deliberative (#3) + Activator (#8)
  → Cauteloso na decisao mas rapido na execucao uma vez decidido
- Enneagram 1 com wing 2 vs wing 9 ambos moderados
  → Complexidade normal do sistema

**Acao recomendada**:
- Documentar como nuance enriquecedora do perfil
- Usar na narrativa para mostrar complexidade ("Por um lado... por outro...")
- NAO reduzir confidence score
- Tempo: 5 minutos para documentar

### Level 2: Medium — Conflito Parcial entre Frameworks

**Definicao**: Dados de frameworks diferentes apontam em direcoes parcialmente
opostas, mas ha explicacoes contextuais ou metodologicas plausiveis.

**Criterios para classificar como Medium**:
- Os dados conflitantes vem de frameworks DIFERENTES
- A contradicao e PARCIAL (nao diametralmente oposta)
- Existe pelo menos uma explicacao plausivel sem necessidade de investigacao profunda
- O conflito envolve construtos RELACIONADOS mas nao identicos

**Exemplos**:
- Big Five E percentil 60 + MBTI preferencia leve por Introversion
  → Zona intermediaria, ambos os resultados sao borderline
- DISC I moderado + Enneagram tipo 5
  → I pode refletir adaptacao social, tipo 5 e core motivation
- SDI Green (autonomia) + CliftonStrengths Includer no Top 10
  → Autonomia no trabalho, inclusao como valor — contextos diferentes

**Acao recomendada**:
- Investigar brevemente: contexto de aplicacao, datas, estado do respondente
- Buscar uma terceira fonte de dados que desempate
- Reduzir confidence em 0.05-0.10 para as afirmacoes afetadas
- Documentar a contradicao e a hipotese explicativa
- Tempo: 15 minutos para investigar e documentar

### Level 3: High — Oposicao Direta entre Construtos

**Definicao**: Dois ou mais construtos de frameworks diferentes apontam em
direcoes CLARAMENTE opostas, com pouca ou nenhuma explicacao simples.

**Criterios para classificar como High**:
- Os dados sao diametralmente opostos (nao apenas parcialmente conflitantes)
- A contradicao envolve construtos que DEVERIAM convergir teoricamente
- Nao ha explicacao obvia sem investigacao aprofundada
- O conflito afeta conclusoes significativas do perfil

**Exemplos**:
- Big Five E percentil 90 + MBTI I com preferencia muito clara + DISC S puro
  → Tres fontes, duas contra uma, oposicao extrema
- Enneagram tipo 8 (controle, poder) + SDI Blue (altruismo puro) + Reiss Power baixo
  → Motivacao de poder vs altruismo em multiplos frameworks
- CliftonStrengths Top 5 todos Relationship Building + Belbin Shaper + DISC D alto
  → Strengths relacionais vs estilo comportamental diretivo

**Acao recomendada**:
- Parar a sintese ate investigar
- Entrevistar o respondente especificamente sobre a discrepancia
- Verificar condicoes de aplicacao de cada assessment
- Considerar se um resultado pode ser invalido (social desirability, fadiga, etc.)
- Reduzir confidence em 0.15-0.25 para as afirmacoes afetadas
- Tempo: 30 minutos para investigacao + possivel entrevista

### Level 4: Critical — Potencialmente Invalidante

**Definicao**: A contradicao e tao severa que questiona a validade de um ou
mais assessments completos, impossibilitando conclusoes confiaveis.

**Criterios para classificar como Critical**:
- MULTIPLAS contradicoes High simultaneas no mesmo perfil
- OU um unico conflito que invalida a premissa central de um assessment
- Os dados sao irreconciliaveis sem reaplicacao
- Nenhuma explicacao contextual resolve o conflito

**Exemplos**:
- TODOS os assessments apontam direcoes diferentes sem qualquer padrao
  → Dados provavelmente corrompidos ou respondente inconsistente
- Respostas do assessment contradizem observacao direta flagrantemente
  → Respondente pode ter respondido sem seriedade
- DISC mostra perfil completamente plano (todos percentis em 50)
  → Assessment possivelmente invalido

**Acao recomendada**:
- INTERROMPER a analise imediatamente
- Verificar integridade dos dados (erro de digitacao, troca de respondente?)
- Contatar fonte dos dados para verificacao
- Considerar reaplicacao dos assessments
- Se nao resolvel: reportar com confidence < 0.4 e caveats explicitos
- Reduzir confidence em 0.30+ ou marcar todo o perfil como "preliminar"
- Tempo: 60+ minutos, pode requerer nova sessao

## Como Aplicar

### Passo 1: Identificar todas as contradicoes
Usar as 5 categorias da Contradiction Taxonomy para busca sistematica.

### Passo 2: Classificar severidade
Para cada contradicao, aplicar os criterios acima para determinar o Level.

### Passo 3: Priorizar resolucao
| Ordem | Acao |
|-------|------|
| 1o | Resolver todas as Level 4 (Critical) |
| 2o | Investigar todas as Level 3 (High) |
| 3o | Documentar todas as Level 2 (Medium) |
| 4o | Incorporar Level 1 (Low) na narrativa |

### Passo 4: Ajustar confidence scores
Aplicar reducoes conforme tabela de cada nivel.

### Passo 5: Documentar no report
Incluir secao "Contradicoes Identificadas" com:
- Descricao da contradicao
- Severidade classificada
- Investigacao realizada
- Resolucao alcancada (ou nao)
- Impacto no confidence do perfil

## Exemplos

### Exemplo Completo: Perfil com Multiplas Contradicoes

**Dados disponiveis**:
- Big Five: E=85, O=70, A=35, C=60, N=40
- MBTI: ENTJ
- DISC: D alto, I moderado
- Enneagram: tipo 2w3
- CliftonStrengths Top 5: Achiever, Command, Strategic, Empathy, Developer

**Contradicoes encontradas**:
1. Big Five A=35 (baixo) + Enneagram tipo 2 (Helper) = **Level 3 (High)**
   - Agreabilidade baixa + motivacao de ajudar outros = oposicao direta
   - Hipotese: tipo 2 pode usar ajuda como ferramenta de influencia (2w3), nao de concordancia
2. CliftonStrengths Command (#2) + Empathy (#4) no mesmo Top 5 = **Level 1 (Low)**
   - Aparente tensao, mas ambos podem coexistir (lider assertivo mas empático)
3. DISC D alto + Enneagram tipo 2 = **Level 2 (Medium)**
   - Dominancia + Helper — parcialmente conflitante
   - Hipotese: 2w3 pode ser assertivo na forma de "ajudar dirigindo"

**Acoes**: Investigar contradicao #1 (High) antes de prosseguir. Documentar #2 e #3.
**Confidence ajustado**: Reducao de 0.15 por #1 ate resolucao.
