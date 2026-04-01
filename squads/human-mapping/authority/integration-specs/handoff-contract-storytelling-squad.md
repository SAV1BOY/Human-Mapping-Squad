# Contrato de Handoff — Storytelling Squad

## Visao Geral

Contrato de troca de dados entre Human-Mapping Squad e Storytelling Squad.
O objetivo e fornecer insights de personalidade que enriquecam narrativas
autenticadas e historias com profundidade psicologica real.

## O que Human-Mapping Entrega

- **Insights de personalidade para narrativa**: tracos que geram historias interessantes
- **Arcos de transformacao**: como a pessoa mudou ao longo do tempo
- **Tensoes internas produtivas**: contradicoes que criam profundidade narrativa
- **Momentos definidores**: experiencias que moldaram a personalidade atual
- **Metaforas naturais**: como a pessoa descreve a si mesma e seu mundo

## O que Storytelling Squad Entrega

- **Preferencias narrativas**: formato, tom, audiencia-alvo da historia
- **Contexto de uso**: onde e como a narrativa sera publicada
- **Restricoes editoriais**: temas sensiveis, limites de exposicao
- **Feedback de audiencia**: como narrativas anteriores foram recebidas

## Formato de Dados

- Formato: JSON conforme schema `personality-narrative-v2.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `narrative_themes`, `confidence_score`
- Campos opcionais: `transformation_arc`, `defining_moments`, `natural_metaphors`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Narrativas publicaveis requerem confianca minima de **0.65**
- Insights com confianca abaixo de 0.5 podem ser usados como "hipotese criativa"

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria:
  - Risco de romantizacao ou dramatizacao excessiva
  - Aspectos que a pessoa NAO autorizou para narrativa publica
  - Diferenca entre historia contada e historia vivida
  - Vieses do avaliador na selecao de momentos definidores

## Nivel de Privacidade

- **Nivel 3** — Dados pessoais para uso narrativo publico
- Consentimento especifico para cada narrativa construida
- Direito de revisao antes de publicacao
- Retencao: duracao do projeto narrativo + 12 meses

## Referencia de Template de Handoff

- Template: `templates/handoff/storytelling-handoff-template.json`
- Versao atual: 2.0
- Inclui campo `narrative_boundaries` para limites de exposicao

## Loop de Feedback

- Storytelling Squad reporta como insights foram incorporados na narrativa
- Validacao do protagonista sobre fidelidade da historia
- Formato: `feedback/storytelling-fidelity-feedback.json`
- Metricas: fidelidade narrativa (1-5), impacto emocional, engajamento
- Revisao por projeto, com retrospectiva ao final de cada narrativa
