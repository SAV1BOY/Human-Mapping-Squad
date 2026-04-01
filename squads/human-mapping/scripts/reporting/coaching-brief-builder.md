# Construtor de Brief para Coaching

## Proposito

Gerar um documento estruturado que permita a um coach externo
entender rapidamente o perfil do coachee, sem precisar refazer
todo o assessment. O brief e a ponte entre mapeamento e desenvolvimento.

## Estrutura do Brief

### 1. Contexto (1 paragrafo)
- Quem e a pessoa (cargo, nivel, tempo na funcao)
- Por que esta sendo encaminhada para coaching
- Objetivos organizacionais para o processo de coaching
- Prazo e formato esperado

### 2. Perfil Sintetico (meia pagina)
- Top 3 forcas identificadas no assessment
- Top 2 areas de desenvolvimento prioritarias
- Estilo de comunicacao preferido (DISC simplificado)
- Motivadores centrais (Enneagrama simplificado)
- Nivel de autoconhecimento observado

### 3. Dados de Assessment (referencia)

**Big Five (percentis):**
- Abertura: [score] — implicacao pratica
- Conscienciosidade: [score] — implicacao pratica
- Extroversao: [score] — implicacao pratica
- Amabilidade: [score] — implicacao pratica
- Neuroticismo: [score] — implicacao pratica

**Enneagrama:**
- Tipo central: [tipo] com asa [asa]
- Nivel de saude observado: [nivel]
- Padrao sob estresse: [direcao]

**Kolbe:**
- Modo de operacao dominante: [modo]
- Implicacao para estilo de trabalho

### 4. Dinamicas Observadas
- Padroes comportamentais recorrentes
- Pontos cegos identificados
- Tensoes internas (ex: quer ser visto como forte mas precisa de apoio)
- Temas que geraram maior reatividade na sessao

### 5. Recomendacoes para o Coach

**Abordagem sugerida:**
- Estilo de coaching mais indicado (diretivo vs exploatorio)
- Temas a priorizar nas primeiras sessoes
- Potenciais resistencias e como lidar
- Linguagem que ressoa vs linguagem que aliena

**Cuidados:**
- Sensibilidades identificadas
- Topicos que requerem delicadeza
- Historico relevante (se autorizado pelo coachee)

### 6. Metricas de Sucesso
- Como medir progresso no coaching
- Indicadores comportamentais observaveis
- Timeline sugerida para reavaliacao

## Processo de Geracao

1. Consolidar dados de todas as fontes de assessment
2. Sintetizar em linguagem acessivel para coaches
3. Revisar com o coachee antes de compartilhar (consentimento)
4. Enviar ao coach com briefing contextual
5. Sessao de alinhamento coach-assessor (opcional mas recomendada)

## Consentimento

O brief so pode ser compartilhado com:
- Consentimento explicito do coachee
- Clareza sobre o que sera compartilhado
- Opcao de remover itens sensiveis
- Registro documentado do consentimento

## Especificacao de I/O

### Input
- Formato: YAML/Markdown
- Campos obrigatorios: perfil integrado, contexto do coachee (cargo, nivel, objetivo), consentimento confirmado
- Exemplo: `{profile: {big_five: {...}, enneagram: {type: 3, wing: 2}}, context: {role: "gerente", level: "senior"}, consent: true}`

### Output
- Formato: Markdown formatado (2-3 paginas)
- Campos: contexto, perfil sintetico, dados de assessment, dinamicas observadas, recomendacoes para coach, metricas de sucesso

### Thresholds
- max_strengths_listed: 3
- max_development_areas: 2
- min_confidence_for_sharing: 60
- consent_required: true (bloqueante)

### Tratamento de Erros
- Input invalido: retornar erro `MISSING_PROFILE_DATA`
- Dados insuficientes: gerar brief parcial com disclaimer e flag `limited-data`
- Consentimento ausente: bloquear geracao e retornar `CONSENT_REQUIRED`
