---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Resume Session Builder

## Propósito

Retomar uma sessão de mapeamento humano previamente iniciada, restaurando o estado completo da session-memory para continuar o processo de assessment de onde parou.

## Input

- `session-id`: ID da sessão a ser retomada (formato HMS-YYYYMMDD-XXXX)
- `user-id`: ID do usuário solicitando a retomada
- `timestamp`: Timestamp da retomada

## Processo (step by step algorithm)

1. **Validar Session ID**
   - Verificar se o session-id existe em `data/sessions/`
   - Verificar se o status não é `completed` ou `cancelled`
   - Verificar se o user-id tem permissão para acessar a sessão

2. **Carregar Session Record**
   - Ler `data/sessions/{session-id}.yaml`
   - Validar integridade do arquivo (campos obrigatórios presentes)
   - Carregar arquivo de audit-log para histórico

3. **Determinar ponto de retomada**
   - Identificar a última task concluída com sucesso
   - Identificar a próxima task pendente no workflow
   - Verificar se há dados parciais de uma task interrompida
   - Se task foi interrompida, determinar se é possível retomar ou precisa reiniciar

4. **Restaurar estado dos componentes**
   - Restaurar calibração (se já concluída)
   - Restaurar scores de camadas já processadas
   - Restaurar dados de auditoria parcial
   - Recarregar configurações da sessão original

5. **Verificar validade temporal**
   - Se a sessão foi pausada há mais de 7 dias, alertar sobre possível mudança no respondente
   - Se pausada há mais de 30 dias, recomendar recalibração
   - Registrar gap temporal no audit-log

6. **Reinicializar componentes auxiliares**
   - Reacionar `scripts/session/session-timer.md` com tempo restante
   - Reativar `scripts/session/response-quality-checker.md`
   - Atualizar status da sessão para `resumed`

7. **Gerar resumo de retomada**
   - Listar o que já foi concluído
   - Indicar próximo passo
   - Estimar tempo restante

## Output

- `session-record`: Session record restaurado com estado atual
- `resume-point`: Task/step exato de retomada
- `completed-summary`: Resumo do que já foi concluído
- `estimated-remaining`: Tempo estimado para conclusão
- `warnings`: Alertas sobre validade temporal ou dados parciais

## Uso

Chamado quando o usuário solicita retomar uma sessão existente via comando `/resume {session-id}` ou quando o sistema detecta uma sessão anterior ativa para o mesmo respondente durante o `/start`.

## Especificação de I/O

### Input
- Formato: YAML (via parâmetros internos)
- Campos obrigatórios: `session-id`, `user-id`, `timestamp`
- Exemplo: `{session-id: "HMS-20260401-0001", user-id: "U-001", timestamp: "2026-04-01T14:00:00Z"}`

### Output
- Formato: YAML
- Campos: `session-record`, `resume-point`, `completed-summary`, `estimated-remaining`, `warnings`

### Thresholds
- max_pause_days_normal: 7 (alerta sobre mudança no respondente)
- max_pause_days_recalibrate: 30 (recomenda recalibração)
- session_status_blocked: `["completed", "cancelled"]`

### Tratamento de Erros
- Input inválido: retornar erro `INVALID_SESSION_ID` com formato esperado
- Dados insuficientes: se session record corrompido, retornar `SESSION_CORRUPT` e sugerir nova sessão
- Sessão não encontrada: retornar `SESSION_NOT_FOUND`
