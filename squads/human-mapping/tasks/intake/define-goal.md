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

## Subtask Breakdown
1. **Apresentar categorias** — Agente: `session-manager`. Input: lista de objetivos suportados. Output: opções exibidas ao usuário. Gate: todas as 6 categorias apresentadas.
2. **Capturar seleção** — Agente: `session-manager`. Input: resposta do usuário. Output: `goal-type` validado. Gate: objetivo pertence à lista suportada.
3. **Capturar detalhamento** — Agente: `session-manager`. Input: texto livre. Output: `goal-detail` (max 500 chars). Gate: texto não vazio e dentro do limite.
4. **Definir camadas** — Agente: `session-manager`. Input: `goal-type`. Output: `required-layers` + `optional-layers`. Gate: ao menos 1 camada obrigatória definida.
5. **Comunicar escopo** — Agente: `session-manager`. Input: camadas definidas. Output: `scope-summary` entregue. Gate: confirmação do usuário recebida.

## Quality Gate
- [ ] Objetivo registrado no session record com `goal-type` e `goal-detail`
- [ ] Camadas obrigatórias >= 1
- Threshold: detalhamento com >= 10 caracteres
- Se FAIL: re-solicitar detalhamento ao usuário

## Rework Trigger
- Objetivo selecionado inválido → retornar ao passo 1
- Usuário muda de objetivo após ver escopo → retornar ao passo 2
