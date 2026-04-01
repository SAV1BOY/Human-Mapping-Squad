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

## Subtask Breakdown
1. **Receber comando** — Agente: `session-manager`. Input: `/start` + metadados. Output: `session-id`. Gate: ID único gerado e validado.
2. **Criar session record** — Agente: `session-manager`. Input: `session-id` + config. Output: `session-record.yaml`. Gate: arquivo persistido em `data/sessions/`.
3. **Carregar configurações** — Agente: `session-manager`. Input: `config.yaml`. Output: `session-config`. Gate: todos os parâmetros obrigatórios presentes.
4. **Inicializar timer e logger** — Agente: `session-manager`. Input: `session-config`. Output: timer ativo + audit-log. Gate: timer respondendo, log gravável.
5. **Enviar boas-vindas** — Agente: `session-manager`. Input: `session-config`. Output: `welcome-message`. Gate: mensagem entregue ao respondente.

## Quality Gate
- [ ] Session ID registrado e sem duplicatas
- [ ] Arquivo `data/sessions/{id}.yaml` existe e é válido
- Threshold: tempo de setup < 5 segundos
- Se FAIL: abortar sessão, logar erro e notificar operador

## Rework Trigger
- Sessão duplicada detectada → retornar ao passo 1 (gerar novo ID)
- Config inválida → retornar ao passo 3 após corrigir `config.yaml`
