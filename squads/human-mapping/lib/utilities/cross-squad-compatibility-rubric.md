# Rubrica: Compatibilidade de Dados Cross-Squad

## Objetivo

Garantir que dados de assessment formatados para outros squads sejam compreensíveis, seguros e acionáveis por audiências que não dominam frameworks de mapeamento comportamental.

## Critérios de Avaliação

### 1. Anonimização Adequada (Peso: Crítico)

| Nível | Descrição |
|-------|-----------|
| Aprovado | Dados pessoais removidos ou pseudonimizados; impossível identificar o respondente sem chave externa |
| Parcial | Nome removido mas detalhes contextuais permitem identificação indireta |
| Reprovado | Dados pessoais presentes ou facilmente inferíveis |

**Checklist de anonimização:**
- [ ] Nome completo removido ou substituído por código
- [ ] Cargo específico generalizado (ex: "liderança sênior" em vez de "VP de Marketing")
- [ ] Detalhes situacionais que identifiquem a pessoa foram abstraídos
- [ ] Dados demográficos sensíveis omitidos quando não essenciais

### 2. Escores de Confiança Incluídos (Peso: Alto)

| Nível | Descrição |
|-------|-----------|
| Completo | Cada afirmação tem score de confiança (alto/médio/baixo) com justificativa |
| Parcial | Scores presentes mas sem justificativa ou aplicados apenas a alguns itens |
| Ausente | Afirmações apresentadas como fatos sem qualificação de confiança |

**Formato padrão:**
```
Achado: [descrição]
Confiança: [Alta/Média/Baixa]
Base: [instrumento oficial / proxy convergente / inferência única]
```

### 3. Contexto Explicado para Audiência Não-Especialista (Peso: Alto)

| Nível | Descrição |
|-------|-----------|
| Acessível | Jargão traduzido; frameworks explicados em linguagem prática |
| Técnico-acessível | Termos técnicos presentes mas com glossário ou notas explicativas |
| Inacessível | Assume conhecimento de frameworks específicos sem explicação |

**Regra prática:** Se o squad receptor precisar googlar um termo para entender o dado, o contexto é insuficiente.

### 4. Limitações Declaradas (Peso: Alto)

| Nível | Descrição |
|-------|-----------|
| Transparente | Limitações explícitas: o que os dados NÃO dizem, condições de validade |
| Parcial | Algumas ressalvas mencionadas mas escopo das limitações incompleto |
| Omisso | Dados apresentados sem qualquer qualificação ou limitação |

**Limitações obrigatórias a declarar:**
- Validade temporal (quando o assessment foi feito)
- Contexto da coleta (sessão ao vivo vs. autoaplicação)
- Frameworks não cobertos que seriam relevantes
- Diferença entre preferência e competência

### 5. Acionabilidade para o Squad Receptor (Peso: Médio-Alto)

| Nível | Descrição |
|-------|-----------|
| Acionável | Dados traduzidos em implicações práticas para o contexto do squad receptor |
| Informativo | Dados corretos mas sem tradução para o domínio do receptor |
| Abstrato | Dados teóricos sem conexão com aplicação prática |

**Perguntas-guia:**
- O squad receptor sabe O QUE FAZER com esta informação?
- Os dados estão no nível de granularidade útil para eles?
- Há recomendações específicas ou apenas descrições?

## Matriz de Decisão: Enviar ou Não Enviar

| Critérios aprovados | Decisão |
|---------------------|---------|
| 5/5 | Enviar com confiança |
| 4/5 (falha não-crítica) | Enviar com nota de ressalva |
| 3/5 ou menos | Revisar antes de enviar |
| Anonimização reprovada | NÃO enviar em hipótese alguma |

## Formatos de Entrega por Squad

| Squad Receptor | Formato Preferido | Nível de Detalhe |
|----------------|-------------------|------------------|
| Liderança | Sumário executivo + implicações | Alto nível |
| Produto | Cards de perfil + recomendações | Médio |
| People/RH | Relatório completo com escores | Detalhado |
| Times técnicos | Bullets objetivos + ações | Conciso |

## Validação Final

Antes de enviar dados cross-squad, o facilitador deve responder SIM a todas:
1. Eu ficaria confortável se o respondente visse este documento?
2. O squad receptor consegue usar isto sem me consultar?
3. As limitações estão claras o suficiente para evitar má interpretação?
