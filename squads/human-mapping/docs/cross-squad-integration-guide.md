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

## Referências
- `data/registries/cross-squad-deliveries.yaml` — Registro de entregas
- `docs/ethical-use-policy.md` — Política de uso ético
- `docs/naming-conventions.md` — Convenções de nomenclatura
