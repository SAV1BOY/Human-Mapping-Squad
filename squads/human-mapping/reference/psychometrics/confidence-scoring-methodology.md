---
type: reference
category: psychometrics
squad: human-mapping
version: "2.0.0"
---

# Metodologia de Pontuacao de Confianca

## Resumo

A pontuacao de confianca e o mecanismo pelo qual o Assessment OS comunica o grau de certeza de cada inferencia realizada. Diferente de instrumentos psicometricos que reportam escores padronizados, o sistema de proxy exige uma camada adicional de transparencia: para cada dimensao avaliada, um nivel de confianca indica quao robusta e a evidencia que sustenta aquela conclusao.

## Conceitos Principais

### Fundamento Estatistico

- Em estatistica, intervalos de confianca indicam a faixa dentro da qual o valor real provavelmente se encontra.
- No Assessment OS, a confianca nao e calculada estatisticamente, mas estimada com base em criterios qualitativos sistematicos.
- A inspiracao vem da logica bayesiana: cada nova evidencia atualiza a probabilidade da hipotese.
- O sistema prioriza transparencia sobre precisao numerica aparente.

### Criterios para Atribuicao de Confianca

- **Quantidade de evidencias**: Quantas fontes de dados sustentam a inferencia?
- **Qualidade das evidencias**: As evidencias sao comportamentais concretas ou genericas?
- **Convergencia entre frameworks**: Os frameworks concordam sobre essa dimensao?
- **Consistencia temporal**: O padrao se repete em diferentes momentos da vida?
- **Ausencia de vieses identificados**: Ha indicios de desejabilidade social ou outros vieses?

### Escala de Confianca

| Nivel | Faixa | Criterios |
|-------|-------|-----------|
| Muito Alto | 90-95% | 4+ evidencias convergentes, multiplos frameworks, consistencia temporal |
| Alto | 75-89% | 3+ evidencias convergentes, pelo menos 2 frameworks |
| Moderado | 60-74% | 2 evidencias, alguma convergencia entre frameworks |
| Baixo | 45-59% | Evidencia unica ou parcialmente conflitante |
| Muito Baixo | 30-44% | Evidencia escassa ou significativamente conflitante |
| Insuficiente | <30% | Dados insuficientes para inferencia |

### Fatores que Reduzem a Confianca

- Respostas excessivamente curtas ou evasivas durante a entrevista.
- Inconsistencias entre relato verbal e comportamento observado.
- Forte presenca de desejabilidade social nas respostas.
- Divergencia significativa entre frameworks.
- Contexto de avaliacao de alto risco (ex: selecao para cargo) aumentando pressao sobre o respondente.

### Fatores que Aumentam a Confianca

- Relatos comportamentais detalhados com contexto especifico.
- Reconhecimento espontaneo de fraquezas e areas de desenvolvimento.
- Convergencia entre autoavaliacao e observacao do avaliador.
- Consistencia entre diferentes perguntas que avaliam a mesma dimensao.
- Multiplas sessoes de entrevista ao longo do tempo.

## Relevancia para o Assessment OS

A pontuacao de confianca e o que diferencia o Assessment OS de sistemas que apresentam resultados como fatos absolutos. Ao comunicar explicitamente o grau de certeza, o sistema respeita as limitacoes do metodo e permite que usuarios e coaches tomem decisoes informadas sobre quais aspectos do perfil merecem mais atencao.

## Aplicacao Pratica

1. Atribuir nivel de confianca a cada dimensao, nao apenas ao perfil geral.
2. Nunca apresentar confianca acima de 95%, reconhecendo as limitacoes inerentes do metodo.
3. Documentar os fatores que sustentam cada nivel de confianca atribuido.
4. Recalcular confianca quando novas evidencias sao incorporadas.
5. Comunicar claramente ao respondente o significado dos niveis de confianca.
6. Usar niveis baixos como gatilho para coleta de dados adicionais.

## Referencias

- Kahneman, D. (2011). Thinking, Fast and Slow. Farrar, Straus and Giroux.
- Silver, N. (2012). The Signal and the Noise. Penguin.
- Tetlock, P. E., & Gardner, D. (2015). Superforecasting. Crown.
- Gigerenzer, G. (2002). Calculated Risks. Simon & Schuster.
