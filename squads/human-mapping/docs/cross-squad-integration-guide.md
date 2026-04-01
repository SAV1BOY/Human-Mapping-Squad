# Guia de Integração Cross-Squad

## Visão Geral
Este guia define como o Human Mapping Squad se integra com outros squads do
ecossistema, incluindo formatos de dados, protocolos de comunicação e
acordos de interface para entregas e recebimentos.

## Conteúdo

### Tipos de integração
1. **Envio de perfil**: compartilhar perfil de persona com outro squad
2. **Recebimento de dados**: receber dados comportamentais de outro squad
3. **Consulta**: responder perguntas sobre perfil de uma persona
4. **Colaboração**: trabalho conjunto em projeto que requer mapeamento

### Protocolo de entrega
1. Verificar consentimento do indivíduo para compartilhamento
2. Selecionar nível de detalhe adequado ao propósito
3. Incluir níveis de confiança em todos os dados compartilhados
4. Usar formato padronizado (YAML ou Markdown)
5. Registrar entrega no `cross-squad-deliveries.yaml`
6. Coletar feedback do squad receptor

### Formatos de dados
- **Perfil resumido**: Markdown com sumário e Top 5 insights
- **Perfil estruturado**: YAML com dimensões e scores
- **Consulta pontual**: resposta textual com nível de confiança

### Limites de compartilhamento
- Compartilhar apenas o necessário para o propósito declarado
- Nunca compartilhar dados brutos de instrumentos proprietários
- Anonimizar quando possível em análises agregadas
- Respeitar classificação de confidencialidade do registro

---

## Tabela de Squads Parceiros

| Squad Parceiro | O que enviamos | O que recebemos | Formato | Workflow |
|---------------|---------------|-----------------|---------|----------|
| **Leadership Squad** | Perfil de liderança com HPI/HDS/MVPI, descarriladores, estilo decisório | Contexto organizacional, feedback 360 | YAML estruturado | `13-leadership-profile-flow.md` |
| **Hiring Squad** | Perfil de candidato com fit cultural, riscos, potencial | Descrição do cargo, competências requeridas, cultura do time | Markdown resumido | `14-hiring-assessment-flow.md` |
| **Team Dynamics Squad** | Composição de equipe com Belbin, DISC, estilos complementares | Dados de performance do time, conflitos reportados | YAML estruturado | `15-team-composition-flow.md` |
| **Career Development Squad** | Orientação vocacional com RIASEC, forças, motivações | Histórico de carreira, aspirações declaradas | Markdown + YAML | `16-career-guidance-flow.md` |
| **Coaching Squad** | Perfil aprofundado com plano de desenvolvimento individual | Progresso do coachee, feedback de sessões | Markdown narrativo | `12-development-plan-generation.md` |
| **Culture & Values Squad** | Dados agregados de motivações e valores (anonimizados) | Mapeamento de cultura organizacional, valores declarados | YAML agregado | `17-cross-squad-handoff-flow.md` |
| **Analytics Squad** | Metadados de confiança e metodologia para calibração | Benchmarks estatísticos, normas populacionais | YAML técnico | `18-methodology-calibration-flow.md` |

### Contratos de Interface
Cada integração tem um contrato registrado em `data/registries/cross-squad-deliveries.yaml`
que especifica:
- **Campos obrigatórios**: quais dados devem estar presentes na entrega
- **Nível de confiança mínimo**: dados abaixo deste threshold não são compartilhados
- **Consentimento**: tipo de consentimento necessário (explícito, implícito por contrato)
- **SLA**: prazo máximo para entrega após solicitação
- **Formato**: YAML estruturado, Markdown narrativo ou ambos

> **Regra crítica**: antes de qualquer compartilhamento cross-squad, verificar se o
> consentimento do respondente cobre o propósito específico da entrega. Em caso de
> dúvida, solicitar consentimento adicional.

## Referências
- `data/registries/cross-squad-deliveries.yaml` — Registro de entregas
- `docs/ethical-use-policy.md` — Política de uso ético
- `docs/naming-conventions.md` — Convenções de nomenclatura
- `workflows/17-cross-squad-handoff-flow.md` — Fluxo de handoff
