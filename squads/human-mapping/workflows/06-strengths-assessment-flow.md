---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Conclusao do 05-motivation-assessment-flow"
agents: [strengths-chief, clifton-analyst, via-analyst, belbin-analyst]
quality_gates: [strength-vs-skill-checklist, strengths-convergence-checklist]
---

# Workflow: Assessment de Forcas e Talentos

## Trigger

Recebe handoff do `05-motivation-assessment-flow.md` apos conclusao da camada motivacional.

## Pre-condicoes

- Camadas de tracos, tipos e motivacao concluidas.
- Respondente ainda engajado (verificar tempo de sessao).
- Camada de forcas incluida em `camadas_ativas[]`.

## Sequencia

### Passo 1: Estabelecer Distincao Forca vs Habilidade
- **Agente:** strengths-chief
- **Acao:** Briefing interno reforçando distincoes criticas:
  - **Talento:** Padrao natural de pensamento, sentimento ou comportamento (inato).
  - **Forca:** Talento + investimento (conhecimento + pratica). Desempenho consistente e quase perfeito.
  - **Habilidade (Skill):** Capacidade adquirida por treino. Pode existir sem talento.
  - **Conhecimento:** Fatos e licoes aprendidas. Nao e forca.
  - Alerta: NAO confundir "sou bom em X" (habilidade) com "X me energiza e vem naturalmente" (forca).
- **Output:** `framework_distincao_ativo`, confirmacao de todos os analistas.

### Passo 2: Executar CliftonStrengths (Gallup)
- **Agente:** clifton-analyst
- **Acao:** Identifica os talentos dominantes entre os 34 temas CliftonStrengths, agrupados em 4 dominios:
  - **Execucao:** Realizador, Organizador, Crenca, Consistencia, Deliberativo, Disciplina, Foco, Responsabilidade, Restaurador.
  - **Influencia:** Ativador, Comando, Comunicacao, Competicao, Maximizacao, Autoconfianca, Significancia, Carisma.
  - **Relacionamento:** Adaptabilidade, Conexao, Desenvolvedor, Empatia, Harmonia, Inclusao, Individualizacao, Positividade, Relacional.
  - **Pensamento Estrategico:** Analitico, Contexto, Futurista, Ideacao, Aprendiz, Input, Inteleccao, Estrategico.
- **Decisao:** Priorizar Top 5 talentos. Se profundidade = "Profundo", mapear Top 10 e Bottom 5.
- **Output:** `clifton_top_5[]`, `clifton_top_10[]` (se profundo), `clifton_bottom_5[]` (se profundo), `dominio_dominante`.

### Passo 3: Executar VIA Character Strengths
- **Agente:** via-analyst
- **Acao:** Avalia as 24 forcas de carater agrupadas em 6 virtudes:
  - **Sabedoria:** Criatividade, Curiosidade, Julgamento, Amor por Aprender, Perspectiva.
  - **Coragem:** Bravura, Perseveranca, Honestidade, Vitalidade.
  - **Humanidade:** Amor, Gentileza, Inteligencia Social.
  - **Justica:** Trabalho em Equipe, Equidade, Lideranca.
  - **Temperanca:** Perdao, Humildade, Prudencia, Autorregulacao.
  - **Transcendencia:** Apreciacao da Beleza, Gratidao, Esperanca, Humor, Espiritualidade.
- **Decisao:** Identificar as 5 forcas de assinatura (signature strengths) e cruzar com Clifton.
- **Output:** `via_top_5_assinatura[]`, `via_24_ranking[]`, `virtude_dominante`, `cruzamento_clifton{}`.

### Passo 4: Executar Belbin Team Roles
- **Agente:** belbin-analyst
- **Acao:** Identifica os papeis de equipe preferidos entre os 9 papeis Belbin:
  - **Orientados a Acao:** Shaper, Implementer, Completer-Finisher.
  - **Orientados a Pessoas:** Coordinator, Teamworker, Resource Investigator.
  - **Orientados a Pensamento:** Plant, Monitor Evaluator, Specialist.
- **Decisao:** Identificar papel primario, secundario e papel evitado. Cruzar com DISC e Insights para validacao.
- **Output:** `belbin_primario`, `belbin_secundario`, `belbin_evitado`, `cruzamento_disc_insights{}`.

### Passo 5: Integracao de Forcas
- **Agente:** strengths-chief
- **Acao:** Consolida os tres instrumentos e gera visao integrada:
  - Zonas de genialidade: onde Clifton, VIA e Belbin convergem.
  - Zonas de potencial: talentos identificados mas nao desenvolvidos.
  - Zonas de risco: fraquezas que podem sabotar se ignoradas.
  - Cruzamento com motivacao: forcas que energizam vs forcas que drenam.
  - Mapa de contribuicao ideal para equipe.
- **Decisao:**
  - Se convergencia alta entre instrumentos → alta confianca.
  - Se Belbin diverge de Clifton/VIA → investigar se e efeito do contexto de equipe vs individual.
- **Output:** `mapa_forcas_integrado{}`, `zonas_genialidade[]`, `zonas_potencial[]`, `zonas_risco[]`, `confianca_camada_forcas`.

## Quality Gates (checkpoints)

- [ ] Distincao forca vs habilidade mantida em todos os instrumentos.
- [ ] Clifton Top 5 identificado com confianca.
- [ ] VIA 5 forcas de assinatura identificadas.
- [ ] Belbin com papel primario, secundario e evitado.
- [ ] Zonas de genialidade mapeadas (convergencia de pelo menos 2 instrumentos).
- [ ] Cruzamento com motivacao realizado.
- [ ] Confianca da camada >= 60%.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `clifton_top_5[]` + dominio | JSON | Synthesis, report-writer |
| `via_top_5_assinatura[]` | JSON | Synthesis, development-planner |
| `belbin_primario` + secundario | JSON | Synthesis, team-composition |
| `mapa_forcas_integrado{}` | JSON | Synthesis, contradiction-auditor |
| `zonas_genialidade[]` | Array | Report-writer, development-planner |
| `confianca_camada_forcas` | Float | Chief |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Respondente confunde forca com habilidade | Strengths-chief intervem com exemplos praticos: "Voce faz isso naturalmente ou aprendeu a fazer?" |
| Clifton e VIA divergem completamente | Investigar se respondente respondeu VIA de forma aspiracional (quem quer ser vs quem e). |
| Belbin inconsistente com perfil individual | Normal se contexto de equipe e muito diferente do perfil solo. Documentar como contextual. |
| Fadiga do respondente (muitos instrumentos) | Oferecer pausa. Se recusar, concluir com instrumentos ja realizados e registrar limitacao. |

## Proximo Workflow

`07-career-action-assessment-flow.md`
