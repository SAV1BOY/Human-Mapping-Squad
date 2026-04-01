---
type: checklist
level: layer
layer: conation
squad: human-mapping
version: "2.0.0"
---

# Checklist: Qualidade da Identificacao dos Modos de Acao

## Proposito
Garantir que os 4 Kolbe Action Modes foram identificados com scores e zonas corretamente classificadas.

## Criterios Obrigatorios
- [ ] Os 4 Kolbe Action Modes foram identificados: Fact Finder, Follow Thru, Quick Start, Implementor — Evidencia: `Kolbe A scores registrados para cada modo: Fact Finder (1-10), Follow Thru (1-10), Quick Start (1-10), Implementor (1-10)`
- [ ] Cada Action Mode possui um score estimado dentro da escala valida — Evidencia: `Score numerico de 1 a 10 atribuido a cada Action Mode no perfil Kolbe A com justificativa baseada em respostas`
- [ ] Zonas de operacao foram classificadas: Prevent, Accommodate ou Initiate — Evidencia: `Zone classification per mode documentada: Prevent (1-3), Accommodate (4-6), Initiate (7-10) para cada Action Mode`
- [ ] Classificacao das zonas e coerente com os scores atribuidos — Evidencia: `Validacao cruzada entre score numerico e zona atribuida confirmada para os 4 modos sem inconsistencias`
- [ ] Modo de acao dominante (Initiate) foi destacado — Evidencia: `Action Mode com score mais alto (zona Initiate) identificado como dominante com descricao de manifestacao comportamental`
- [ ] Modo de acao evitado (Prevent) foi destacado — Evidencia: `Action Mode com score mais baixo (zona Prevent) identificado com descricao de comportamentos naturalmente evitados`
- [ ] Descricao comportamental de cada modo esta presente — Evidencia: `Campo 'descricao_comportamental' preenchido para cada um dos 4 modos com exemplos de como o score se manifesta no dia a dia`
- [ ] Dados utilizados para a identificacao sao rastrevaeis — Evidencia: `Secao 'fontes_de_dados' com referencia ao questionario/entrevista utilizado, data de coleta e respostas-chave mapeadas`
- [ ] Identificacao diferencia entre comportamento natural e comportamento adaptado — Evidencia: `Colunas 'comportamento_natural' e 'comportamento_adaptado' preenchidas por modo, com indicacao de contextos de adaptacao`

## Criterios Desejaveis
- [ ] Exemplos concretos de manifestacao de cada Action Mode foram fornecidos
- [ ] Comparacao com distribuicao populacional foi incluida
- [ ] Interacao entre os 4 modos foi analisada como sistema integrado
- [ ] Implicacoes praticas de cada zona foram descritas para o dia a dia

## Decisao
- **PASS**: Todos os 9 criterios obrigatorios atendidos com Kolbe A scores registrados para os 4 modos, zone classification correta e descricoes comportamentais completas.
- **CONDITIONAL**: 7-8 criterios obrigatorios atendidos. Descricoes comportamentais incompletas ou diferenciacao natural/adaptado parcial, corrigiveis sem re-coleta.
- **FAIL**: Menos de 7 criterios obrigatorios atendidos, ou Kolbe A scores ausentes para algum Action Mode, ou zone classification inconsistente com scores.

## Acao se Falhar
Retornar ao kolbe-analyst para revisao dos scores e zonas. Verificar se os dados de entrada sao suficientes para a classificacao. Se insuficientes, solicitar informacoes complementares antes de re-processar.

## Agente Responsavel
kolbe-analyst
