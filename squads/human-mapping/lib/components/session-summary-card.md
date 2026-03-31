# Card: Resumo de Sessão

## Objetivo

Sintetizar os resultados de uma sessão de mapeamento concluída em formato padronizado para registro, acompanhamento e comunicação cross-squad.

## Estrutura do Card

```yaml
session_summary_card:
  session_id: "[CÓDIGO-ÚNICO]"
  data: "[DD/MM/AAAA]"
  respondente: "[Nome ou código anônimo]"
  facilitador: "[Nome do facilitador]"
  tipo_sessao: "[Mapeamento completo / Parcial / Reavaliação / Workshop]"
  duracao_minutos: "[tempo total]"

  camadas_completadas:
    - nome: "[Nome da camada]"
      status: "[Completa / Parcial / Não iniciada]"
      confianca: "[Alta / Média / Baixa]"
    # Repetir para cada camada

  confianca_geral: "[Alta / Média / Baixa]"
  justificativa_confianca: "[Breve explicação do nível de confiança geral]"

  achados_principais:
    - "[Achado 1 — o insight mais relevante da sessão]"
    - "[Achado 2 — segundo insight em ordem de importância]"
    - "[Achado 3 — terceiro insight ou padrão identificado]"

  contradicoes_detectadas:
    - descricao: "[Qual contradição]"
      frameworks_envolvidos: "[Framework A vs Framework B]"
      severidade: "[Alta / Média / Baixa]"
      resolucao: "[Resolvida na sessão / Pendente / Requer investigação]"

  prioridades_de_desenvolvimento:
    - prioridade: "[Área de desenvolvimento]"
      urgencia: "[Alta / Média / Baixa]"
      base: "[Quais dados sustentam esta prioridade]"

  proximos_passos:
    - "[Ação 1 com responsável e prazo]"
    - "[Ação 2 com responsável e prazo]"
    - "[Ação 3 com responsável e prazo]"

  notas_do_facilitador: |
    [Observações qualitativas que não cabem nos campos estruturados:
    engajamento do respondente, sinais não-verbais relevantes,
    hipóteses a investigar, ajustes metodológicos necessários]
```

## Regras de Preenchimento

### Session ID
Formato: `HMS-[ANO][MÊS]-[SEQUENCIAL]` (ex: HMS-202603-042)

### Confiança Geral
- **Alta**: Todos os instrumentos aplicados, respondente engajado, convergência clara
- **Média**: Alguns instrumentos por proxy, leve fadiga ou contradição menor
- **Baixa**: Múltiplos proxies, fadiga significativa, contradições não resolvidas

### Achados Principais
- Máximo 3 bullets — forçar priorização
- Cada bullet deve ser acionável ou revelar um padrão significativo
- Evitar repetir dados brutos; focar em síntese e insight

### Contradições
- Registrar TODAS, mesmo as resolvidas na sessão
- Contradições resolvidas são evidência de profundidade da análise
- Contradições pendentes devem gerar itens em "próximos passos"

### Próximos Passos
- Cada item deve ter: ação clara + responsável + prazo estimado
- Incluir tanto ações do facilitador quanto do respondente
- Se houver handoff para outro squad, especificar qual e o que será enviado

## Uso do Card

| Contexto | Como Usar |
|----------|-----------|
| Registro interno | Arquivar como documentação da sessão |
| Handoff para coaching | Enviar como briefing para o coach |
| Cross-squad | Usar como base para o formato de compatibilidade |
| Reavaliação futura | Comparar com card da sessão anterior |
| Supervisão | Revisar qualidade e consistência metodológica |

## Exemplo Preenchido (Parcial)

```yaml
session_summary_card:
  session_id: "HMS-202603-015"
  data: "15/03/2026"
  respondente: "Respondente-Alpha"
  confianca_geral: "Média"
  achados_principais:
    - "Forte tensão entre preferência por autonomia (Big Five) e necessidade de validação (Eneatipo 3)"
    - "CliftonStrengths top-5 concentrados em Execução — possível ponto cego em Relacionamento"
    - "Kolbe sugere resistência a processos rígidos que contradiz Conscienciosidade alta"
```
