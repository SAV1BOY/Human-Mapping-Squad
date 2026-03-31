---
type: workflow
squad: human-mapping
version: "2.0.0"
trigger: "Necessidade de entregar dados ou resultados para outros squads"
agents: [chief, synthesis-architect]
quality_gates: [format-validation-checklist, data-privacy-checklist, handoff-confirmation-checklist]
---

# Workflow: Handoff Cross-Squad

## Trigger

Ativado quando resultados do human-mapping squad precisam ser compartilhados com outros squads do ecossistema. Pode ser acionado por qualquer workflow posterior ao 09.

## Pre-condicoes

- Pelo menos o relatorio executivo (workflow 10) finalizado.
- Identificacao do squad destinatario e ponto de contato.
- Consentimento do respondente para compartilhamento externo.

## Sequencia

### Passo 1: Identificar Necessidade de Handoff
- **Agente:** chief
- **Acao:** Determina o que precisa ser entregue e para quem:
  - **Qual squad destino?** Identificar pelo nome e funcao.
  - **Que dados sao necessarios?** Nem todos os dados do mapeamento sao relevantes para todos os squads.
  - **Que nivel de detalhe?** Executivo (resumo), operacional (dados processados), ou bruto (scores).
  - **Qual o proposito?** Para que o squad destino vai usar os dados.
  - **Prazo?** Urgencia da entrega.
- **Decisao:** Se proposito nao e claro, solicitar esclarecimento antes de formatar.
- **Output:** `handoff_request{}` com destino, dados, nivel, proposito, prazo.

### Passo 2: Formatar Dados para Entrega
- **Agente:** synthesis-architect
- **Acao:** Prepara pacote de dados no formato adequado:
  - **Formato padrao de handoff:**
    - Cabecalho: session_id, data, squad_origem, squad_destino, classificacao.
    - Resumo executivo do perfil (max 200 palavras).
    - Dados especificos solicitados em formato JSON estruturado.
    - Mapa de confianca relevante para os dados entregues.
    - Limitacoes e ressalvas explicitas.
    - Recomendacoes de uso dos dados.
    - Validade: data de expiracao dos dados (sugestao: 6 meses).
  - **Remover dados nao solicitados.** Principio do menor privilegio.
  - **Anonimizar se necessario** (caso o squad destino nao precise identificar o individuo).
- **Output:** `pacote_handoff{}` formatado.

### Passo 3: Validar Conteudo
- **Agente:** chief
- **Acao:** Revisa pacote de handoff contra criterios de qualidade:
  - Dados sao precisos e refletem mapa unificado.
  - Confianca esta representada honestamente.
  - Nenhuma informacao sensivel incluida sem necessidade.
  - Formato esta aderente ao protocolo inter-squads.
  - Linguagem e clara para audiencia externa (sem jargoes internos do squad).
  - Recomendacoes de uso sao praticas e realistas.
- **Decisao:** Se falhar em qualquer criterio, devolver para synthesis-architect corrigir.
- **Output:** `validacao_handoff` (aprovado | ajustar), `correcoes_necessarias[]`.

### Passo 4: Executar Handoff
- **Agente:** chief
- **Acao:** Envia pacote ao squad destino seguindo protocolo:
  - Notificacao formal ao ponto de contato do squad destino.
  - Envio do `pacote_handoff{}` pelo canal oficial.
  - Registro do envio no log da sessao com timestamp.
  - Solicitacao de ACK (confirmacao de recebimento).
  - Timeout para ACK: 24 horas. Apos isso, retry + escalacao.
- **Output:** `handoff_enviado`, `timestamp_envio`, `ack_solicitado`.

### Passo 5: Confirmar Recebimento
- **Agente:** chief
- **Acao:** Aguarda e processa confirmacao de recebimento:
  - **ACK recebido:** Registrar como handoff concluido. Verificar se destinatario tem duvidas.
  - **ACK parcial:** Destinatario recebeu mas precisa de esclarecimentos. Responder.
  - **NACK:** Destinatario rejeita o pacote. Investigar motivo e corrigir.
  - **Timeout (24h sem resposta):** Reenviar + notificar chief do squad destino.
- **Decisao:**
  - ACK → finalizar.
  - ACK parcial → fornecer esclarecimentos e aguardar novo ACK.
  - NACK → retornar ao Passo 2 com feedback do destinatario.
  - Timeout → escalar para lideranca inter-squads.
- **Output:** `status_confirmacao` (ack | ack_parcial | nack | timeout).

### Passo 6: Registrar Handoff
- **Agente:** chief
- **Acao:** Cria registro permanente do handoff:
  - Session_id, squad destino, dados entregues (resumo, nao conteudo completo).
  - Timestamp de envio e confirmacao.
  - Proposito declarado do uso.
  - Validade dos dados.
  - Status final.
  - Consentimento do respondente referenciado.
- **Output:** `registro_handoff{}` no log permanente do squad.

## Quality Gates (checkpoints)

- [ ] Consentimento do respondente para compartilhamento registrado.
- [ ] Dados formatados conforme protocolo padrao inter-squads.
- [ ] Principio do menor privilegio aplicado (so envia o necessario).
- [ ] Confianca e limitacoes incluidas no pacote.
- [ ] Validacao do chief aprovada.
- [ ] ACK do squad destino recebido.
- [ ] Registro permanente do handoff criado.

## Outputs Finais

| Output | Formato | Destino |
|--------|---------|---------|
| `pacote_handoff{}` | JSON | Squad destino |
| `registro_handoff{}` | JSON | Log permanente |
| `status_confirmacao` | Enum | Sessao, auditoria |

## Tratamento de Falhas

| Falha | Acao |
|-------|------|
| Squad destino nao reconhecido | Verificar lista de squads ativos. Se inexistente, negar handoff. |
| Respondente nega consentimento | Handoff cancelado. Informar squad destino sem dados pessoais. |
| NACK repetido (3x) | Escalar para lideranca. Possivel incompatibilidade de formato ou expectativas. |
| Dados se tornam invalidos apos handoff | Notificar squad destino sobre atualizacao. Sugerir novo handoff com dados atualizados. |

## Proximo Workflow

Nenhum workflow direto. Handoff encerra a responsabilidade do human-mapping squad sobre aquele pacote de dados.
