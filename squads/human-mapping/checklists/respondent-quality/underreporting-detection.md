---
type: checklist
level: layer
layer: respondent-quality
squad: human-mapping
version: "2.0.0"
---
# Checklist: Detecção de Underreporting

## Propósito
Detectar quando o respondente subreporta fraquezas, dificuldades ou aspectos negativos, distorcendo o perfil mapeado.

## Critérios
- [ ] Frequência de respostas que minimizam dificuldades foi calculada — Evidência: `campo freq_minimizacao preenchido`
- [ ] Ausência de relato de qualquer fraqueza foi sinalizada — Evidência: `flag zero_fraquezas verificado`
- [ ] Respostas a itens sobre desafios foram analisadas — Evidência: `análise de itens de desafio realizada`
- [ ] Padrão de evitação de temas sensíveis foi detectado — Evidência: `análise de padrão de evitação`
- [ ] Linguagem de minimização foi identificada (ex: "não é bem assim", "raramente") — Evidência: `análise linguística de minimização`
- [ ] Comparação entre respostas diretas e indiretas sobre fraquezas — Evidência: `análise direta vs. indireta realizada`
- [ ] Nível de vulnerabilidade demonstrado pelo respondente foi avaliado — Evidência: `campo nivel_vulnerabilidade classificado`
- [ ] Contexto de segurança psicológica da sessão foi considerado — Evidência: `campo seguranca_psicologica avaliado`
- [ ] Score de risco de underreporting foi calculado — Evidência: `campo score_underreporting preenchido`
- [ ] Impacto do underreporting nos resultados foi estimado — Evidência: `campo impacto_underreporting definido`
- [ ] Perguntas adicionais de normalização foram aplicadas — Evidência: `perguntas de normalização enviadas`
- [ ] Relatório final inclui nota sobre nível de underreporting detectado — Evidência: `nota de underreporting no relatório`

## Ação se Falhar
Reformular perguntas usando técnica de normalização ("muitas pessoas sentem...") para reduzir a barreira de relato. Inserir cenários hipotéticos que permitem revelar fraquezas indiretamente. Ajustar confiança dos construtos que dependem de relato de dificuldades. Incluir nota no relatório final.

## Agente Responsável
respondent-quality-agent
