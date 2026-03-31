# Human-Mapping Squad — Assessment OS

> Mapeamento completo de pessoas por meio de IA multi-camada.
> 34 agentes. 26+ frameworks. Uma visao integrada.

---

## Visao Geral

O **Human-Mapping Squad** e o sistema operacional de assessment dentro do ecossistema MMOS. Seu objetivo e mapear pessoas de forma profunda e multidimensional, cruzando multiplas camadas de analise:

- **Tracos de personalidade** (Big Five, HEXACO, Dark Triad)
- **Tipos e estilos** (MBTI, Eneagrama, DISC, Estilos de Comunicacao)
- **Motivacoes e drives** (SDT, Reiss, McClelland, Ikigai)
- **Forcas e talentos** (CliftonStrengths, VIA, Realizacoes)
- **Papeis em equipe** (Belbin, Papeis Funcionais)
- **Fit de carreira** (Holland/RIASEC, Ancoras de Carreira, Career Drivers)
- **Conacao** (Kolbe, modos de acao natural)

O squad opera com **34 agentes de IA especializados** organizados em camadas, cada um responsavel por uma etapa do pipeline de assessment. O resultado final e um perfil sintetico, com scores de confianca, contradicoes mapeadas e um plano de desenvolvimento acionavel.

---

## Principio Central — O Pipeline

O Assessment OS segue um pipeline rigoroso e sequencial. Cada camada alimenta a proxima.

```
Intake --> Calibracao --> Tracos --> Tipos/Estilos --> Motivacoes --> Forcas
  --> Equipe --> Carreira --> Acao --> Contradicoes --> Sintese --> Relatorio --> Memoria
```

| Etapa | O que acontece |
|---|---|
| **Intake** | Coleta de dados brutos: questionarios, entrevistas, historico |
| **Calibracao** | Ajuste de confianca com base na qualidade dos dados de entrada |
| **Tracos** | Mapeamento dimensional (Big Five, HEXACO, Dark Triad) |
| **Tipos/Estilos** | Classificacao tipologica (MBTI, Eneagrama, DISC) |
| **Motivacoes** | Identificacao de drives internos (SDT, Reiss, McClelland) |
| **Forcas** | Mapeamento de talentos e pontos fortes (Clifton, VIA) |
| **Equipe** | Papeis naturais em times (Belbin, dinamicas de grupo) |
| **Carreira** | Fit profissional e direcao (Holland, Ancoras de Schein) |
| **Acao** | Estilo de conacao e execucao natural (Kolbe) |
| **Contradicoes** | Deteccao de conflitos entre frameworks |
| **Sintese** | Integracao cross-framework com pesos de confianca |
| **Relatorio** | Geracao do perfil final documentado |
| **Memoria** | Persistencia para uso futuro e evolucao longitudinal |

---

## O que Separa Assessment OS de um Teste de Personalidade

| Teste de personalidade convencional | Assessment OS |
|---|---|
| Aplica um unico instrumento | Cruza 26+ frameworks simultaneamente |
| Interpreta sem calibrar | Calibra confianca antes de interpretar |
| Classifica em tipos diretamente | Mapeia tracos dimensionais antes de tipos |
| Ignora contradicoes entre modelos | Detecta e explicita contradicoes cross-framework |
| Entrega um rotulo | Entrega scores de confianca por conclusao |
| Resultado estatico | Plano de desenvolvimento acionavel |
| Sem integracao | Alimenta decisoes de equipe, carreira, lideranca e hiring |

### Diferenciais tecnicos

1. **Calibracao antes de interpretacao** — a qualidade dos dados de entrada e avaliada e ponderada antes de qualquer conclusao
2. **Tracos antes de tipos** — dimensoes continuas precedem categorias discretas, evitando reducao prematura
3. **Deteccao de contradicoes cross-framework** — quando MBTI e Eneagrama divergem, isso e um sinal, nao um erro
4. **Score de confianca por conclusao** — cada afirmacao carrega seu nivel de certeza
5. **Planos de desenvolvimento acionaveis** — o output nao e vaidade, e direcao

---

## Dois Modos de Operacao

O Assessment OS opera em dois modos distintos, dependendo dos dados disponiveis:

### Modo 1 — Instrumento Oficial (Official Instrument Mode)

Quando o usuario fornece resultados de instrumentos formais aplicados (ex.: resultado oficial do CliftonStrengths, teste MBTI certificado, Kolbe A Index).

- Dados de alta confianca
- Calibracao base elevada
- Interpretacao direta dos scores oficiais
- Cross-referencia com demais camadas

### Modo 2 — Inferencia por Proxy (Proxy Inference Mode)

Quando nao ha instrumentos formais. O sistema infere tracos a partir de dados comportamentais observaveis:

- Respostas a perguntas conversacionais
- Historico de decisoes e preferencias
- Narrativas e relatos do usuario
- Comportamento observado em contextos reais

Neste modo, os scores de confianca sao ajustados para baixo e as conclusoes sao apresentadas como hipoteses ponderadas, nao como diagnosticos.

---

## Estrutura do Squad

```
squads/human-mapping/
```

| Diretorio | Descricao |
|---|---|
| `agents/` | Definicoes dos 34 agentes de IA (prompts, parametros, roles) |
| `frameworks/` | Bases teoricas dos 26+ frameworks de assessment |
| `frameworks/traits/` | Big Five, HEXACO, Dark Triad |
| `frameworks/types-styles/` | MBTI, Eneagrama, DISC, Estilos de Comunicacao |
| `frameworks/motivation-drives/` | SDT, Reiss Motivation Profile, McClelland, Ikigai |
| `frameworks/strengths/` | CliftonStrengths, VIA Character Strengths |
| `frameworks/team-roles/` | Belbin Team Roles, Papeis Funcionais |
| `frameworks/career-fit/` | Holland/RIASEC, Ancoras de Carreira de Schein |
| `frameworks/conation/` | Kolbe, modos de acao natural |
| `frameworks/reference-intellectual/` | Frameworks de referencia intelectual complementar |
| `workflows/` | Pipelines de execucao e orquestracao de agentes |
| `templates/` | Templates de relatorios, perfis e planos de desenvolvimento |
| `data/` | Dados de referencia, normas e benchmarks |
| `docs/` | Documentacao tecnica e guias de uso |
| `lib/` | Bibliotecas compartilhadas e utilitarios |
| `scripts/` | Scripts de automacao e processamento |
| `checklists/` | Checklists de qualidade e validacao |
| `reference/` | Material de referencia teorica e academica |
| `authority/` | Fontes de autoridade e fundamentacao cientifica |
| `voice/` | Tom de voz e diretrizes de comunicacao |
| `phrases/` | Banco de frases e vocabulario padronizado |
| `tasks/` | Tarefas e backlog do squad |
| `projects/` | Projetos ativos e historico |
| `swipe/` | Swipe files e referencias de output |
| `swipe-sources/` | Fontes originais dos swipe files |
| `swipe.config/` | Configuracoes de swipe |
| `archive/` | Material arquivado e versoes anteriores |

---

## 34 Agentes — Organizacao por Camada

### Camada: Command (2 agentes)

| Agente | Funcao |
|---|---|
| `command-router` | Recebe comandos do usuario e roteia para o pipeline correto |
| `command-orchestrator` | Orquestra a execucao sequencial e paralela entre camadas |

### Camada: Intake (4 agentes)

| Agente | Funcao |
|---|---|
| `intake-interviewer` | Conduz entrevista estruturada ou conversacional |
| `intake-parser` | Processa e estrutura dados brutos de entrada |
| `intake-validator` | Valida completude e qualidade dos dados coletados |
| `intake-calibrator` | Calcula score de confianca inicial dos dados |

### Camada: Traits (5 agentes)

| Agente | Funcao |
|---|---|
| `traits-bigfive` | Mapeia dimensoes do Big Five (OCEAN) |
| `traits-hexaco` | Mapeia dimensoes do modelo HEXACO |
| `traits-dark` | Avalia tracos da Dark Triad (Narcisismo, Maquiavelismo, Psicopatia) |
| `traits-synthesizer` | Integra resultados dos modelos de tracos |
| `traits-confidence` | Calcula confianca por dimensao de traco |

### Camada: Types & Styles (6 agentes)

| Agente | Funcao |
|---|---|
| `types-mbti` | Mapeia tipo MBTI e funcoes cognitivas |
| `types-enneagram` | Identifica tipo, asa e nivel de saude do Eneagrama |
| `types-disc` | Mapeia perfil DISC e estilo comportamental |
| `types-communication` | Identifica estilo de comunicacao predominante |
| `types-synthesizer` | Integra tipologias e detecta convergencias |
| `types-confidence` | Calcula confianca por classificacao tipologica |

### Camada: Motivation (5 agentes)

| Agente | Funcao |
|---|---|
| `motivation-sdt` | Mapeia necessidades basicas (Autonomia, Competencia, Vinculo) |
| `motivation-reiss` | Identifica perfil dos 16 motivos basicos de Reiss |
| `motivation-mcclelland` | Avalia drives de Realizacao, Poder e Afiliacao |
| `motivation-ikigai` | Mapeia interseccao de paixao, missao, vocacao e profissao |
| `motivation-synthesizer` | Integra drives motivacionais cross-framework |

### Camada: Strengths (4 agentes)

| Agente | Funcao |
|---|---|
| `strengths-clifton` | Mapeia Top Strengths via CliftonStrengths |
| `strengths-via` | Identifica forcas de carater pelo modelo VIA |
| `strengths-achievement` | Analisa padroes de realizacao e alto desempenho |
| `strengths-synthesizer` | Integra forcas e identifica temas dominantes |

### Camada: Career (3 agentes)

| Agente | Funcao |
|---|---|
| `career-holland` | Mapeia perfil RIASEC (Holland) |
| `career-anchors` | Identifica Ancoras de Carreira de Schein |
| `career-synthesizer` | Integra fit de carreira e gera recomendacoes |

### Camada: Integration (4 agentes)

| Agente | Funcao |
|---|---|
| `integration-contradictions` | Detecta e analisa contradicoes cross-framework |
| `integration-synthesizer` | Gera perfil sintetico unificado |
| `integration-reporter` | Produz relatorio final formatado |
| `integration-memory` | Persiste perfil para uso futuro e evolucao |

### Agente extra: Conation (1 agente)

| Agente | Funcao |
|---|---|
| `conation-kolbe` | Mapeia Kolbe A Index e modos de acao instintiva |

---

## Comandos

| Comando | Descricao |
|---|---|
| `/start` | Inicia um novo assessment completo do zero |
| `/resume` | Retoma um assessment em andamento |
| `/fast` | Executa assessment rapido (camadas essenciais) |
| `/deep` | Executa assessment profundo (todas as camadas + validacao extra) |
| `/report` | Gera relatorio do perfil atual |
| `/contradictions` | Exibe analise de contradicoes cross-framework |
| `/development` | Gera plano de desenvolvimento acionavel |
| `/career` | Foco em fit de carreira e direcao profissional |
| `/team` | Analise de papeis em equipe e dinamica de grupo |
| `/leadership` | Perfil de lideranca baseado no mapeamento completo |
| `/hiring` | Gera perfil para contexto de selecao e recrutamento |

### Exemplos de uso

```
/start
> Inicia a entrevista de intake e percorre todo o pipeline

/fast
> Coleta dados minimos e gera perfil com as camadas mais robustas

/contradictions
> Mostra onde MBTI, Eneagrama e Big Five divergem — e o que isso significa

/development
> Gera um plano de 90 dias baseado em forcas, motivacoes e gaps identificados
```

---

## Integracao Cross-Squad

O Human-Mapping Squad alimenta e e alimentado por outros squads do ecossistema MMOS:

| Squad | Integracao |
|---|---|
| **Advisory Squad** | Perfil do cliente informa estilo de consultoria e abordagem de aconselhamento |
| **C-Level Squad** | Mapeamento de lideranca alimenta estrategia de posicionamento executivo |
| **Sales Squad** | Estilo de comunicacao e motivacao do prospect informam abordagem comercial |
| **Brand Squad** | Tracos e valores do fundador informam posicionamento de marca pessoal |
| **Storytelling Squad** | Perfil profundo alimenta narrativa autentica e arcos de transformacao |
| **Movement Squad** | Motivacoes e valores informam alinhamento de causa e construcao de movimento |
| **Data Squad** | Dados estruturados do assessment alimentam analytics e dashboards |

### Fluxo de dados

```
Human-Mapping --> Advisory    (perfil do cliente)
Human-Mapping --> C-Level     (perfil de lideranca)
Human-Mapping --> Sales       (perfil do prospect)
Human-Mapping --> Brand       (DNA de marca pessoal)
Human-Mapping --> Storytelling (materia-prima narrativa)
Human-Mapping --> Movement    (alinhamento de causa)
Human-Mapping <-> Data        (persistencia e analytics)
```

---

## Principios

Os principios abaixo governam todas as decisoes do Assessment OS:

| Principio | Significado |
|---|---|
| `evidence_over_impression` | Dados e evidencias sempre prevalecem sobre impressoes ou intuicoes |
| `confidence_per_conclusion` | Cada conclusao carrega seu proprio score de confianca |
| `traits_before_types` | Dimensoes continuas sao mapeadas antes de categorias discretas |
| `motivation_after_style` | Motivacoes so sao interpretadas apos o estilo comportamental estar mapeado |
| `contradiction_is_signal` | Contradicao entre frameworks e informacao, nao erro |
| `no_single_framework_rules_all` | Nenhum framework isolado tem autoridade absoluta |
| `synthesis_over_labeling` | O objetivo e sintese integrativa, nao rotulacao simplista |
| `actionability_over_vanity` | O output deve gerar acao, nao apenas autoconhecimento superficial |

### Detalhamento

**evidence_over_impression** — O sistema nunca conclui com base em "sensacao" ou vieses cognitivos comuns. Toda afirmacao precisa de lastro em dados coletados, respostas fornecidas ou comportamentos observados.

**confidence_per_conclusion** — Diferente de testes que entregam um resultado binario, aqui cada dimensao e cada classificacao carrega um score de 0 a 1 indicando o nivel de certeza. Scores abaixo de 0.6 sao sinalizados como hipoteses.

**traits_before_types** — Big Five e HEXACO sao mapeados antes de MBTI e Eneagrama. Isso evita o vies de confirmacao que acontece quando voce comeca com uma "caixa" e depois procura evidencias para encaixar a pessoa nela.

**contradiction_is_signal** — Se o Big Five sugere alta Abertura mas o DISC indica perfil S (Estabilidade), isso nao e um bug. E uma informacao valiosa sobre a complexidade da pessoa.

---

## Como Comecar

### Inicio rapido

1. **Acesse o squad** no ambiente MMOS
2. **Execute `/start`** para iniciar um assessment completo
3. **Responda as perguntas** do agente de intake (entrevista conversacional)
4. **Aguarde o processamento** — o pipeline percorre todas as camadas automaticamente
5. **Receba seu relatorio** com perfil sintetico, scores de confianca e plano de acao

### Para assessment rapido

```
/fast
```

Executa apenas as camadas essenciais (Traits + Types + Strengths) e gera um perfil condensado em menos tempo.

### Para assessment profundo

```
/deep
```

Percorre todas as camadas incluindo Conacao, faz validacao cruzada extra e gera o relatorio mais completo possivel.

### Para contextos especificos

```
/career      # Foco em direcao profissional
/team        # Foco em dinamica de equipe
/leadership  # Foco em perfil de lideranca
/hiring      # Foco em selecao e recrutamento
```

---

## Requisitos

- Acesso ao ecossistema MMOS
- Dados de entrada: respostas a entrevista conversacional e/ou resultados de instrumentos oficiais
- Tempo estimado: 15-30 min (modo rapido) | 60-90 min (modo profundo)

---

## Licenca e Uso

Este squad faz parte do ecossistema MMOS e segue as diretrizes de uso definidas no nivel organizacional. Os frameworks referenciados (CliftonStrengths, MBTI, DISC, Kolbe, etc.) sao propriedade de seus respectivos criadores e editoras. O Assessment OS utiliza esses modelos como referencia teorica para integracao e sintese, nao como substituicao dos instrumentos oficiais.

---

> **Human-Mapping Squad** — Porque entender pessoas e a base de tudo.
