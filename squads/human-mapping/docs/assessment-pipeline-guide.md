# Guia do Pipeline de Avaliação

## Visão Geral
Este guia descreve o pipeline completo de avaliação do Human Mapping Squad,
desde a solicitação inicial até a entrega do relatório final, incluindo
pontos de decisão, gates de qualidade e fluxos alternativos.

## Conteúdo

### Pipeline padrão (Full Persona Mapping)
1. **Intake** — coleta de dados e alinhamento
2. **Calibração** — seleção de frameworks e instrumentos
3. **Avaliação dimensional** — traços, tipos, motivações, forças
4. **Orientação** — tradução em direcionamentos práticos
5. **Contradições** — resolução de inconsistências
6. **Síntese** — integração em perfil coerente
7. **Relatório** — geração e entrega do documento final

### Gates de qualidade
- Após intake: validação de completude dos dados
- Após calibração: aprovação do plano de avaliação
- Após avaliação: verificação de níveis de confiança mínimos
- Após síntese: peer review da narrativa integrada
- Após relatório: revisão final antes da entrega

### Fluxos alternativos
- Pipelines reduzidos para projetos específicos (leadership, hiring, etc.)
- Reassessment: pipeline de reavaliação com comparação temporal
- Emergência: pipeline acelerado para demandas urgentes

### Tempos médios
| Tipo de projeto | Duração típica |
|----------------|----------------|
| Full Persona | 2-4 semanas |
| Leadership | 1-3 semanas |
| Hiring | 1-2 semanas |
| Team Composition | 2-3 semanas |
| Career Guidance | 1-2 semanas |

---

## Detalhamento de Cada Etapa do Pipeline

### 1. Intake (Tempo: 30-60 min)
- **Agentes**: `intake-orchestrator`, `context-mapper`
- **Entradas**: solicitação do cliente, dados disponíveis do respondente
- **Saídas**: ficha de intake completa, contexto mapeado
- **Problema comum**: dados insuficientes. Solução: usar checklist de dados mínimos
  por tipo de projeto antes de avançar.

### 2. Calibração (Tempo: 15-30 min)
- **Agentes**: `readiness-gatekeeper`, `human-mapping-chief`
- **Entradas**: ficha de intake
- **Saídas**: plano de avaliação com frameworks selecionados e confiança-alvo
- **Problema comum**: escolha de frameworks inadequados ao objetivo. Solução:
  consultar `framework-selection-guide.md` e validar com a matriz de recomendação.

### 3. Avaliação Dimensional (Tempo: 1-3 dias)
- **Agentes**: chiefs de cada camada + analistas especializados
- **Entradas**: plano de avaliação, dados do respondente
- **Saídas**: resultados por framework com níveis de confiança individuais
- **Problema comum**: respostas com desejabilidade social alta. Solução: o
  `respondent-quality-auditor` aplica checklist de validade e sinaliza respostas suspeitas.

### 4. Orientação e Carreira (Tempo: 1-2 horas)
- **Agentes**: `career-fit-analyst`, `riasec-strong-analyst`, `development-planner`
- **Entradas**: resultados das avaliações dimensionais
- **Saídas**: direcionamentos de carreira, plano de desenvolvimento
- **Problema comum**: falta de dados vocacionais. Solução: usar proxy-inference
  de Big Five para RIASEC quando dados diretos não existem (marcar como [proxy]).

### 5. Contradições (Tempo: 30-60 min)
- **Agentes**: `contradiction-auditor`
- **Entradas**: todos os resultados das avaliações
- **Saídas**: registro de contradições classificadas, resolução proposta
- **Problema comum**: contradições genuínas forçadas a resolução. Solução: usar
  a técnica do "E" (ambos válidos) antes de forçar uma resolução.

### 6. Síntese (Tempo: 1-2 horas)
- **Agentes**: `synthesis-architect`, `rapport-architect`
- **Entradas**: resultados resolvidos, contradições documentadas
- **Saídas**: narrativa integrada, mapa visual de persona
- **Problema comum**: narrativa genérica sem diferenciação. Solução: usar o
  checklist anti-Barnum do `report-writing-guide.md`.

### 7. Relatório (Tempo: 1-2 horas)
- **Agentes**: `report-writer`, `respondent-quality-auditor` (revisão)
- **Entradas**: narrativa integrada, dados de confiança
- **Saídas**: relatório final formatado, pronto para entrega
- **Problema comum**: linguagem determinista. Solução: revisão automática
  substitui "é" por "tende a" e inclui confiança em cada afirmação.

## Referências
- `projects/` — Templates de cada tipo de projeto
- `docs/framework-selection-guide.md` — Como escolher frameworks
- `docs/confidence-scoring-guide.md` — Sistema de confiança
- `workflows/` — Definição detalhada de cada fluxo
