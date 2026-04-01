---
type: script
squad: human-mapping
version: "2.0.0"
---

# Script: Session Timer

## Propósito

Monitorar o tempo gasto em cada camada do assessment e na sessão como um todo, alertando quando os limites de tempo são atingidos e gerando métricas de timing para análise de eficiência.

## Input

- `session-id`: ID da sessão ativa
- `depth-mode`: Modo de profundidade (`fast`, `start`, `deep`)
- `time-targets`: Tempos-alvo por camada (em minutos)
- `max-session-time`: Tempo máximo total da sessão (em minutos)

## Processo (step by step algorithm)

1. **Inicializar timer global**
   - Registrar `session-start-time` com timestamp atual
   - Calcular `session-end-target` = start + max-session-time
   - Configurar tempos-alvo por camada conforme depth-mode:
     - `/fast`: Calibração 5min, Camadas 3min cada, Total ~25min
     - `/start`: Calibração 8min, Camadas 5min cada, Total ~50min
     - `/deep`: Calibração 10min, Camadas 8min cada, Total ~90min

2. **Iniciar timer de camada** (chamado ao iniciar cada camada)
   - Registrar `layer-start-time` para a camada atual
   - Calcular `layer-end-target` = start + target da camada
   - Iniciar monitoramento contínuo

3. **Monitorar tempo** (loop de verificação)
   - A cada resposta do respondente, verificar:
     - Tempo na camada atual vs target
     - Tempo total da sessão vs max
   - Gerar alertas nos marcos:
     - 75% do tempo da camada: alerta amarelo
     - 100% do tempo da camada: alerta laranja (sugerir conclusão)
     - 120% do tempo da camada: alerta vermelho (forçar próxima camada)
     - 80% do tempo total: alerta de sessão se aproximando do fim

4. **Finalizar timer de camada** (chamado ao concluir cada camada)
   - Registrar `layer-end-time` e calcular `layer-duration`
   - Calcular desvio do target (adiantado ou atrasado)
   - Atualizar tempo restante estimado para a sessão

5. **Gerar métricas de timing**
   - Tempo médio por pergunta
   - Tempo por camada vs target
   - Tempo total da sessão
   - Velocidade do respondente (rápido, normal, lento)

6. **Registrar no session record**
   - Salvar todas as métricas de timing
   - Incluir timestamps de início e fim de cada camada

## Output

- `timing-metrics`: Métricas completas de tempo por camada e global
- `alerts`: Lista de alertas gerados durante a sessão
- `respondent-speed`: Classificação de velocidade do respondente
- `time-remaining`: Tempo restante estimado para conclusão

## Uso

Inicializado por `scripts/session/start-session-builder.md` ou `scripts/session/resume-session-builder.md`. Consultado por cada task de assessment para verificar tempo disponível.

## Especificação de I/O

### Input
- Formato: YAML
- Campos obrigatórios: `session-id`, `depth-mode`, `time-targets`, `max-session-time`
- Exemplo: `{session-id: "HMS-20260401-0001", depth-mode: "start", time-targets: {calibration: 8, trait: 5, type: 5}, max-session-time: 50}`

### Output
- Formato: YAML
- Campos: `timing-metrics`, `alerts`, `respondent-speed`, `time-remaining`

### Thresholds
- alert_yellow: 75% do tempo da camada
- alert_orange: 100% do tempo da camada
- alert_red: 120% do tempo da camada (forçar próxima)
- session_warning: 80% do tempo total

### Tratamento de Erros
- Input inválido: usar tempos padrão do depth-mode e logar warning
- Dados insuficientes: se `time-targets` ausente, derivar de `depth-mode`
