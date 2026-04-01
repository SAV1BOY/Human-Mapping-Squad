# Changelog

## Visão Geral
Registro cronológico de todas as mudanças significativas no repositório do
Human Mapping Squad, incluindo novos conteúdos, atualizações de metodologia
e correções.

## Conteúdo

### 2026-03-31 — Estrutura Inicial
- Criação da estrutura completa do repositório
- Adição de 9 resumos de frameworks em `authority/framework-summaries/`
  - MBTI, DISC, Eneagrama, CliftonStrengths, Belbin
  - Hogan, RIASEC, Kolbe, FIRO-B/PCM/Birkman
- Adição de 5 kits de workshop em `authority/workshop-kits/`
- Criação de 7 tipos de projeto com templates completos em `projects/`
  - Full Persona Mapping (10 fases)
  - Leadership Assessment (6 fases)
  - Hiring Assessment (5 fases)
  - Team Composition (5 fases)
  - Career Guidance (5 fases)
  - Personal Development (5 fases)
  - Reassessment (4 fases)
- Criação de 10 registries YAML em `data/registries/`
- Criação de 18 documentos de referência em `docs/`

### Formato de entrada
Cada entrada deve seguir o formato:
```
### YYYY-MM-DD — Título da Mudança
- Descrição do que foi adicionado, alterado ou removido
- Impacto na operação do squad
- Referências aos arquivos afetados
```

### v2.0.0 — 2026-03-31 — Full MMOS Integration
- Integração completa com o MMOS (Multi-Model Orchestration System)
- Implementação de decision trees para roteamento de projetos
- Go/no-go gates em cada fase dos projetos com critérios mensuráveis
- Contratos cross-squad formalizados (Human Mapping → Strategy, People, etc.)
- Adição de 18 documentos de referência em `docs/`
- Criação de 10 registries YAML em `data/registries/`
- Reestruturação completa do repositório para padrão MMOS
- Quality gates com thresholds de confiança por tipo de projeto
- Suporte a modos /quick, /standard e /deep com pipelines diferenciados

### v1.5.0 — 2026-02-15 — Quality Gates e Confidence Scoring
- Introdução do sistema de confiança por camada (score 0.0-1.0 por framework)
- Score de confiança global com metodologia de média ponderada documentada
- Penalidade automática por divergências não resolvidas entre frameworks
- Bônus de confiança por convergências fortes entre 3+ frameworks
- Gates de qualidade: relatório não é liberado se confiança global < 0.6
- Adição do `contradiction-resolution-guide.md` com protocolo S1/S2/S3
- Detecção de desejabilidade social via inconsistência inter-framework
- Implementação de proxy-inference com marcação "[proxy]" obrigatória
- Calibração cultural para normas brasileiras do NEO-PI-R

### v1.2.0 — 2026-01-20 — Swipe Files e Phrase Libraries
- Criação do diretório `swipe/` com perfis de exemplo gold-standard
- Perfil CEO (Ricardo Almeida) como referência de mapeamento completo
- Adição de `phrases/` com bibliotecas de frases operacionais
- Frases de rapport, reframing, encerramento e transição
- Templates de devolutiva para diferentes públicos

### v1.1.0 — 2026-01-05 — Expansão de Frameworks
- Adição de 9 resumos de frameworks em `authority/framework-summaries/`
- Inclusão de MBTI, DISC, Enneagram, CliftonStrengths, Belbin
- Inclusão de Hogan, RIASEC, Kolbe, FIRO-B/PCM/Birkman
- Adição de 5 kits de workshop em `authority/workshop-kits/`
- Tabela de correlação inter-framework (`framework-correlation-matrix.md`)

### v1.0.0 — 2025-12-01 — Release Inicial
- Estrutura inicial do repositório com 34 agentes definidos
- Suporte a 26 frameworks de personalidade e comportamento
- Pipeline básico de mapeamento: coleta → análise → síntese → relatório
- 7 tipos de projeto com templates completos em `projects/`:
  Full Persona Mapping, Leadership Assessment, Hiring Assessment,
  Team Composition, Career Guidance, Personal Development, Reassessment
- Documentação base: getting-started, ethical-use-policy, FAQ inicial
- Integração com formato YAML para registries de dados

## Referências
- `docs/contribution-guide.md` — Como contribuir com mudanças
- `docs/naming-conventions.md` — Convenções de nomenclatura
