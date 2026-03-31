---
type: task
squad: human-mapping
version: "2.0.0"
agent: audit-agent
workflow: audit-workflow
---

# Task: Rodar Verificação Geral de Qualidade

## Objetivo

Executar uma verificação abrangente de qualidade sobre todos os dados coletados e processados, garantindo integridade, completude e consistência antes de prosseguir para a síntese do perfil.

## Pré-condições

- Auditoria de contradições e reconciliação concluídas
- Scores de confiança verificados
- Todos os dados de assessment disponíveis

## Passos

1. Verificar completude dos dados:
   - Todas as camadas obrigatórias foram executadas?
   - Todas as perguntas planejadas foram respondidas?
   - Há camadas com dados insuficientes?
2. Verificar integridade dos dados:
   - Nenhum score está fora do range válido
   - Timestamps são consistentes e sequenciais
   - Session record está completo e sem campos nulos obrigatórios
3. Executar `scripts/analysis/pattern-matcher.md` para identificar padrões conhecidos:
   - Padrões de resposta suspeitos (todas respostas iguais, padrão alternado)
   - Perfis estatisticamente improváveis
   - Combinações raras que merecem investigação
4. Verificar se o fator de correção de desejabilidade social foi aplicado corretamente
5. Validar que a reconciliação de contradições não gerou novas inconsistências
6. Calcular score geral de qualidade da sessão (QS) de 0-100:
   - Completude: 30% do QS
   - Confiança: 30% do QS
   - Consistência: 25% do QS
   - Integridade: 15% do QS
7. Se QS < 60, sinalizar como sessão de qualidade insuficiente
8. Gerar certificado de qualidade da sessão

## Outputs

- `quality-score`: Score geral de qualidade (0-100)
- `quality-breakdown`: Decomposição do score por critério
- `quality-issues`: Lista de problemas de qualidade encontrados
- `quality-certificate`: Certificado de qualidade da sessão
- `synthesis-readiness`: Flag indicando se está pronto para síntese

## Checklist de Conclusão

- [ ] Completude dos dados verificada
- [ ] Integridade dos dados validada
- [ ] Pattern matcher executado
- [ ] Correção de desejabilidade social validada
- [ ] Reconciliação verificada por novas inconsistências
- [ ] Score de qualidade calculado
- [ ] Certificado de qualidade gerado
- [ ] Flag de prontidão para síntese definido

## Próxima Task

`tasks/synthesis/synthesize-profile.md` — Sintetizar perfil integrado
