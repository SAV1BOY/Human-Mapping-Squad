---
type: checklist
level: layer
layer: team
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Avaliacao de Dinamica de Equipe

## Proposito
Garantir que a dinamica de equipe foi avaliada com analise de interacoes, conflitos potenciais e complementaridades entre membros.

## Criterios Obrigatorios
- [ ] Padroes de interacao entre membros da equipe foram identificados — Evidencia: `Pair interaction analysis com frequencia e qualidade de interacao entre cada par de membros no dynamics assessment report`
- [ ] Conflitos potenciais foram mapeados com base nos perfis individuais — Evidencia: `Conflict prediction documented no dynamics assessment report com pares de risco, gatilhos e probabilidade de ocorrencia`
- [ ] Complementaridades entre membros foram documentadas — Evidencia: `Secao 'complementaridades' no dynamics assessment report com pares complementares e valor gerado pela combinacao`
- [ ] Dinamica de poder e influencia na equipe foi analisada — Evidencia: `Mapa de influencia no dynamics assessment report com papeis de lideranca formal/informal e fontes de autoridade`
- [ ] Pontos de tensao recorrentes foram identificados — Evidencia: `Lista de tensoes recorrentes no dynamics assessment report com frequencia estimada e impacto na produtividade`
- [ ] Aliancas naturais entre perfis foram descritas — Evidencia: `Pair interaction analysis identificando pares com alta afinidade de perfil e historico de colaboracao positiva`
- [ ] Impacto da dinamica atual na produtividade da equipe foi avaliado — Evidencia: `Secao 'impacto_produtividade' no dynamics assessment report com indicadores de velocidade de entrega e qualidade afetados`
- [ ] Analise considera dados de multiplas camadas (tracos, papeis, motivacao) — Evidencia: `Dynamics assessment report referencia cruzada com dados de tracos, papeis Belbin e perfil motivacional de cada membro`
- [ ] Dinamica sob pressao versus em rotina foi diferenciada — Evidencia: `Secoes separadas 'dinamica_pressao' e 'dinamica_rotina' no dynamics assessment report com comportamentos distintos por cenario`

## Criterios Desejaveis
- [ ] Cenarios de conflito mais provaveis foram descritos com sugestoes de mitigacao
- [ ] Protocolos de comunicacao recomendados para a equipe foram sugeridos
- [ ] Impacto de adicao ou remocao de membros na dinamica foi simulado
- [ ] Evolucao esperada da dinamica ao longo do tempo foi considerada

## Decisao
- **PASS**: Todos os 9 criterios obrigatorios atendidos com dynamics assessment report completo e pair interaction analysis documentada para todos os pares.
- **CONDITIONAL**: 7-8 criterios obrigatorios atendidos. Pares faltantes na pair interaction analysis podem ser completados com dados existentes.
- **FAIL**: Menos de 7 criterios obrigatorios atendidos, ou dynamics assessment report ausente, ou conflict prediction nao documentada.

## Acao se Falhar
Retornar ao synthesis-architect para revisao da analise de dinamica. Solicitar dados complementares dos perfis individuais se necessario. Garantir que todas as camadas relevantes foram cruzadas antes de re-submeter.

## Agente Responsavel
synthesis-architect
