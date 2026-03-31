---
type: task
squad: human-mapping
version: "2.0.0"
agent: session-manager
workflow: intake-workflow
---

# Task: Definir Objetivo da Análise

## Objetivo

Capturar e registrar o objetivo específico da análise de mapeamento humano, garantindo que o processo seja direcionado ao contexto correto do respondente ou solicitante.

## Pré-condições

- Sessão iniciada com sucesso (`start-session.md` concluída)
- Session ID ativo e válido
- Respondente ou solicitante disponível para interação

## Passos

1. Apresentar ao usuário as categorias de objetivo disponíveis:
   - Autoconhecimento pessoal
   - Desenvolvimento profissional
   - Avaliação para contratação
   - Composição de equipe
   - Coaching/mentoria
   - Transição de carreira
2. Capturar a seleção do usuário e validar contra a lista de objetivos suportados
3. Solicitar detalhamento do objetivo (texto livre, máximo 500 caracteres)
4. Registrar o objetivo no `session-record` com campo `goal-type` e `goal-detail`
5. Ajustar parâmetros de avaliação conforme o objetivo selecionado
6. Determinar quais camadas de assessment são obrigatórias vs opcionais para o objetivo
7. Informar ao usuário o escopo da análise que será realizada
8. Registrar decisão no log de auditoria

## Outputs

- `goal-definition`: Objeto com tipo e detalhamento do objetivo
- `required-layers`: Lista de camadas obrigatórias para o objetivo
- `optional-layers`: Lista de camadas opcionais sugeridas
- `scope-summary`: Resumo do escopo apresentado ao usuário

## Checklist de Conclusão

- [ ] Objetivo selecionado e validado
- [ ] Detalhamento capturado
- [ ] Camadas obrigatórias e opcionais definidas
- [ ] Session record atualizado com objetivo
- [ ] Escopo comunicado ao usuário
- [ ] Log de auditoria atualizado

## Próxima Task

`tasks/intake/select-depth.md` — Selecionar profundidade da análise
