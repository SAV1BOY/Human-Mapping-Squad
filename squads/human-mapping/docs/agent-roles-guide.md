# Guia de Papéis dos Agentes

## Visão Geral
Este guia descreve os papéis e responsabilidades de cada agente que opera dentro
do Human Mapping Squad, incluindo suas competências, escopo de atuação e
interações com outros agentes.

## Conteúdo

### Agente de Intake
- **Responsabilidade**: coleta inicial de dados e alinhamento de expectativas
- **Escopo**: fases de intake em todos os tipos de projeto
- **Competências**: comunicação, organização, empatia

### Agente de Avaliação
- **Responsabilidade**: aplicação e interpretação de instrumentos de avaliação
- **Escopo**: fases de avaliação de traços, tipos, motivações e forças
- **Competências**: psicometria, frameworks de personalidade, análise de dados

### Agente de Síntese
- **Responsabilidade**: integração de dados e resolução de contradições
- **Escopo**: fases de síntese, contradições e relatório
- **Competências**: pensamento sistêmico, escrita, análise crítica

### Agente de Relatório
- **Responsabilidade**: geração de relatórios finais e comunicação de resultados
- **Escopo**: fase de relatório e entrega ao cliente
- **Competências**: escrita clara, adaptação de linguagem, visualização

### Agente de Qualidade
- **Responsabilidade**: revisão de qualidade e calibração de confiança
- **Escopo**: transversal a todas as fases
- **Competências**: validação, calibração estatística, atenção a detalhes

---

## Tabela Completa dos 34 Agentes

### Camada de Orquestração
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `human-mapping-chief` | Líder do squad | Coordena todo o pipeline, decisões estratégicas |
| `intake-orchestrator` | Orquestrador de intake | Coleta de dados, alinhamento, triagem de projetos |
| `readiness-gatekeeper` | Gatekeeper | Valida prontidão dos dados antes de avançar fase |
| `context-mapper` | Mapeador de contexto | Mapeia contexto profissional, pessoal e cultural |

### Camada de Avaliação — Traços
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `trait-chief` | Líder de traços | Coordena avaliações dimensionais de traços |
| `big-five-analyst` | Analista Big Five | Avalia 5 fatores e 30 facetas de personalidade |
| `hexaco-analyst` | Analista HEXACO | Avalia 6 dimensões incluindo Honestidade-Humildade |
| `neo-16pf-analyst` | Analista NEO/16PF | Avalia via NEO-PI-R e 16PF de Cattell |
| `hogan-bright-side-analyst` | Analista HPI | Avalia lado brilhante (comportamento habitual) |
| `hogan-dark-side-analyst` | Analista HDS | Avalia descarriladores sob pressão |
| `predictive-index-analyst` | Analista PI | Avalia perfil comportamental no trabalho |

### Camada de Avaliação — Tipos e Estilos
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `type-style-chief` | Líder de tipos | Coordena avaliações tipológicas |
| `mbti-analyst` | Analista MBTI | Avalia 4 dicotomias e 16 tipos |
| `disc-analyst` | Analista DISC | Avalia perfil comportamental DISC |
| `insights-social-style-analyst` | Analista Insights | Avalia estilo social e energias de cor |

### Camada de Avaliação — Motivações
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `motivation-chief` | Líder de motivações | Coordena avaliações motivacionais |
| `enneagram-analyst` | Analista Eneagrama | Avalia tipo, asa e nível de saúde |
| `mvpi-driving-forces-analyst` | Analista MVPI | Avalia valores e forças motoras |
| `reiss-analyst` | Analista Reiss | Avalia 16 motivações básicas |
| `firo-pcm-birkman-analyst` | Analista FIRO/PCM/Birkman | Avalia necessidades interpessoais |
| `sdi-analyst` | Analista SDI | Avalia sistema de motivação em conflito |

### Camada de Avaliação — Forças
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `strengths-chief` | Líder de forças | Coordena avaliações de forças e talentos |
| `cliftonstrengths-analyst` | Analista CliftonStrengths | Avalia Top 34 talentos Gallup |
| `via-strengths-analyst` | Analista VIA | Avalia 24 forças de caráter |
| `belbin-analyst` | Analista Belbin | Avalia 9 papéis de equipe |
| `kolbe-analyst` | Analista Kolbe | Avalia 4 modos de ação conativa |

### Camada de Orientação e Síntese
| Agente | Papel | Responsabilidade principal |
|--------|-------|--------------------------|
| `career-fit-analyst` | Analista de carreira | Avalia fit vocacional e direcionamento |
| `riasec-strong-analyst` | Analista RIASEC/Strong | Avalia interesses vocacionais |
| `development-planner` | Planejador de desenvolvimento | Cria planos de desenvolvimento individual |
| `contradiction-auditor` | Auditor de contradições | Identifica e classifica contradições entre frameworks |
| `synthesis-architect` | Arquiteto de síntese | Integra dados em perfil coerente e narrativa |
| `rapport-architect` | Arquiteto de rapport | Garante tom empático e construtivo |
| `respondent-quality-auditor` | Auditor de qualidade | Valida qualidade das respostas do respondente |
| `report-writer` | Escritor de relatórios | Gera relatórios executivos e aprofundados |

> Para descrições completas de cada agente (instruções, ferramentas, interações),
> consulte os arquivos individuais em `agents/`.

## Referências
- `docs/workflow-guide.md` — Como os agentes interagem nos fluxos
- `docs/confidence-scoring-guide.md` — Sistema de confiança
- `agents/` — Definições completas de cada agente
