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

## Referências
- `data/registries/methodology-registry.yaml` — Registro de metodologias
- `docs/confidence-scoring-guide.md` — Sistema de confiança
