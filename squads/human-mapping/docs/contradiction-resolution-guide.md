# Guia de Resolução de Contradições

## Visão Geral
Este guia apresenta o processo e as técnicas para identificar, classificar e
resolver contradições entre resultados de diferentes frameworks de avaliação
aplicados a uma mesma pessoa.

## Conteúdo

### Tipos de contradição
1. **Contextual**: a pessoa se comporta diferente em contextos diferentes
   - Exemplo: extrovertido no DISC, introvertido no Big Five
   - Resolução: documentar ambos os aspectos como válidos em seus contextos
2. **Desenvolvimental**: a pessoa mudou ao longo do tempo
   - Exemplo: resultados diferentes entre avaliações com anos de intervalo
   - Resolução: considerar o resultado mais recente como primário
3. **Metodológica**: limitação do instrumento ou método
   - Exemplo: proxy-inference diverge do resultado direto
   - Resolução: priorizar resultado do instrumento validado
4. **Genuína**: a pessoa é genuinamente complexa naquela dimensão
   - Exemplo: alto em abertura mas baixo em busca de novidades
   - Resolução: aceitar e documentar a complexidade

### Processo de resolução
1. Identificar a contradição e os dados envolvidos
2. Classificar por tipo (contextual, desenvolvimental, metodológica, genuína)
3. Investigar causas prováveis
4. Aplicar técnica de resolução adequada ao tipo
5. Recalcular nível de confiança
6. Registrar no contradiction-registry.yaml

### Técnica do "E" em vez de "OU"
Antes de forçar uma resolução, considere que ambos os resultados podem ser
verdadeiros simultaneamente. A pessoa pode SER X em um contexto E Y em outro.

---

## 3 Exemplos Reais de Contradição com Resolução

### Exemplo 1 — Contradição Contextual
**Dados**: Big Five mostra Extroversão baixa (percentil 25). DISC mostra perfil "I"
dominante (alta influência social).
**Análise**: o respondente é introvertido em termos de energia (Big Five mede
preferência por estímulo) mas extrovertido no estilo de comunicação no trabalho
(DISC mede comportamento observável no contexto profissional).
**Resolução**: ambos são válidos. Documentar: "Prefere ambientes tranquilos para
recarregar energia (Big Five), mas adota estilo comunicativo e persuasivo em
contextos profissionais (DISC). Confiança: 0.75."
**Tipo**: Contextual. **Técnica**: "E" em vez de "OU".

### Exemplo 2 — Contradição Metodológica
**Dados**: CliftonStrengths tem "Analytical" no Top 5. Proxy-inference de
CliftonStrengths para Belbin sugere papel "Plant" (criativo), mas Belbin direto
mostra "Monitor Evaluator" (analítico).
**Análise**: o proxy CliftonStrengths → Belbin tem confiança baixa (0.3-0.4).
O mapeamento não captura que "Analytical" no Gallup se correlaciona melhor com
"Monitor Evaluator" no Belbin do que com "Plant".
**Resolução**: priorizar resultado direto do Belbin. Descartar proxy. Registrar
a limitação do mapeamento para calibração futura.
**Tipo**: Metodológica. **Técnica**: priorizar instrumento validado.

### Exemplo 3 — Contradição Genuína
**Dados**: Eneagrama tipo 7 (Entusiasta, busca novidades) com Big Five mostrando
Abertura a Experiências moderada-baixa (percentil 35).
**Análise**: tipo 7 no Eneagrama correlaciona-se com alta abertura, mas o
respondente mostra abertura seletiva — busca novas experiências práticas e sociais,
mas não tem interesse por ideias abstratas ou arte.
**Resolução**: aceitar a complexidade. Documentar: "Busca ativamente novas
experiências práticas e estímulos sociais (Eneagrama 7), mas mantém preferências
convencionais em domínios intelectuais e estéticos (Big Five Abertura subfacetas).
Confiança: 0.70."
**Tipo**: Genuína. **Técnica**: análise por subfacetas.

> **Dica operacional**: ao encontrar uma contradição, sempre registre no
> `contradiction-registry.yaml` com ID no formato `CON-YYYY-NNN`, mesmo que a
> resolução seja imediata. Isso alimenta a base de conhecimento do squad.

## Referências
- `data/registries/contradiction-registry.yaml` — Registro de contradições
- `authority/workshop-kits/contradiction-resolution-workshop.md` — Workshop
- `docs/cross-framework-reconciliation.md` — Reconciliação entre frameworks
