---
type: task
squad: human-mapping
version: "2.0.0"
agent: session-manager
workflow: intake-workflow
---

# Task: Iniciar Sessão com /start

## Objetivo

Iniciar uma nova sessão de mapeamento humano, criando o registro de sessão e preparando o ambiente para a análise do respondente.

## Pré-condições

- Comando `/start` recebido do usuário
- Nenhuma sessão ativa para o mesmo respondente
- Agente session-manager disponível

## Passos

1. Receber o comando `/start` e extrair metadados iniciais (timestamp, canal, usuário solicitante)
2. Gerar um `session-id` único no formato `HMS-YYYYMMDD-XXXX`
3. Criar registro de sessão em `data/sessions/` com status `initiated`
4. Verificar se existe sessão anterior para o mesmo respondente
5. Caso exista sessão anterior, oferecer opção de retomar ou iniciar nova
6. Carregar configurações padrão de `config.yaml`
7. Inicializar o timer de sessão via `scripts/session/session-timer.md`
8. Enviar mensagem de boas-vindas ao respondente
9. Registrar evento de início no log de auditoria

## Outputs

- `session-record`: Registro completo da sessão com ID, timestamp e status
- `session-config`: Configurações carregadas para a sessão
- `welcome-message`: Mensagem de boas-vindas personalizada

## Checklist de Conclusão

- [ ] Session ID gerado e registrado
- [ ] Registro de sessão criado em `data/sessions/`
- [ ] Configurações carregadas do `config.yaml`
- [ ] Timer de sessão inicializado
- [ ] Mensagem de boas-vindas enviada
- [ ] Log de auditoria atualizado
- [ ] Nenhuma sessão duplicada ativa

## Próxima Task

`tasks/intake/define-goal.md` — Definir objetivo da análise
