---
type: task
squad: human-mapping
version: "2.0.0"
agent: operations-agent
workflow: operations-workflow
---

# Task: Atualizar Registries

## Objetivo

Atualizar os registros centrais do squad (registries) com dados de sessões concluídas, mantendo a base de conhecimento atualizada e acessível para consultas futuras e análises de tendências.

## Pré-condições

- Sessão de assessment concluída e relatórios entregues
- Feedback de acurácia coletado (quando disponível)
- Session record completo e fechado

## Passos

1. Atualizar o registry de sessões em `data/registries/sessions/`:
   - Adicionar entrada com session-id, data, contexto, profundidade, status
   - Incluir score de qualidade e acurácia (quando disponível)
   - Marcar sessão como concluída
2. Atualizar o registry de perfis em `data/registries/profiles/`:
   - Registrar perfil anônimo para análise de tendências
   - Incluir scores agregados sem dados pessoais identificáveis
   - Vincular ao session-id para rastreabilidade
3. Atualizar o registry de frameworks em `data/registries/frameworks/`:
   - Registrar performance de cada framework na sessão
   - Atualizar estatísticas de acurácia por framework
   - Registrar contradições encontradas e como foram resolvidas
4. Atualizar o registry de padrões em `data/registries/patterns/`:
   - Adicionar novos padrões descobertos durante a sessão
   - Atualizar frequência de padrões existentes
   - Sinalizar padrões emergentes que merecem investigação
5. Verificar integridade de todos os registries atualizados
6. Executar backup incremental dos registries
7. Atualizar índices de busca para consultas rápidas
8. Gerar resumo das atualizações realizadas

## Outputs

- `registry-update-log`: Log de todas as atualizações realizadas
- `updated-stats`: Estatísticas atualizadas dos registries
- `new-patterns`: Novos padrões registrados
- `backup-confirmation`: Confirmação do backup realizado

## Checklist de Conclusão

- [ ] Registry de sessões atualizado
- [ ] Registry de perfis atualizado (dados anonimizados)
- [ ] Registry de frameworks atualizado
- [ ] Registry de padrões atualizado
- [ ] Integridade verificada
- [ ] Backup realizado
- [ ] Índices de busca atualizados
- [ ] Resumo de atualizações gerado

## Próxima Task

`tasks/operations/cross-squad-handoff.md` — Handoff para outros squads (se necessário)
