# Gold Standard e Estado da Arte (SOTA)

## Visão Geral
Este documento define o gold standard de avaliação de personalidade adotado pelo
squad e resume o estado da arte (SOTA) na área, servindo como referência para
decisões metodológicas e calibração de qualidade.

## Conteúdo

### Gold Standard do Squad
O Big Five (Five-Factor Model) é o gold standard para avaliação de traços de
personalidade, baseado em décadas de pesquisa e validação transcultural.

**Instrumento de referência**: NEO-PI-R (Costa & McCrae)
- 5 domínios, 30 facetas
- Alta confiabilidade teste-reteste
- Validação transcultural extensiva
- Prediz resultados organizacionais e de saúde

### Estado da Arte (SOTA)
| Área | SOTA atual | Tendência |
|------|-----------|-----------|
| Traços | Big Five / HEXACO | HEXACO ganha adoção |
| Liderança | Hogan Assessments | Integração com IA |
| Forças | CliftonStrengths | Abordagem baseada em evidências |
| Equipe | Belbin + análise de rede | Modelos dinâmicos |
| Vocacional | RIASEC + O*NET | Integração com dados de mercado |
| Neurociência | Correlatos neurais de traços | Ainda experimental |

### Tendências emergentes
1. Avaliação baseada em dados digitais (pegadas digitais)
2. IA para predição de personalidade a partir de texto
3. Modelos dinâmicos de personalidade (mudança ao longo do tempo)
4. Integração de múltiplos frameworks via machine learning
5. Personalização de instrumentos conforme contexto cultural

### Posição do squad
Adotamos uma postura conservadora: incorporamos novas metodologias apenas após
validação independente suficiente, mantendo o Big Five como âncora principal.

## Referências
- Costa, P.T. & McCrae, R.R. (1992). NEO-PI-R Professional Manual
- Ashton, M.C. & Lee, K. (2007). HEXACO Model of Personality
- Hogan, R. & Kaiser, R.B. (2005). What We Know About Leadership

### O que separa um assessment SOTA de um assessment "apenas bom"

Um assessment "bom" aplica instrumentos corretamente e gera um relatório legível.
Um assessment SOTA vai além em cinco dimensões críticas:

**1. Prevenção de Efeito Barnum**
O efeito Barnum (ou Forer) ocorre quando descrições são tão genéricas que qualquer
pessoa se identifica. Um assessment SOTA combate isso com: especificidade de
percentil (não "você é criativo" mas "Abertura no percentil 72 — acima de 72% da
população de referência"), exemplos comportamentais concretos derivados da entrevista
(não templates genéricos), e o teste interno: "essa frase poderia ser dita para
qualquer pessoa? Se sim, reescreva ou remova."

**2. Densidade de Evidência**
Cada afirmação no relatório SOTA é rastreável a pelo menos uma fonte de dados.
Se diz "o respondente tem tendência a evitar conflito", deve citar: Amabilidade 85
(Big Five), S alto (DISC), MVS Blue (SDI), e preferencialmente um exemplo
comportamental da entrevista. Afirmações sem evidência são hipóteses — e devem
ser marcadas como tal.

**3. Transparência de Confiança**
Assessment SOTA nunca apresenta resultados sem score de confiança. Cada camada
tem sua confiança individual. A síntese tem confiança global. Resultados com
confiança abaixo de 0.7 são sinalizados explicitamente. O leitor do relatório
sempre sabe o quanto pode confiar em cada afirmação. Isso é o oposto da maioria
dos assessments de mercado que apresentam tudo com a mesma certeza aparente.

**4. Convergência Multi-Framework como Validação**
O poder do assessment SOTA está na triangulação. Quando Big Five, Enneagram, DISC
e CliftonStrengths apontam para o mesmo traço, a confiança é alta. Quando divergem,
isso é sinal — não ruído. O relatório SOTA mapeia explicitamente convergências
(com score), divergências (com hipóteses de resolução) e contradições abertas
(com transparência sobre o que não sabemos).

**5. Filosofia de Contradição-como-Sinal**
Na abordagem convencional, contradições entre instrumentos são tratadas como erro
ou são ignoradas. Na filosofia SOTA do squad, contradições são os dados mais
informativos. Uma contradição pode revelar: adaptação contextual (a pessoa se
comporta diferente em casa vs. trabalho), mudança temporal (a pessoa está em
transição), desejabilidade social (a pessoa responde como acha que deveria, não
como realmente é), ou limitação do instrumento para aquele perfil específico.
O assessment SOTA investiga cada contradição e registra a resolução — ou a
ausência dela, com honestidade.

### Checklist de Qualidade SOTA

| Critério | Bom | SOTA |
|---|---|---|
| Frameworks utilizados | 1-2 | 3-6, com triangulação explícita |
| Score de confiança | Ausente ou global único | Por camada + global + metodologia |
| Efeito Barnum | Presente em partes | Eliminado sistematicamente |
| Contradições | Ignoradas ou ocultas | Investigadas e documentadas |
| Evidência por afirmação | Implícita | Rastreável a fonte específica |
| Plano de desenvolvimento | Genérico | Baseado em gaps inter-framework |
| Devolutiva | Unidirecional | Dialógica (respondente contesta e complementa) |
| Viés cultural | Não mencionado | Explicitado e mitigado |

### Anti-patterns a Evitar

1. **Relatório-horóscopo:** Frases que servem para qualquer pessoa. "Você é
   alguém que valoriza conexões autênticas" — isso é Barnum puro.
2. **Framework-único como verdade:** Usar apenas MBTI ou apenas DISC e apresentar
   como retrato completo. Um framework é uma lente, não a realidade.
3. **Confiança inflada:** Apresentar proxy-inference com a mesma certeza de
   assessment direto. Se é proxy, marque como proxy.
4. **Desenvolvimento genérico:** "Trabalhe sua comunicação" sem especificar
   que dimensão, em que contexto, e baseado em que evidência.
5. **Ignorar desejabilidade social:** Não investigar quando todos os scores
   são "perfeitos demais". Perfil sem nenhuma tensão provavelmente é máscara.
