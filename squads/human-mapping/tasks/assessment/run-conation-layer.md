---
type: task
squad: human-mapping
version: "2.0.0"
agent: assessment-agent
workflow: assessment-workflow
---

# Task: Rodar Modo de Ação (Kolbe)

## Objetivo

Executar a camada conativa utilizando o framework Kolbe, identificando o modo instintivo de ação do respondente — como ele naturalmente inicia, resolve problemas e produz resultados.

## Pré-condições

- Todas as camadas anteriores do assessment concluídas
- Dados de personalidade, motivação e forças disponíveis
- Respondente ainda engajado (última camada de assessment)

## Passos

1. Carregar banco de perguntas conativas de `lib/questions/conation/`
2. Explicar ao respondente que esta camada avalia "como você faz" (não o que sabe ou quer)
3. Aplicar perguntas para avaliar os 4 modos de ação Kolbe:
   - **Fact Finder (FF)**: Como busca e processa informação
     - Alto: pesquisa extensiva antes de agir
     - Baixo: age com informação mínima, simplifica
   - **Follow Thru (FT)**: Como organiza e estrutura
     - Alto: cria sistemas, processos, checklists
     - Baixo: improvisa, adapta no caminho
   - **Quick Start (QS)**: Como lida com risco e incerteza
     - Alto: abraça mudança, inicia rápido, experimenta
     - Baixo: prefere estabilidade, resiste a mudança brusca
   - **Implementor (IM)**: Como lida com espaço e tangibilidade
     - Alto: precisa de protótipos, modelos físicos
     - Baixo: trabalha confortavelmente com abstrações
4. Usar cenários de decisão e resolução de problemas para capturar instintos
5. Calcular score em cada modo de ação (escala 1-10)
6. Gerar perfil Kolbe com zona de operação por modo (iniciante, acomodador, resistente)
7. Cruzar com dados anteriores:
   - Alto QS + alta abertura + baixa conscienciosidade: perfil consistente
   - Alto FF + baixa abertura: possível inconsistência, investigar
8. Identificar potenciais conflitos entre instinto conativo e ambiente/função atual
9. Calcular confiança da camada

## Outputs

- `kolbe-profile`: Scores nos 4 modos de ação (1-10 cada)
- `action-zones`: Zona de operação por modo
- `conative-conflicts`: Conflitos entre instinto e ambiente
- `kolbe-confidence`: Confiança da camada
- `productivity-tips`: Dicas de produtividade baseadas no perfil

## Checklist de Conclusão

- [ ] Perguntas conativas aplicadas
- [ ] Scores calculados nos 4 modos
- [ ] Zonas de operação identificadas
- [ ] Cruzamento com camadas anteriores realizado
- [ ] Conflitos conativos identificados
- [ ] Confiança calculada
- [ ] Dados registrados no session record

## Próxima Task

`tasks/audit/audit-contradictions.md` — Auditar contradições entre frameworks
