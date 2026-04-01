# Visão Geral do Human Mapping Squad

## Visão Geral
O Human Mapping Squad é responsável por mapear, avaliar e sintetizar perfis humanos
utilizando múltiplos frameworks de personalidade, comportamento, motivação e forças.
Nosso objetivo é fornecer perfis integrados, confiáveis e acionáveis.

## Conteúdo

### Missão
Fornecer mapeamentos de persona precisos, éticos e úteis que integrem múltiplos
frameworks de avaliação em perfis coerentes e acionáveis.

### Tipos de projeto
- **Full Persona Mapping**: mapeamento completo em 10 fases
- **Leadership Assessment**: avaliação de liderança em 6 fases
- **Hiring Assessment**: avaliação para contratação em 5 fases
- **Team Composition**: análise de composição de equipe em 5 fases
- **Career Guidance**: orientação de carreira em 5 fases
- **Personal Development**: desenvolvimento pessoal em 5 fases
- **Reassessment**: reavaliação e acompanhamento em 4 fases

### Princípios operacionais
1. **Rigor metodológico**: usar frameworks validados com transparência
2. **Confiança calibrada**: nunca afirmar mais do que os dados suportam
3. **Ética primeiro**: respeitar privacidade e evitar uso indevido
4. **Integração**: combinar frameworks para visão mais completa
5. **Acionabilidade**: perfis devem gerar ações concretas

### Estrutura de dados
- `authority/` — frameworks, resumos e kits de workshop
- `projects/` — templates de projeto por tipo
- `data/registries/` — registros operacionais em YAML
- `docs/` — documentação e guias

---

## Missão do Squad
Fornecer mapeamentos de persona que sejam simultaneamente rigorosos do ponto de
vista psicométrico, éticos no uso dos dados e acionáveis para quem os recebe.
Cada perfil integra múltiplos frameworks para capturar a complexidade real das
pessoas, evitando simplificações reducionistas.

## Os 34 Agentes em Resumo
O squad opera com 34 agentes especializados organizados em camadas:
- **Orquestração (4 agentes)**: `human-mapping-chief`, `intake-orchestrator`,
  `readiness-gatekeeper`, `context-mapper` — coordenam o pipeline e validam dados
- **Traços (7 agentes)**: `trait-chief` + 6 analistas (Big Five, HEXACO, NEO/16PF,
  Hogan Bright, Hogan Dark, Predictive Index) — avaliam dimensões de personalidade
- **Tipos e Estilos (4 agentes)**: `type-style-chief` + 3 analistas (MBTI, DISC,
  Insights/Social Style) — classificam estilos comportamentais
- **Motivações (6 agentes)**: `motivation-chief` + 5 analistas (Eneagrama, MVPI,
  Reiss, FIRO/PCM/Birkman, SDI) — mapeiam motivações e valores
- **Forças (5 agentes)**: `strengths-chief` + 4 analistas (CliftonStrengths, VIA,
  Belbin, Kolbe) — identificam talentos e papéis de equipe
- **Orientação e Síntese (8 agentes)**: career-fit, RIASEC/Strong, development-planner,
  contradiction-auditor, synthesis-architect, rapport-architect,
  respondent-quality-auditor, report-writer — integram e entregam

## Visão Geral do Pipeline
Todo projeto segue um pipeline de 7 etapas: Intake → Calibração → Avaliação
Dimensional → Orientação → Contradições → Síntese → Relatório. Cada etapa tem
gates de qualidade obrigatórios. O pipeline pode ser completo (Full Persona,
2-4 semanas) ou reduzido (Hiring, 1-2 semanas).

## Diferenciais do Squad
1. **Multi-framework por design**: nunca usamos um único instrumento para decisões
2. **Confiança calibrada**: cada afirmação tem nível de confiança explícito (0.0-1.0)
3. **Resolução de contradições**: contradições entre frameworks são oportunidades
   de insight, não erros a serem eliminados
4. **Proxy-inference transparente**: quando usamos inferência indireta, documentamos
   e ajustamos a confiança
5. **Ética integrada**: consentimento, LGPD e não-discriminação em cada etapa

## Referências
- `docs/agent-roles-guide.md` — Papéis dos agentes (tabela completa)
- `docs/workflow-guide.md` — Fluxos de trabalho (22 workflows)
- `docs/ethical-use-policy.md` — Política de uso ético
- `docs/getting-started.md` — Primeiros passos
