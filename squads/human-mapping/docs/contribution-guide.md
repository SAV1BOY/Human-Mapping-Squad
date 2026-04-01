# Guia de Contribuição

## Visão Geral
Este guia orienta como contribuir com novos conteúdos, correções e melhorias
para o repositório do Human Mapping Squad, incluindo padrões de qualidade
e processo de revisão.

## Conteúdo

### O que pode ser contribuído
- Novos resumos de frameworks em `authority/framework-summaries/`
- Novos kits de workshop em `authority/workshop-kits/`
- Melhorias nos templates de projeto em `projects/`
- Atualizações na documentação em `docs/`
- Novas entradas nos registries em `data/registries/`

### Padrões de qualidade
1. Seguir a estrutura de seções definida para cada tipo de arquivo
2. Escrever em português brasileiro (PT-BR)
3. Usar convenções de nomenclatura conforme `naming-conventions.md`
4. Citar fontes e referências quando aplicável
5. Manter arquivos entre 20-50 linhas quando possível
6. Revisar ortografia e coerência antes de submeter

### Processo de contribuição
1. Identificar a necessidade ou melhoria
2. Verificar se já não existe conteúdo similar
3. Criar ou editar o arquivo seguindo os padrões
4. Solicitar revisão de pelo menos um membro do squad
5. Incorporar feedback e finalizar
6. Atualizar referências cruzadas se necessário

### Revisão
- Toda contribuição requer pelo menos uma revisão por par
- Revisão verifica: precisão técnica, aderência ao padrão, clareza
- Contribuições para `authority/` requerem revisão adicional de especialista

---

## Como Adicionar Novos Conteúdos

### Adicionar um novo framework
1. Crie o resumo em `authority/framework-summaries/<nome>-summary.md`
   - Use a estrutura: Visão Geral, Dimensões, Validade, Aplicações, Limitações
   - Siga o padrão dos resumos existentes (ex: `big-five-summary.md`)
2. Registre o framework em `data/registries/framework-registry.yaml`
3. Crie o agente analista em `agents/<nome>-analyst.md` com instruções de avaliação
4. Atualize a tabela em `docs/framework-selection-guide.md`
5. Adicione mapeamentos de proxy-inference se aplicável

### Adicionar um novo padrão ou pattern
1. Documente o padrão em `authority/patterns/` com nome descritivo
2. Inclua: quando usar, como aplicar, exemplos, limitações
3. Referencie nos workflows relevantes em `workflows/`

### Adicionar um novo agente
1. Crie o arquivo em `agents/<nome-do-agente>.md` seguindo o template existente
2. Defina: papel, instruções, ferramentas, interações com outros agentes
3. Atualize a tabela de agentes em `docs/agent-roles-guide.md`
4. Adicione o agente nos workflows onde ele participará

### Convenções de nomenclatura para arquivos
| Tipo de arquivo | Padrão | Exemplo |
|----------------|--------|---------|
| Resumo de framework | `<nome>-summary.md` | `big-five-summary.md` |
| Agente analista | `<nome>-analyst.md` | `disc-analyst.md` |
| Agente chief | `<camada>-chief.md` | `trait-chief.md` |
| Workflow | `NN-<descricao>-flow.md` | `03-trait-assessment-flow.md` |
| Registry | `<nome>-registry.yaml` | `framework-registry.yaml` |
| Guia/doc | `<descricao>-guide.md` | `framework-selection-guide.md` |

### Processo de Pull Request
1. Crie uma branch com nome descritivo: `add/<nome-do-conteudo>`
2. Faça as alterações seguindo os padrões acima
3. Verifique referências cruzadas: todos os links internos funcionam?
4. Solicite revisão de pelo menos 1 membro do squad
5. Para conteúdo em `authority/`: revisão adicional de especialista obrigatória
6. Após aprovação, faça merge e atualize registries afetados

## Referências
- `docs/naming-conventions.md` — Convenções de nomenclatura
- `docs/report-writing-guide.md` — Padrões de escrita
- `docs/agent-roles-guide.md` — Tabela completa de agentes
