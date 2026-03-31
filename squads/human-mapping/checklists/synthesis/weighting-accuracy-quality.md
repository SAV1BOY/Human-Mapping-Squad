---
type: checklist
level: layer
layer: synthesis
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Precisao dos Pesos por Camada

## Proposito
Garantir que os pesos por camada foram aplicados corretamente, com tracos como base mais pesada, tipos como derivacao e motivacao como motor.

## Criterios Obrigatorios
- [ ] Pesos por camada foram explicitamente definidos e documentados — Evidencia: `___`
- [ ] Camada de tracos recebeu o maior peso como base fundamental — Evidencia: `___`
- [ ] Camada de tipos foi tratada como derivacao dos tracos, nao como base independente — Evidencia: `___`
- [ ] Camada de motivacao foi posicionada como motor energetico do perfil — Evidencia: `___`
- [ ] Camada de conacao foi ponderada como dimensao instintiva complementar — Evidencia: `___`
- [ ] Camada de equipe foi integrada como manifestacao contextual — Evidencia: `___`
- [ ] Nenhuma camada recebeu peso desproporcional sem justificativa — Evidencia: `___`
- [ ] Hierarquia de pesos e coerente com a teoria subjacente — Evidencia: `___`
- [ ] Ajustes de peso baseados na qualidade dos dados foram documentados — Evidencia: `___`

## Criterios Desejaveis
- [ ] Justificativa teorica para cada peso foi referenciada
- [ ] Sensibilidade do resultado a mudancas nos pesos foi testada
- [ ] Pesos foram calibrados com base na confiança dos dados de cada camada
- [ ] Documentacao permite auditoria completa da ponderacao aplicada

## Acao se Falhar
Retornar ao synthesis-architect para revisao da ponderacao. Verificar se a hierarquia tracos > tipos > motivacao esta respeitada. Corrigir distorcoes e re-processar a sintese com pesos adequados.

## Agente Responsavel
synthesis-architect
