# Fase 06: Monitoramento Continuo da Dinamica de Equipe

## Objetivo

Acompanhar a evolucao da dinamica de equipe apos mudancas de composicao, detectando precocemente sinais de disfuncao e validando se as recomendacoes do assessment de composicao estao gerando os resultados esperados. Equipes sao sistemas vivos — a fotografia do assessment inicial muda com o tempo.

## Quando Executar

- **Check-in rapido:** Mensalmente nos primeiros 3 meses apos mudanca de composicao
- **Revisao estruturada:** Trimestralmente apos os primeiros 3 meses
- **Reassessment completo:** Anualmente ou quando houver mudanca significativa (saida, entrada, mudanca de lider)

## Metricas de Monitoramento

### 1. Indicadores de Saude da Equipe

| Indicador | Metodo de Medicao | Frequencia | Sinal de Alerta |
|-----------|------------------|-----------|-----------------|
| Satisfacao da equipe | Pulse survey (1-10) | Mensal | Score < 6 ou queda > 1.5 pontos |
| Conflitos nao resolvidos | Relato do lider + equipe | Mensal | 2+ conflitos ativos sem resolucao |
| Turnover/intencao de saida | Confidencial ao RH | Trimestral | Qualquer membro avaliando saida |
| Entrega de resultados | Metricas de performance | Mensal | Queda > 15% vs. baseline |
| Coesao percebida | Survey ou retrospectiva | Trimestral | Score < 6 |

### 2. Indicadores Derivados do Assessment

| Indicador | O que Monitorar | Sinal de Alerta |
|-----------|----------------|-----------------|
| Cobertura Belbin | Papeis nao cobertos estao gerando problemas? | Gap de papel correlaciona com falha recorrente |
| Pares de atrito | Pares identificados como risco estao em conflito? | Conflito repetido entre par previsto |
| Compatibilidade DISC | Comunicacao entre estilos diferentes esta fluindo? | Mal-entendidos recorrentes entre perfis opostos |
| Lider-equipe fit | O estilo do lider esta funcionando para a equipe? | Equipe reporta falta de suporte ou microgerenciamento |

## Protocolo de Check-In Mensal (Primeiros 3 Meses)

### Duracao: 30 minutos com o lider da equipe

**Roteiro:**
1. Como esta a dinamica geral da equipe esta semana? (1-10 + justificativa)
2. Algum conflito ou tensao entre membros especificos?
3. Os papeis estao claros? Alguem esta sobrecarregado ou subutilizado?
4. As recomendacoes do assessment de composicao foram implementadas?
5. Ha algo que o assessment nao previu e que emergiu?

**Registro:**
```yaml
monthly_checkin:
  date: ___
  team_health_score: ___ /10
  active_issues:
    - ___
  recommendations_implemented: (Todas / Parciais / Nenhuma)
  new_observations: ___
  action_required: (Sim / Nao)
```

## Protocolo de Revisao Trimestral

### Duracao: 60-90 minutos com equipe completa (retrospectiva facilitada)

**Estrutura:**
1. **O que esta funcionando bem na dinamica da equipe?** (10 min)
2. **O que esta gerando atrito ou ineficiencia?** (15 min)
3. **Revisao dos pares de risco previstos** — confirmados ou nao? (10 min)
4. **Gaps de papel Belbin** — estao sendo sentidos? (10 min)
5. **Acoes para o proximo trimestre** (15 min)

**Output:** Atualizacao do Team Dynamics Report com dados reais vs. previsoes.

## Criterios para Reassessment Completo

Acionar reassessment completo quando:
- [ ] Novo membro entra na equipe (perfil individual + integracao ao mapa)
- [ ] Membro sai da equipe (recalcular cobertura e gaps)
- [ ] Lider da equipe muda (novo perfil de lideranca + compatibilidade)
- [ ] Objetivo da equipe muda significativamente (nova demanda de papeis)
- [ ] Score de saude da equipe cai abaixo de 5 por 2 meses consecutivos
- [ ] 12 meses desde o ultimo assessment completo

## Documentacao Longitudinal

Manter registro historico para detectar tendencias:

```yaml
team_health_timeline:
  - date: ___
    health_score: ___
    key_events: ___
  - date: ___
    health_score: ___
    key_events: ___
```

## Integracao com RalphLoop

A cada 3 meses, submeter dados de monitoramento de equipe ao processo de RalphLoop para:
- Validar acuracia das previsoes de conflito
- Calibrar o algoritmo de composicao de equipe
- Identificar melhorias no processo de team-composition-assessment

## Notas Importantes

- Monitoramento NAO e vigilancia — a equipe deve saber que o acompanhamento existe e qual seu proposito
- Dados individuais de assessment permanecem confidenciais — o monitoramento foca na dinamica coletiva
- O lider da equipe e co-responsavel pelo monitoramento, nao apenas o analista externo
- Equipes remotas ou hibridas podem necessitar frequencia de monitoramento maior nos primeiros meses

## Critérios de Decisão

### GO (avançar — ciclo de monitoramento encerrado)
- [ ] Score de saúde da equipe ≥ 6 por 2 meses consecutivos
- [ ] Gaps críticos da Fase 02 preenchidos ou em mitigação ativa
- [ ] Dados de monitoramento submetidos ao RalphLoop

### NO-GO (não encerrar monitoramento)
- Score de saúde < 5 por 2 meses → Ação: acionar reassessment completo
- Membro saiu ou entrou na equipe → Ação: recalcular cobertura e gaps

### Entregáveis Obrigatórios
- `monthly_checkin` (YAML) — preenchido a cada check-in
- `team-dynamics-report-template` — atualizado trimestralmente

### Arquivos Relacionados
- `templates/reports/team-dynamics-report-template.md`
- `checklists/team/team-dynamics-quality.md`
- `workflows/20-ralphloop-assessment-retro.md`
