---
type: template
squad: human-mapping
version: "2.0.0"
used_by: [chief, synthesis-architect, contradiction-auditor]
---

# Quality Improvement Tracking (RalphLoop)

> Instrucoes: Use este template para documentar e acompanhar melhorias de qualidade identificadas durante retrospectivas (RalphLoop) ou durante o pipeline de assessment. Cada issue identificada deve ser rastreada desde a deteccao ate a validacao da melhoria.

## Dados Gerais
- **ID da melhoria:** QI-___
- **Data de identificacao:** ___
- **Identificado por:** (agente / chief / respondente / audit)
- **Sessao(oes) de origem:** ___
- **Prioridade:** (Critica / Alta / Media / Baixa)
- **Status:** (Identificado / Em Analise / Implementando / Validando / Concluido / Rejeitado)

## Issue Identificada

### Descricao do Problema
___

### Onde no Pipeline o Problema Ocorre
- **Fase:** (Intake / Calibracao / Assessment / Sintese / Report / Devolutiva)
- **Agente responsavel:** ___
- **Frequencia observada:** (Unica / Ocasional / Frequente / Sistematica)

### Impacto
- **Na qualidade do output:** ___
- **No confidence score:** ___
- **Na experiencia do respondente:** ___

### Evidencia
- Exemplo concreto 1: ___
- Exemplo concreto 2: ___

## Analise de Causa Raiz

### Causa Identificada
___

### Categoria da Causa
- [ ] Processo: etapa do pipeline ausente ou mal definida
- [ ] Dados: qualidade ou disponibilidade de dados insuficiente
- [ ] Ferramenta: framework ou instrumento inadequado para o contexto
- [ ] Competencia: agente sem conhecimento ou calibracao suficiente
- [ ] Comunicacao: informacao perdida entre agentes no pipeline
- [ ] Escopo: expectativa do respondente fora do escopo do mapeamento

### Analise dos 5 Porques
1. Por que o problema ocorreu? ___
2. Por que [causa 1]? ___
3. Por que [causa 2]? ___
4. Por que [causa 3]? ___
5. Por que [causa 4]? ___

## Acao de Melhoria

### Descricao da Melhoria
___

### Tipo de Melhoria
- [ ] Novo checklist ou gate de qualidade
- [ ] Atualizacao de template existente
- [ ] Novo pattern na biblioteca
- [ ] Ajuste em script de analise
- [ ] Atualizacao de rubrica
- [ ] Mudanca no workflow do pipeline
- [ ] Novo treinamento ou calibracao de agente

### Arquivos Afetados
- ___

### Implementacao
- **Responsavel:** ___
- **Prazo:** ___
- **Dependencias:** ___

## Validacao

### Metrica de Sucesso
- **Antes da melhoria:** ___
- **Meta apos melhoria:** ___

### Metodo de Validacao
- [ ] Comparacao de confidence scores antes/depois
- [ ] Review de proximas N sessoes
- [ ] Feedback do respondente
- [ ] Audit do chief
- [ ] Reducao de contradicoes nao resolvidas
- [ ] Outro: ___

### Resultado da Validacao
- **Data da validacao:** ___
- **Metrica alcancada:** ___
- **Status:** (Sucesso / Parcial / Falha — requer iteracao)

## Plano de Rollback

Caso a melhoria gere efeitos colaterais negativos:
- **Sinais de que o rollback e necessario:** ___
- **Como reverter:** ___
- **Arquivos a restaurar:** ___

## Aprendizados

### O que funcionou
- ___

### O que nao funcionou
- ___

### Recomendacoes para futuro
- ___

## Historico de Atualizacoes
| Data | Autor | Mudanca |
|------|-------|---------|
| ___ | ___ | ___ |
