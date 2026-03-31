---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Fit de Carreira (RIASEC / Strong)

## Objetivo

Avaliar o fit de carreira do respondente utilizando os frameworks RIASEC (Holland) e Strong Interest Inventory, identificando áreas de interesse profissional e ambientes de trabalho compatíveis.

## Pré-condições

- Camadas anteriores concluídas
- Perfil de personalidade, motivação e forças disponíveis
- Contexto profissional mapeado no intake

## Passos

1. Carregar banco de perguntas de interesses profissionais de `lib/questions/career/`
2. Aplicar perguntas para identificar preferências nos 6 tipos RIASEC:
   - **Realista (R)**: Atividades práticas, mecânicas, ao ar livre
   - **Investigativo (I)**: Pesquisa, análise, resolução de problemas complexos
   - **Artístico (A)**: Criatividade, expressão, inovação
   - **Social (S)**: Ensino, cuidado, ajuda ao próximo
   - **Empreendedor (E)**: Liderança, persuasão, vendas, gestão
   - **Convencional (C)**: Organização, dados, processos estruturados
3. Gerar código Holland de 3 letras (ex: IAS, ECS)
4. Cruzar com dados anteriores para validação:
   - Alta abertura -> geralmente A e/ou I
   - Alta extroversão + ambição -> geralmente E e/ou S
   - Alta conscienciosidade -> geralmente C e/ou R
5. Mapear código Holland para famílias de carreiras compatíveis
6. Para contexto de contratação, avaliar fit com a vaga/papel específico
7. Para contexto de transição de carreira, identificar áreas de maior potencial
8. Identificar ambientes de trabalho mais compatíveis (estruturado vs flexível, individual vs coletivo)
9. Calcular confiança da camada
10. Gerar lista de carreiras/funções sugeridas com grau de fit

## Outputs

- `riasec-code`: Código Holland de 3 letras
- `riasec-scores`: Scores por tipo (0-100)
- `career-families`: Famílias de carreiras compatíveis
- `environment-fit`: Ambientes de trabalho recomendados
- `career-suggestions`: Lista de carreiras sugeridas com grau de fit
- `career-confidence`: Confiança da camada

## Checklist de Conclusão

- [ ] Perguntas de interesses profissionais aplicadas
- [ ] Código Holland gerado
- [ ] Cruzamento com camadas anteriores validado
- [ ] Famílias de carreiras mapeadas
- [ ] Ambientes compatíveis identificados
- [ ] Confiança calculada
- [ ] Dados registrados no session record

## Próxima Task

`tasks/assessment/run-conation-layer.md` — Rodar modo de ação
