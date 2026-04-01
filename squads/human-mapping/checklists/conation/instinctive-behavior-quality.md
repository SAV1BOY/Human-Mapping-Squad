---
type: checklist
level: layer
layer: conation
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade do Mapeamento de Padroes Instintivos

## Proposito
Garantir que padroes instintivos de comportamento foram mapeados e diferenciados de tracos cognitivos e afetivos.

## Criterios Obrigatorios
- [ ] Padroes instintivos de comportamento foram identificados e descritos — Evidencia: `Behavioral pattern documentation com MO (Modus Operandi) descrito para cada Action Mode, incluindo tendencias automaticas`
- [ ] Diferenciacao clara entre conacao (instintivo) e cognicao (pensamento) foi feita — Evidencia: `Instinct vs learned behavior separation documentada com coluna 'tipo' (conativo/cognitivo) para cada comportamento identificado`
- [ ] Diferenciacao clara entre conacao (instintivo) e afeto (sentimento) foi feita — Evidencia: `Instinct vs learned behavior separation documentada com coluna 'tipo' (conativo/afetivo) diferenciando impulso de acao vs preferencia emocional`
- [ ] Cada padrao instintivo esta fundamentado em evidencia comportamental — Evidencia: `Cada entrada na behavioral pattern documentation possui exemplo situacional com comportamento observado automatico`
- [ ] Padroes instintivos refletem como a pessoa age naturalmente sob pressao — Evidencia: `Secao 'comportamento_sob_pressao' na behavioral pattern documentation com MO description em cenarios de estresse`
- [ ] Mapeamento nao confunde habilidades aprendidas com instintos naturais — Evidencia: `Instinct vs learned behavior separation aplicada: cada comportamento classificado como 'instintivo' ou 'aprendido' com criterio de diferenciacao`
- [ ] Resistencias naturais (o que a pessoa evita instintivamente) foram documentadas — Evidencia: `Secao 'resistencias_naturais' na behavioral pattern documentation com lista de acoes evitadas e zona Prevent dos Action Modes`
- [ ] Consistencia entre padroes instintivos e os Action Modes foi verificada — Evidencia: `Checagem de alinhamento entre MO (Modus Operandi) description e Kolbe A scores documentada com resultado de validacao cruzada`

## Criterios Desejaveis
- [ ] Exemplos de situacoes onde os instintos se manifestam foram incluidos
- [ ] Impacto dos padroes instintivos na tomada de decisao foi descrito
- [ ] Tensoes entre instintos e demandas do ambiente foram identificadas
- [ ] Relacao entre padroes instintivos e nivel de energia/esgotamento foi explorada
- [ ] Comparacao com perfil cognitivo e afetivo das outras camadas foi feita

## Decisao
- **PASS**: Todos os 8 criterios obrigatorios atendidos com behavioral pattern documentation completa, instinct vs learned behavior separation documentada e MO description consistente com Kolbe A scores.
- **CONDITIONAL**: 6-7 criterios obrigatorios atendidos. Separacao instintivo/aprendido parcial ou MO description incompleta, corrigiveis com dados existentes.
- **FAIL**: Menos de 6 criterios obrigatorios atendidos, ou behavioral pattern documentation ausente, ou nenhuma separacao entre conacao/cognicao/afeto realizada.

## Acao se Falhar
Retornar ao kolbe-analyst para revisao do mapeamento instintivo. Garantir que a separacao entre as tres dimensoes (cognitiva, afetiva, conativa) esta clara. Re-processar com foco na diferenciacao.

## Agente Responsavel
kolbe-analyst
