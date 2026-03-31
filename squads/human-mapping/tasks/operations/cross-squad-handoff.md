---
type: task
squad: human-mapping
version: "2.0.0"
agent: operations-agent
workflow: operations-workflow
---

# Task: Handoff para Outros Squads

## Objetivo

Realizar o handoff estruturado de dados e insights do mapeamento humano para outros squads que possam utilizar os resultados, garantindo que a informação seja transferida de forma segura, útil e com o contexto adequado.

## Pré-condições

- Sessão concluída com relatórios finalizados
- Identificação de squads que podem se beneficiar dos dados
- Autorização do respondente/solicitante para compartilhamento (quando aplicável)

## Passos

1. Identificar quais squads podem receber handoff:
   - Squad de Coaching: para planos de desenvolvimento
   - Squad de Recrutamento: para relatórios de contratação
   - Squad de Equipe: para análise de composição de time
   - Squad de Liderança: para desenvolvimento de líderes
2. Para cada squad receptor, preparar pacote de handoff:
   - Selecionar dados relevantes para o contexto do squad receptor
   - Remover dados irrelevantes ou sensíveis demais
   - Adaptar formato ao padrão esperado pelo squad receptor
   - Incluir resumo executivo orientado ao uso do squad
3. Verificar conformidade com políticas de privacidade:
   - Dados pessoais: requer consentimento explícito
   - Dados anonimizados: pode compartilhar livremente
   - Dados de contratação: seguir política específica
4. Criar ticket de handoff com:
   - Squad de origem e destino
   - Resumo do conteúdo transferido
   - Contexto e recomendações de uso
   - Limitações e caveats
   - Nível de confiança dos dados
5. Enviar handoff pelo canal oficial de comunicação entre squads
6. Registrar handoff no log de operações
7. Acompanhar confirmação de recebimento pelo squad receptor
8. Disponibilizar-se para esclarecimentos durante 48h

## Outputs

- `handoff-package`: Pacote de dados preparado para cada squad
- `handoff-ticket`: Ticket formal de transferência
- `privacy-clearance`: Confirmação de conformidade com privacidade
- `handoff-log`: Registro completo do handoff

## Checklist de Conclusão

- [ ] Squads receptores identificados
- [ ] Pacotes de handoff preparados
- [ ] Conformidade com privacidade verificada
- [ ] Tickets de handoff criados
- [ ] Handoffs enviados pelos canais oficiais
- [ ] Registros atualizados no log de operações
- [ ] Confirmações de recebimento obtidas

## Próxima Task

Nenhuma — esta é uma task terminal do fluxo de operações.
