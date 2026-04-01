---
type: component
squad: human-mapping
version: "2.0.0"
---

# Environment Fit Card

## Proposito

O Environment Fit Card descreve o ambiente de trabalho ideal para o respondente, derivado dos dados do mapeamento. Ao inves de descrever quem a pessoa E, descreve ONDE ela funciona melhor — que tipo de estrutura, ritmo, interacao social, autonomia e cultura organizacional maximizam seu desempenho e bem-estar.

Este card e especialmente valioso para decisoes de contratacao, realocacao interna e redesenho de funcoes.

## Estrutura do Card

O card mapeia dimensoes ambientais chave, conectando cada uma aos frameworks que fundamentam a recomendacao.

## Campos Obrigatorios

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `structure_level` | string | Nivel de estrutura ideal: alta (processos claros), media (guidelines flexiveis), baixa (autonomia total) |
| `pace` | string | Ritmo ideal: rapido e dinamico, moderado e previsivel, variavel com periodos de intensidade |
| `social_interaction` | string | Nivel ideal de interacao: alta (equipe constante), moderada (mista), baixa (trabalho individual predominante) |
| `autonomy` | string | Grau de autonomia ideal: alta (autodirecao), moderada (objetivos claros, metodo livre), baixa (instrucoes detalhadas) |
| `challenge_type` | string | Tipo de desafio que engaja: intelectual, interpessoal, operacional, criativo, estrategico |
| `culture_fit` | text | Descricao da cultura organizacional ideal |
| `derived_from` | list | Frameworks e dados que fundamentaram cada recomendacao |

## Campos Opcionais

| Campo | Tipo | Descricao |
|-------|------|-----------|
| `dealbreakers` | list | Condicoes ambientais que provavelmente causarao desengajamento ou saida |
| `growth_environment` | text | Ambiente que desafiaria positivamente a pessoa a crescer |
| `remote_hybrid_onsite` | string | Preferencia e adequacao para trabalho remoto, hibrido ou presencial |
| `leadership_style_needed` | text | Estilo de lideranca do gestor que melhor funciona com este perfil |
| `team_composition_ideal` | text | Caracteristicas ideais dos colegas de equipe |

## Exemplo Preenchido

```yaml
structure_level: "Media — guidelines claros mas liberdade de metodo"
pace: "Moderado com picos de intensidade — nao funciona bem em urgencia cronica nem em monotonia"
social_interaction: "Moderada — misto de trabalho individual profundo e colaboracao em pequenos grupos"
autonomy: "Alta — funciona melhor com objetivos claros e liberdade total de como alcancar"
challenge_type: "Intelectual e estrategico — problemas complexos que demandam analise e criatividade"
culture_fit: >
  Cultura que valoriza profundidade sobre velocidade, qualidade sobre quantidade,
  e competencia tecnica sobre politica. Baixa tolerancia a ambientes de alta
  politicagem ou onde aparencia importa mais que resultado. Funciona bem em
  organizacoes com meritocracia genuina e espaco para trabalho focado.
derived_from:
  - "Big Five Extroversao baixa + Abertura alta → interacao moderada + desafio intelectual"
  - "Kolbe Fact Finder alto + Follow Thru alto → precisa de profundidade e sistematizacao"
  - "Birkman necessidade de autonomia percentil 82 → alta autonomia"
  - "RIASEC Investigative → desafios analiticos e complexos"
  - "SDI Green → ambiente que valoriza competencia e logica"
dealbreakers:
  - "Open office sem espaco para foco — introvertido precisa de controle sobre estimulos"
  - "Microgerenciamento — necessidade alta de autonomia gera conflito com gestao controladora"
  - "Reunioes excessivas sem pauta clara — Kolbe Fact Finder alto precisa de proposito definido"
remote_hybrid_onsite: >
  Hibrido ideal: 2-3 dias remoto para deep work, 2-3 dias presencial para
  colaboracao e alinhamento. Trabalho 100% presencial em open office seria
  especialmente desgastante para este perfil.
leadership_style_needed: >
  Gestor que define o "o que" e confia no "como". Estilo coaching ou
  delegador. Evitar gestor diretivo ou controlador — gerara resistencia
  passiva e desengajamento progressivo.
team_composition_ideal: >
  Equipe com pelo menos 1 colega de nivel intelectual similar para
  trocas profundas. Evitar equipes onde o respondente e significativamente
  mais analitico que todos — gera isolamento e frustracao.
```

## Regras de Preenchimento

1. Cada campo deve ser fundamentado em dados — `derived_from` deve ser rastreavel.
2. Descrever o ambiente ideal em termos concretos e observaveis, nao em abstracoes.
3. Os `dealbreakers` sao tao importantes quanto as preferencias — incluir sempre.
4. Diferenciar entre o que a pessoa PREFERE e o que ela PRECISA — Birkman e util para isso.
5. Considerar o contexto cultural brasileiro ao descrever culture fit.
6. O `growth_environment` deve ser levemente desafiador, nao completamente oposto ao ideal.
7. Este card deve ser cruzado com os dados reais do ambiente atual para identificar gaps de fit.
8. Atualizar quando dados de reassessment indicarem mudanca de necessidades.
