---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Start Session Builder

## Propósito

Inicializar uma nova sessão de mapeamento humano, criando a estrutura de dados necessária a partir das informações coletadas durante o intake, configurando o ambiente e retornando o session record pronto para uso.

## Input

- `user-id`: Identificador do usuário solicitante
- `respondent-id`: Identificador do respondente (pode ser o mesmo que user-id)
- `channel`: Canal de origem (chat, web, API)
- `timestamp`: Timestamp do início da sessão
- `config`: Configurações do squad carregadas de `config.yaml`

## Processo (step by step algorithm)

1. **Gerar Session ID**
   - Formato: `HMS-YYYYMMDD-XXXX` onde XXXX é sequencial do dia
   - Verificar unicidade contra registry de sessões existentes
   - Se duplicado, incrementar XXXX

2. **Criar estrutura do Session Record**
   ```
   session-record:
     id: HMS-YYYYMMDD-XXXX
     status: initiated
     created-at: timestamp
     user-id: user-id
     respondent-id: respondent-id
     channel: channel
     goal: null (preenchido no intake)
     depth: null (preenchido no intake)
     context: null (preenchido no intake)
     calibration: {}
     layers: {}
     audit: {}
     synthesis: {}
     review: {}
     quality-score: null
     confidence-baseline: null
   ```

3. **Persistir Session Record**
   - Salvar em `data/sessions/{session-id}.yaml`
   - Criar diretório de trabalho `data/sessions/{session-id}/`
   - Inicializar arquivo de log `data/sessions/{session-id}/audit-log.yaml`

4. **Carregar configurações de sessão**
   - Ler `config.yaml` para obter parâmetros padrão
   - Aplicar overrides específicos do canal se existirem
   - Definir timeouts e limites de perguntas

5. **Inicializar componentes auxiliares**
   - Acionar `scripts/session/session-timer.md` com config de tempos
   - Preparar `scripts/session/response-quality-checker.md` em modo standby

6. **Retornar session record e configurações**

## Output

- `session-record`: Objeto completo do registro de sessão
- `session-config`: Configurações aplicáveis à sessão
- `session-path`: Caminho do diretório de trabalho da sessão
- `audit-log-path`: Caminho do arquivo de log de auditoria

## Uso

Chamado por `tasks/intake/start-session.md` no início de cada nova sessão. Deve ser a primeira operação executada ao receber o comando `/start`.
