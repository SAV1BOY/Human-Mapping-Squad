# Contrato de Handoff — Brand Squad

## Visao Geral

Contrato de troca de dados entre Human-Mapping Squad e Brand Squad.
O foco e fornecer dados de personalidade de fundadores e lideres que
informem a construcao de marca pessoal e posicionamento autentico.

## O que Human-Mapping Entrega

- **Personalidade do fundador/lider**: tracos dominantes, valores centrais
- **Estilo de comunicacao natural**: tom, vocabulario, ritmo, nivel de formalidade
- **Narrativa pessoal**: temas recorrentes, momentos formativos, crencas centrais
- **Contradicoes produtivas**: tensoes internas que geram autenticidade
- **Zona de autenticidade**: limites do que e genuino vs forcado para a marca

## O que Brand Squad Entrega

- **Contexto de arquetipo de marca**: arquetipo atual ou desejado
- **Posicionamento de mercado**: diferenciacao, audiencia-alvo
- **Restricoes de marca**: o que a marca NAO pode ser
- **Historico de comunicacao**: tom usado anteriormente, recepcao do publico

## Formato de Dados

- Formato: JSON conforme schema `founder-personality-brand-v1.json`
- Encoding: UTF-8
- Campos obrigatorios: `profile_id`, `core_traits`, `communication_style`, `confidence_score`
- Campos opcionais: `authenticity_boundaries`, `brand_alignment_score`

## Confianca Minima

- Score minimo de confianca para handoff: **0.5**
- Para construcao de marca pessoal publica, minimo recomendado: **0.7**
- Dados com confianca 0.5-0.7 devem ser validados diretamente com o lider

## Divulgacao de Limitacoes

- Secao `limitations` obrigatoria:
  - Diferenca entre persona publica e personalidade real
  - Risco de amplificacao de tracos para fins de marca
  - Aspectos da personalidade que NAO devem ser explorados publicamente
  - Estabilidade dos tracos ao longo do tempo

## Nivel de Privacidade

- **Nivel 3** — Dados sensiveis de personalidade para uso publico
- Aprovacao explicita do lider para cada uso de dados
- Direito de veto sobre qualquer interpretacao
- Retencao maxima: duracao do projeto de marca + 6 meses

## Referencia de Template de Handoff

- Template: `templates/handoff/brand-handoff-template.json`
- Versao atual: 1.2
- Inclui campo `do_not_use` para tracos que o lider nao quer publicizados

## Loop de Feedback

- Brand Squad reporta como dados de personalidade foram usados
- Feedback do lider sobre autenticidade do resultado final
- Formato: `feedback/brand-authenticity-feedback.json`
- Metricas: autenticidade percebida (1-5), conforto do lider (1-5)
- Revisao a cada campanha ou reposicionamento de marca
