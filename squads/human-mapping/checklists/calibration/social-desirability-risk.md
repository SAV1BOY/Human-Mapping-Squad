---
type: checklist
level: layer
layer: calibration
squad: human-mapping
version: "2.0.0"
---
# Checklist: Risco de Respostas Socialmente Desejáveis

## Propósito
Avaliar e mitigar o risco de que o respondente esteja fornecendo respostas socialmente desejáveis em vez de respostas autênticas.

## Critérios
- [ ] Escala de desejabilidade social implícita foi aplicada — Evidência: `itens de controle inseridos e analisados`
- [ ] Frequência de respostas extremamente positivas foi calculada — Evidência: `campo freq_respostas_positivas_extremas preenchido`
- [ ] Ausência de qualquer fraqueza autorrelatada foi sinalizada — Evidência: `flag ausencia_fraquezas verificado`
- [ ] Respostas foram comparadas com benchmarks populacionais — Evidência: `análise de desvio do benchmark realizada`
- [ ] Contexto de avaliação (seleção, desenvolvimento, pessoal) foi considerado — Evidência: `campo contexto_avaliacao definido`
- [ ] Nível de anonimato percebido pelo respondente foi avaliado — Evidência: `campo anonimato_percebido registrado`
- [ ] Perguntas de validação cruzada foram incluídas — Evidência: `itens de validação cruzada presentes`
- [ ] Respondente foi orientado sobre importância da autenticidade — Evidência: `mensagem de autenticidade enviada no início`
- [ ] Score de risco de desejabilidade social foi calculado — Evidência: `campo score_desejabilidade preenchido`
- [ ] Impacto da desejabilidade social nos resultados foi estimado — Evidência: `campo impacto_estimado definido`
- [ ] Estratégias de mitigação foram aplicadas quando risco > moderado — Evidência: `log de mitigação atualizado`
- [ ] Resultado final inclui nota sobre nível de desejabilidade detectada — Evidência: `nota no relatório registrada`

## Ação se Falhar
Aplicar técnicas adicionais de mitigação: reformular perguntas em formato de escolha forçada, utilizar cenários situacionais em vez de autoavaliação direta, ou inserir perguntas âncora. Registrar o risco no relatório final para que o leitor interprete os resultados com cautela.

## Agente Responsável
calibration-agent
