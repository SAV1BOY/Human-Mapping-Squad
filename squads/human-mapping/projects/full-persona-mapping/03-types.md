# Fase 03 — Tipologia

## Objetivo
Complementar o perfil dimensional com classificações tipológicas (MBTI, Eneagrama,
DISC), oferecendo linguagem acessível e categorias práticas para o cliente.

## Inputs
- Perfil de traços (Fase 02)
- Resultados de instrumentos tipológicos aplicados
- Mapeamentos de conversão traço-tipo (quando usando proxy)

## Processo
1. Coletar ou derivar tipo MBTI (direto ou via mapeamento Big Five)
2. Identificar tipo Eneagrama (se dados disponíveis)
3. Mapear perfil DISC (direto ou inferido)
4. Cruzar resultados tipológicos com perfil de traços
5. Identificar convergências e divergências entre sistemas
6. Documentar nível de confiança para cada tipologia

## Outputs
- Tipo MBTI identificado com nível de confiança
- Tipo Eneagrama identificado (se aplicável)
- Perfil DISC mapeado
- Análise de convergência entre tipologias e traços
- Contradições identificadas para investigação posterior

## Checklist
- [ ] Tipo MBTI determinado (direto ou proxy)
- [ ] Eneagrama mapeado (se no escopo)
- [ ] Perfil DISC determinado
- [ ] Cruzamento com Big Five realizado
- [ ] Convergências documentadas
- [ ] Contradições sinalizadas para Fase 07

## Critérios de Decisão

### GO (avançar para próxima fase)
- [ ] ≥ 2 frameworks tipológicos avaliados (ex: MBTI + DISC, ou MBTI + Eneagrama)
- [ ] Cruzamento com Big Five realizado e documentado
- [ ] Contradições sinalizadas para Fase 07

### NO-GO (não avançar)
- Apenas 1 framework avaliado sem possibilidade de cruzamento → Ação: aplicar segundo framework ou proxy
- Divergência crítica entre tipologias sem explicação → Ação: investigar antes de avançar

### Entregáveis Obrigatórios
- `type-style-map-template` — preenchido e validado

### Arquivos Relacionados
- `templates/layers/type-style-map-template.md`
- `checklists/type-assessment-quality.md`
- `checklists/types/mbti-inference-quality.md`
- `workflows/04-type-style-assessment-flow.md`

## Próxima Fase
`04-motivation.md` — Avaliação de motivações e valores
