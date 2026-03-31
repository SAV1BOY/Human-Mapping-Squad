---
type: checklist
level: layer
layer: intake
squad: human-mapping
version: "2.0.0"
---
# Checklist: Qualidade do Comando /start

## Propósito
Garantir que o comando /start foi executado com clareza e que os dados mínimos necessários para iniciar o mapeamento foram coletados.

## Critérios
- [ ] Comando /start foi invocado explicitamente pelo usuário — Evidência: `log de entrada com timestamp`
- [ ] Nome completo do respondente foi coletado — Evidência: `campo nome preenchido`
- [ ] Idioma preferido foi identificado ou confirmado — Evidência: `campo idioma definido`
- [ ] Canal de comunicação está funcional e bidirecional — Evidência: `resposta de confirmação recebida`
- [ ] Objetivo inicial declarado pelo usuário foi registrado — Evidência: `campo objetivo_inicial preenchido`
- [ ] Consentimento para coleta de dados foi obtido — Evidência: `flag consentimento = true`
- [ ] Dados duplicados ou sessões anteriores foram verificados — Evidência: `consulta ao histórico realizada`
- [ ] Formato de saída esperado foi perguntado — Evidência: `campo formato_saida definido`
- [ ] Tempo estimado da sessão foi comunicado ao respondente — Evidência: `mensagem de tempo enviada`
- [ ] Versão do protocolo de mapeamento foi registrada — Evidência: `campo versao_protocolo = 2.0.0`
- [ ] Nenhum campo obrigatório ficou em branco — Evidência: `validação de campos obrigatórios passou`
- [ ] Respondente confirmou estar pronto para iniciar — Evidência: `confirmação registrada no log`

## Ação se Falhar
Solicitar novamente os dados faltantes antes de prosseguir. Se o respondente não fornecer consentimento, encerrar a sessão com mensagem explicativa. Registrar falha no log de qualidade para auditoria.

## Agente Responsável
intake-agent
