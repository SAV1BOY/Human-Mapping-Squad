# Metodologia de Proxy-Inference

## Visão Geral
Este documento descreve a metodologia utilizada pelo squad para inferir resultados
de um framework a partir de dados de outro framework, quando avaliação direta
não é possível ou viável. Proxy-inference é uma ferramenta útil mas com
limitações que devem ser sempre documentadas.

## Conteúdo

### O que é proxy-inference
É o processo de estimar o resultado de um framework (alvo) utilizando dados
obtidos por outro framework (fonte), baseado em correlações conhecidas entre
as dimensões de ambos os instrumentos.

### Mapeamentos suportados
| Fonte | Alvo | Confiança da conversão |
|-------|------|----------------------|
| Big Five → | MBTI | Moderada (0.5-0.6) |
| Big Five → | DISC | Moderada (0.5-0.6) |
| Hogan HPI → | Big Five | Alta (0.7-0.8) |
| CliftonStrengths → | Belbin | Baixa (0.3-0.4) |
| RIASEC → | Big Five (parcial) | Baixa (0.3-0.4) |

### Regras de uso
1. Proxy-inference nunca substitui avaliação direta para decisões críticas
2. Sempre documentar que o resultado é inferido, não medido diretamente
3. Reduzir o nível de confiança proporcionalmente à qualidade do mapeamento
4. Sinalizar claramente no relatório com marcação "[proxy]"
5. Registrar o método utilizado no methodology-registry.yaml

### Limitações
- Correlações entre frameworks são imperfeitas e baseadas em amostras específicas
- Perda de informação nas subfacetas e nuances de cada framework
- Risco de circularidade se múltiplas inferências são encadeadas
- Viés de confirmação ao interpretar resultados inferidos

---

## Quando Usar Proxy vs Avaliação Direta

### Use proxy-inference quando:
- O instrumento alvo não está disponível (licença, custo, tempo)
- O respondente já completou múltiplos instrumentos e fadiga é um risco
- O projeto precisa de cobertura ampla mas o orçamento é limitado
- A dimensão alvo é complementar (não central) ao objetivo do projeto

### Nunca use proxy-inference quando:
- A decisão é de alto impacto (contratação executiva, promoção sênior)
- O framework alvo é central ao objetivo do projeto
- A confiança do mapeamento fonte → alvo é baixa (< 0.40)
- O cliente solicitou explicitamente avaliação direta

## Ajustes de Confiança por Tipo de Proxy

| Tipo de proxy | Penalidade na confiança | Confiança máxima possível |
|--------------|------------------------|--------------------------|
| Mapeamento direto validado (ex: HPI → Big Five) | -0.10 a -0.15 | 0.70 |
| Mapeamento por correlação teórica (ex: Big Five → MBTI) | -0.20 a -0.30 | 0.60 |
| Inferência por padrão comportamental (ex: CliftonStrengths → Belbin) | -0.30 a -0.40 | 0.45 |
| Proxy encadeado (fonte → intermediário → alvo) | -0.40 a -0.50 | 0.35 |

> **Regra**: nunca encadeie mais de 2 proxies. Proxy de proxy de proxy tem
> confiança tão baixa que não agrega valor ao relatório.

## Design de Indicadores Comportamentais

Quando proxy formal não existe, é possível inferir dimensões a partir de
indicadores comportamentais observáveis. O processo é:

1. **Definir a dimensão-alvo**: qual traço, tipo ou motivação queremos estimar?
2. **Listar comportamentos correlacionados**: baseado em literatura, quais
   comportamentos observáveis se correlacionam com a dimensão?
3. **Criar checklist de evidências**: para cada comportamento, definir evidência
   observável (ex: "frequentemente voluntaria-se para apresentações" → Extroversão)
4. **Atribuir pesos**: comportamentos com maior correlação recebem peso maior
5. **Calcular score e confiança**: somar evidências ponderadas e atribuir confiança
   proporcional à quantidade e qualidade das evidências (máximo 0.50)
6. **Documentar**: registrar indicadores usados, pesos e fontes de evidência

> Para o guia completo de proxy-inference com todos os mapeamentos validados e
> indicadores comportamentais padronizados, consulte
> `authority/guides/proxy-inference-mode-guide.md`.

## Referências
- `data/registries/methodology-registry.yaml` — Registro de metodologias
- `docs/confidence-scoring-guide.md` — Sistema de confiança
- `authority/guides/proxy-inference-mode-guide.md` — Guia completo de proxy
