# Template: Atualização Metodológica RalphLoop

## Objetivo

Documentar, justificar e planejar qualquer alteração na metodologia de mapeamento, garantindo rastreabilidade, validação e possibilidade de rollback.

## Identificação da Mudança

| Campo | Valor |
|-------|-------|
| **ID da mudança** | RLU-[ANO][MÊS]-[SEQ] |
| **Data da proposta** | [DD/MM/AAAA] |
| **Autor** | [Nome do proponente] |
| **Revisor** | [Nome do revisor — obrigatório para mudanças de impacto alto] |
| **Status** | [Proposta / Em revisão / Aprovada / Implementada / Revertida] |
| **Área afetada** | [Scoring / Rubrica / Template / Processo / Framework / Outro] |

## O Que Mudou

### Descrição da Mudança
[Descrever de forma clara e específica o que está sendo alterado. Incluir o estado anterior e o estado proposto.]

**Estado anterior:**
```
[Descrever como era antes]
```

**Estado proposto:**
```
[Descrever como ficará depois]
```

### Escopo da Mudança
- [ ] Afeta scoring de confiança
- [ ] Afeta rubricas de avaliação
- [ ] Afeta templates de sessão
- [ ] Afeta processo de coleta
- [ ] Afeta interpretação de frameworks
- [ ] Afeta formato de relatório
- [ ] Afeta integração cross-squad

## Por Que Mudou

### Motivação
[Qual problema, ineficiência ou lacuna esta mudança resolve?]

### Trigger
- [ ] Feedback de facilitadores
- [ ] Feedback de respondentes
- [ ] Análise de qualidade interna
- [ ] Novo dado de pesquisa/literatura
- [ ] Mudança em instrumento/framework externo
- [ ] Requisição de outro squad
- [ ] Outro: [especificar]

## Evidência para a Mudança

### Dados que Sustentam a Mudança
| Tipo de Evidência | Descrição | Força |
|-------------------|-----------|-------|
| [Quantitativa/Qualitativa/Literatura] | [__] | [Forte/Moderada/Fraca] |
| [Quantitativa/Qualitativa/Literatura] | [__] | [Forte/Moderada/Fraca] |

### Sessões ou Casos que Motivaram
- Sessão [ID]: [breve descrição do que evidenciou a necessidade]
- Sessão [ID]: [breve descrição]

### Referências Externas (se aplicável)
- [Artigo, manual, pesquisa que embasa a mudança]

## Impacto no Scoring

| Critério | Antes | Depois | Direção do Impacto |
|----------|-------|--------|-------------------|
| [Critério de scoring afetado] | [valor/regra] | [valor/regra] | [Mais restritivo / Mais leniente / Neutro] |

### Sessões Retroativas Afetadas
- [ ] Mudança NÃO é retroativa (aplica-se apenas a novas sessões)
- [ ] Mudança É retroativa — plano de reclassificação:
  - Sessões afetadas: [quantidade estimada]
  - Plano: [como serão reavaliadas]

## Impacto em Rubricas

| Rubrica Afetada | Tipo de Alteração | Detalhamento |
|-----------------|-------------------|-------------|
| [Nome da rubrica] | [Critério alterado / Novo critério / Critério removido] | [__] |

## Plano de Validação

### Como Saber se a Mudança Funciona
| Métrica | Valor Esperado | Prazo de Avaliação |
|---------|---------------|-------------------|
| [O que medir] | [Meta] | [Após X sessões ou Y semanas] |

### Piloto
- [ ] Mudança será pilotada antes de implementação geral
  - Escopo do piloto: [__]
  - Duração: [__]
  - Critérios de sucesso: [__]
- [ ] Mudança será implementada diretamente (justificar): [__]

## Plano de Rollback

### Condições para Reversão
- [Condição 1 que justificaria reverter a mudança]
- [Condição 2]

### Procedimento de Rollback
1. [Passo 1 para reverter ao estado anterior]
2. [Passo 2]
3. [Notificação a facilitadores e squads afetados]

### Dados a Preservar
- [ ] Sessões realizadas durante o piloto serão reclassificadas
- [ ] Sessões durante o piloto mantêm classificação do momento

## Comunicação

| Audiência | Formato | Prazo |
|-----------|---------|-------|
| Facilitadores | [Reunião / Documento / Canal] | [Antes da implementação] |
| Squads afetados | [Briefing / Nota] | [Na implementação] |
| Respondentes (se aplicável) | [__] | [__] |

## Aprovação

| Papel | Nome | Data | Status |
|-------|------|------|--------|
| Proponente | [__] | [__] | Proposto |
| Revisor | [__] | [__] | [Aprovado/Rejeitado/Revisão solicitada] |
| Implementador | [__] | [__] | [Implementado] |
