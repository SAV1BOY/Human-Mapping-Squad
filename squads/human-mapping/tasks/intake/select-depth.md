---
type: task
squad: human-mapping
version: "2.0.0"
agent: session-manager
workflow: intake-workflow
---

# Task: Selecionar Profundidade da Análise

## Objetivo

Permitir que o usuário selecione a profundidade da análise entre os modos `/fast`, `/start` e `/deep`, ajustando o processo de assessment conforme o nível escolhido.

## Pré-condições

- Objetivo da análise definido (`define-goal.md` concluída)
- Camadas obrigatórias e opcionais já determinadas
- Session record ativo e atualizado

## Passos

1. Apresentar as três opções de profundidade ao usuário:
   - `/fast` — Análise rápida (15-20 min), cobre camadas essenciais, gera snapshot executivo
   - `/start` — Análise padrão (30-45 min), cobre todas as camadas obrigatórias, gera relatório completo
   - `/deep` — Análise profunda (60-90 min), cobre todas as camadas + exploração detalhada, gera relatório profundo + plano de desenvolvimento
2. Capturar a seleção do usuário
3. Validar que a profundidade é compatível com o objetivo definido
4. Caso `/fast` seja incompatível com o objetivo (ex: contratação requer mais profundidade), alertar e sugerir alternativa
5. Configurar o número de perguntas por camada conforme a profundidade:
   - `/fast`: 3-5 perguntas por camada
   - `/start`: 6-10 perguntas por camada
   - `/deep`: 10-15 perguntas por camada + perguntas de aprofundamento
6. Definir tempo-alvo por camada no session-timer
7. Atualizar session record com `depth-mode` selecionado
8. Confirmar seleção com o usuário antes de prosseguir

## Outputs

- `depth-mode`: Modo selecionado (`fast`, `start` ou `deep`)
- `questions-per-layer`: Configuração de perguntas por camada
- `time-targets`: Tempos-alvo por camada
- `output-types`: Tipos de relatório que serão gerados

## Checklist de Conclusão

- [ ] Modo de profundidade selecionado
- [ ] Compatibilidade com objetivo verificada
- [ ] Perguntas por camada configuradas
- [ ] Timer ajustado com tempos-alvo
- [ ] Session record atualizado
- [ ] Confirmação do usuário obtida

## Próxima Task

`tasks/intake/map-context.md` — Mapear contexto do respondente
