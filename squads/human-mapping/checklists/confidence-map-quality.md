---
type: checklist
level: macro
squad: human-mapping
version: "2.0.0"
gate: mandatory
---
# Checklist: Qualidade do Mapa de Confianca

## Proposito
Verificar que o score de confianca foi definido para cada camada avaliada, com metodologia transparente e calculo rastreavel, permitindo ao leitor saber exatamente o quanto confiar em cada resultado.

## Criterios de Aprovacao

### Obrigatorios (todos devem passar)
- [ ] Score de confianca foi calculado para cada camada avaliada — Evidencia: `score por camada registrado`
- [ ] Metodologia de calculo do score esta documentada — Evidencia: `descricao da formula ou criterio utilizado`
- [ ] Fatores que compoe o score de cada camada estao listados — Evidencia: `fatores com pesos registrados`
- [ ] Score global foi calculado a partir dos scores individuais — Evidencia: `score global com formula de composicao`
- [ ] Limiares de confianca estao definidos (minimo aceitavel, alerta, critico) — Evidencia: `tabela de limiares documentada`
- [ ] Camadas abaixo do limiar minimo estao sinalizadas — Evidencia: `flags de baixa confianca registrados`
- [ ] Impacto da calibracao no score foi incorporado — Evidencia: `ajuste de calibracao aplicado`
- [ ] Impacto das contradicoes no score foi incorporado — Evidencia: `ajuste de contradicoes aplicado`
- [ ] Mapa de confianca e apresentado de forma visual e intuitiva — Evidencia: `representacao visual incluida`

### Desejaveis (aumentam confianca)
- [ ] Score de confianca inclui intervalo (nao apenas ponto unico)
- [ ] Sensibilidade do score a variacoes foi analisada
- [ ] Comparacao com benchmarks de sessoes anteriores foi incluida
- [ ] Recomendacoes para aumentar confianca em camadas fracas foram feitas
- [ ] Respondente foi informado sobre os niveis de confianca

## Evidencia Necessaria
- Score de confianca individual por camada avaliada
- Descricao da metodologia de calculo utilizada
- Lista de fatores com pesos por camada
- Score global com formula de composicao
- Tabela de limiares (minimo, alerta, critico)
- Flags de camadas abaixo do limiar
- Ajustes aplicados de calibracao e contradicoes
- Representacao visual do mapa de confianca

## Acao se Falhar
- Se alguma camada nao tem score: calcular score com a metodologia padrao
- Se metodologia nao esta documentada: descrever formula ou criterio utilizado
- Se score global nao foi calculado: compor a partir dos scores individuais
- Se limiares nao estao definidos: aplicar limiares padrao do sistema
- Se camadas fracas nao estao sinalizadas: adicionar flags de alerta
- Se ajustes de calibracao/contradicoes nao foram aplicados: recalcular com ajustes
- Mapa de confianca e obrigatorio e deve ser incluido em todo relatorio final

## Agente Responsavel
- **Agente principal**: Agente de Confianca
- **Agentes de suporte**: Agente de Calibracao, Agente de Auditoria de Contradicoes
- **Aprovador final**: Agente de Qualidade
