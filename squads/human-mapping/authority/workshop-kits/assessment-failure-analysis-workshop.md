# Workshop: Analise de Falhas em Assessment

## Visao Geral

Workshop pratico para aprender com erros de assessment. Os participantes
analisam casos reais (anonimizados) de assessments que falharam, identificam
o que deu errado e desenvolvem estrategias de prevencao.

## Publico-Alvo

- Avaliadores em formacao e avaliadores experientes
- Gestores que usam dados de assessment para decisoes
- Qualquer membro do Human-Mapping Squad

## Duracao

- 3 horas (com intervalo de 15 minutos)

## Materiais Necessarios

- Casos anonimizados de assessment com falha (minimo 3)
- Template de analise de falha (fornecido abaixo)
- Quadro branco ou Miro para mapeamento coletivo
- Checklist de anti-patterns (ver `lib/patterns/assessment-failure-antipattern.md`)

## Estrutura do Workshop

### Bloco 1 — Contextualizacao (30 min)

**Facilitador apresenta**:
- Por que estudar falhas e mais util do que estudar sucessos
- Taxonomia de erros em assessment (framework, interpretacao, contexto, vies, comunicacao)
- Estatisticas de precisao: nenhum assessment e 100% preciso
- Cultura de "nao-culpa" — o objetivo e aprender, nao punir

**Discussao em grupo**:
- "Alguem ja viveu ou testemunhou um assessment que errou?" (sem nomes)
- "O que sentiu? O que fez?"

### Bloco 2 — Analise de Caso em Grupo (60 min)

**Exercicio**: Dividir em grupos de 3-4 pessoas. Cada grupo recebe um caso
de assessment com falha (anonimizado) contendo:
- Contexto do assessment
- Instrumentos utilizados
- Conclusoes do avaliador
- O que realmente aconteceu depois

**Cada grupo deve preencher o Template de Analise**:

```
CASO: [Titulo do caso]

1. QUAL FOI O ERRO PRINCIPAL?
   [ ] Framework unico
   [ ] Rotulacao prematura
   [ ] Ignorou contradicoes
   [ ] Efeito Barnum
   [ ] Patologizou diferenca
   [ ] Vies do avaliador
   [ ] Pressao politica
   [ ] Outro: ___

2. EM QUE ESTAGIO DO PIPELINE O ERRO OCORREU?
   [ ] Coleta  [ ] Validacao  [ ] Scoring  [ ] Interpretacao  [ ] Entrega

3. O ERRO ERA EVITAVEL? COMO?
   ___

4. QUE SINAIS DE ALERTA FORAM IGNORADOS?
   ___

5. QUAL SERIA A ABORDAGEM CORRETA?
   ___

6. QUE REGRA OU CHECKLIST PREVENIRIA ESSE ERRO?
   ___
```

### Bloco 3 — Apresentacao e Debate (45 min)

- Cada grupo apresenta seu caso e analise (10 min por grupo)
- Outros grupos desafiam e complementam
- Facilitador destaca padroes que aparecem em multiplos casos
- Construcao coletiva de "muro de sabedoria" com licoes-chave

### Bloco 4 — Construcao de Salvaguardas (30 min)

**Exercicio coletivo**: baseado nos padroes identificados, o grupo constroi:

1. **Top 5 regras inviolaveis** do assessment no squad
2. **Checklist pre-entrega** — verificacoes antes de finalizar qualquer relatorio
3. **Protocolo de escalacao** — quando pedir segunda opiniao
4. **Ritual de retrospectiva** — como integrar revisao de falhas na rotina

## Criterios para Selecao de Casos

Bons casos para o workshop devem ter:
- Erro claro e identificavel (nao ambiguo demais)
- Consequencias reais documentadas
- Pelo menos uma licao transferivel para outros contextos
- Anonimizacao completa (nenhum dado identificavel)

## Follow-Up

- Participantes recebem compilado de licoes aprendidas em 48h
- Cada participante se compromete com uma mudanca pratica no seu processo
- Check-in em 30 dias para verificar implementacao
- Workshop repetido semestralmente com casos novos

## Regras do Workshop

1. Confidencialidade total — nada sai da sala com identificacao
2. Sem julgamento — errar e humano, nao aprender e escolha
3. Foco em sistema, nao em pessoa — "o processo falhou" vs "fulano errou"
4. Honestidade radical — compartilhar erros proprios e valorizado
