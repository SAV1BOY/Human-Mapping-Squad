---
type: template
squad: human-mapping
version: "2.0.0"
used_by: [calibration-agent, quality-agent]
---
# Quality Flag Sheet

> Instrucoes: Registre qualquer flag de qualidade identificada durante a sessao. Cada flag deve incluir evidencia concreta e acao tomada. Flags afetam diretamente o Confidence Map.

## Dados da Sessao
- **Session ID:**
- **Respondente:**
- **Assessor:**
- **Data:** YYYY-MM-DD

## Registro de Flags

### Flag #___
- **Tipo de flag:** (ver categorias abaixo)
- **Severidade:** Baixa / Media / Alta / Critica
- **Framework/Instrumento afetado:**
- **Evidencia:**
- **Acao tomada:**
- **Impacto na interpretacao:**
- **Status:** Aberta / Mitigada / Resolvida

### Flag #___
- **Tipo de flag:**
- **Severidade:** Baixa / Media / Alta / Critica
- **Framework/Instrumento afetado:**
- **Evidencia:**
- **Acao tomada:**
- **Impacto na interpretacao:**
- **Status:** Aberta / Mitigada / Resolvida

### Flag #___
- **Tipo de flag:**
- **Severidade:** Baixa / Media / Alta / Critica
- **Framework/Instrumento afetado:**
- **Evidencia:**
- **Acao tomada:**
- **Impacto na interpretacao:**
- **Status:** Aberta / Mitigada / Resolvida

## Categorias de Flags Pre-Definidas

### Inconsistency (Inconsistencia)
- **Descricao:** Respostas contraditorias entre instrumentos ou dentro do mesmo instrumento
- **Exemplos:** Big Five mostra alta amabilidade, mas Hogan HDS indica alto Skeptical
- **Threshold:** Divergencia > 1.5 desvio-padrao entre frameworks equivalentes
- **Acao padrao:** Investigar causa, documentar no Contradiction Map

### Extreme Responding (Respostas Extremas)
- **Descricao:** Padrao de respostas consistentemente nos extremos da escala
- **Exemplos:** Todas as respostas 1 ou 5 em escala Likert
- **Threshold:** >70% das respostas nos extremos da escala
- **Acao padrao:** Avaliar se reflete personalidade real ou vies de resposta

### Midpoint Responding (Tendencia Central)
- **Descricao:** Respostas consistentemente no ponto medio da escala
- **Exemplos:** Maioria das respostas em 3 numa escala de 1-5
- **Threshold:** >60% das respostas no ponto medio
- **Acao padrao:** Verificar fadiga, indecisao ou falta de engajamento

### Random Responding (Respostas Aleatorias)
- **Descricao:** Padrao de respostas sem coerencia logica
- **Exemplos:** Itens reversos com mesma direcao, inconsistencia intra-escala
- **Threshold:** Coeficiente de consistencia interna < 0.50
- **Acao padrao:** Considerar invalidacao do instrumento afetado

### Coaching (Preparacao)
- **Descricao:** Respondente foi preparado ou orientado sobre como responder
- **Exemplos:** Respostas alinham perfeitamente com job description
- **Threshold:** Correlacao suspeitamente alta com perfil ideal do cargo
- **Acao padrao:** Aumentar peso de instrumentos mais dificeis de manipular

## Resumo de Flags

| # | Tipo | Severidade | Status | Impacto no Confidence |
|---|---|---|---|---|
| 1 | | | | -___ pontos |
| 2 | | | | -___ pontos |
| 3 | | | | -___ pontos |

## Impacto Agregado
- **Total de flags:** ___
- **Flags criticas:** ___
- **Reducao estimada no confidence score:** -___
- **Layers mais afetadas:**
- **Recomendacao geral:**
