# Card: Flag de Risco em Assessment

## Objetivo

Sinalizar riscos que podem comprometer a validade, a confiança ou a interpretação de um assessment, garantindo transparência e ação corretiva.

## Estrutura do Card

```yaml
risk_flag_card:
  respondente: "[Nome ou código]"
  sessao_id: "[HMS-XXXXXXXX]"
  data_flag: "[DD/MM/AAAA]"

  flags:
    - tipo_risco: "[Barnum / Baixa Confiança / Fadiga / Desejabilidade Social / Contradição / Outro]"
      severidade: "[Crítica / Alta / Média / Baixa]"
      evidencia: "[Dados específicos que geraram o flag]"
      impacto_interpretacao: "[Como este risco afeta a leitura dos resultados]"
      acao_recomendada: "[O que fazer a respeito]"
      status: "[Ativo / Mitigado / Resolvido]"
```

## Tipos de Risco

### 1. Efeito Barnum
**O que é:** Interpretações genéricas que parecem precisas mas se aplicam a qualquer pessoa.

| Severidade | Indicador |
|------------|-----------|
| Crítica | Mais de 50% das conclusões são genéricas e não diferenciadas |
| Alta | Achados principais são vagos, sem especificidade individual |
| Média | Algumas conclusões são genéricas, mas o perfil tem elementos únicos |
| Baixa | Risco pontual em um ou dois itens específicos |

**Ação:** Revisar cada afirmação com o teste "isso se aplicaria a 70%+ das pessoas?" — se sim, refinar ou remover.

### 2. Baixa Confiança
**O que é:** Dados insuficientes ou ambíguos para sustentar as conclusões apresentadas.

| Severidade | Indicador |
|------------|-----------|
| Crítica | Confiança geral da sessão abaixo de 50% |
| Alta | Camadas inteiras baseadas em evidência fraca ou proxy único |
| Média | Alguns achados com base limitada, mas núcleo do perfil é sólido |
| Baixa | Confiança reduzida em itens periféricos que não afetam conclusões centrais |

**Ação:** Declarar limitações explicitamente; recomendar aplicação de instrumentos oficiais; não usar dados de baixa confiança para decisões de alto impacto.

### 3. Fadiga do Respondente
**O que é:** Queda de qualidade nas respostas por cansaço, desatenção ou perda de motivação ao longo da sessão.

| Severidade | Indicador |
|------------|-----------|
| Crítica | Respondente declarou desengajamento ou respostas finais são claramente aleatórias |
| Alta | Padrão claro de respostas aceleradas ou uniformes na segunda metade |
| Média | Leve redução de elaboração nas respostas, mas dados ainda parecem válidos |
| Baixa | Sinais sutis de cansaço sem impacto mensurável |

**Ação:** Ponderar dados da segunda metade com menor peso; considerar sessão de follow-up para validar; reduzir duração de sessões futuras.

### 4. Desejabilidade Social
**O que é:** Respondente distorce respostas (consciente ou inconscientemente) para parecer mais favorável.

| Severidade | Indicador |
|------------|-----------|
| Crítica | Perfil "perfeito demais" — sem fraquezas, sem contradições, tudo no extremo positivo |
| Alta | Divergência clara entre autorrelato e evidências comportamentais |
| Média | Alguns indicadores inflados, mas padrão geral ainda parece autêntico |
| Baixa | Leve tendência positiva consistente com desejabilidade social normal |

**Ação:** Cruzar com dados comportamentais; usar escalas de validade quando disponíveis; explorar contradições com perguntas situacionais.

### 5. Contradição Não Resolvida
**O que é:** Frameworks apresentam resultados conflitantes que não foram explicados ou integrados.

| Severidade | Indicador |
|------------|-----------|
| Crítica | Contradição afeta a conclusão central do perfil |
| Alta | Contradição em camada importante sem explicação plausível |
| Média | Contradição em camada secundária ou com explicação parcial |
| Baixa | Nuance sutil entre frameworks que não altera conclusões |

**Ação:** Investigar com dados adicionais; buscar explicação contextual; se não resolvível, declarar a contradição no relatório.

## Matriz de Ação por Severidade

| Severidade | Ação Imediata | Impacto no Relatório |
|------------|---------------|---------------------|
| Crítica | Pausar interpretação; buscar dados adicionais ou nova sessão | Seção dedicada a limitações; conclusões afetadas são condicionais |
| Alta | Documentar flag; ajustar confiança dos achados impactados | Nota de ressalva nos achados específicos |
| Média | Registrar flag; monitorar padrão ao longo do relatório | Menção breve nas limitações |
| Baixa | Registrar para referência futura | Sem impacto no relatório |

## Regras de Governança

1. **Flags críticas exigem revisão por segundo facilitador** antes de finalizar relatório
2. **Flags nunca são deletados** — podem ser mitigados ou resolvidos, mas o registro permanece
3. **Acúmulo de 3+ flags médias equivale a 1 flag alta** em termos de ação
4. **O respondente tem direito de saber** sobre flags que afetam suas conclusões
