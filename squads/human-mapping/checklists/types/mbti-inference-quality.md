---
type: checklist
level: layer
layer: types
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade da Inferência MBTI

## Propósito
Garantir que o tipo MBTI foi inferido com evidência consistente em todas as 4 dimensões.

## Critérios
- [ ] Dimensão E/I (Extroversão/Introversão) foi inferida com evidência — Evidência: `score e evidência E/I registrados`
- [ ] Dimensão S/N (Sensação/Intuição) foi inferida com evidência — Evidência: `score e evidência S/N registrados`
- [ ] Dimensão T/F (Pensamento/Sentimento) foi inferida com evidência — Evidência: `score e evidência T/F registrados`
- [ ] Dimensão J/P (Julgamento/Percepção) foi inferida com evidência — Evidência: `score e evidência J/P registrados`
- [ ] Clareza da preferência foi avaliada em cada dimensão — Evidência: `campo clareza_preferencia por dimensão`
- [ ] Dimensões com preferência fraca foram sinalizadas — Evidência: `flag preferencia_fraca aplicado`
- [ ] Funções cognitivas dominante e auxiliar foram identificadas — Evidência: `campo funcoes_cognitivas preenchido`
- [ ] Tipo de 4 letras resultante foi registrado — Evidência: `campo tipo_mbti definido`
- [ ] Tipo inferido é coerente com dados comportamentais da sessão — Evidência: `validação comportamental realizada`
- [ ] Tipo inferido é coerente com traços Big Five medidos — Evidência: `análise de convergência MBTI-Big Five`
- [ ] Respondente foi informado de que MBTI é indicativo, não definitivo — Evidência: `disclaimer comunicado`
- [ ] Confiança da inferência geral foi calculada — Evidência: `campo confianca_mbti preenchido`

## Ação se Falhar
Se alguma dimensão não puder ser inferida com confiança, reportar como "preferência não clara" naquela dimensão. Oferecer os dois tipos possíveis (ex: INTJ ou INFJ) com explicação da ambiguidade. Nunca forçar uma preferência sem evidência suficiente.

## Agente Responsável
types-agent
