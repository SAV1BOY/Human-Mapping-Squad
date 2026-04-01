# Convenções de Nomenclatura

## Visão Geral
Este documento define as convenções de nomenclatura para arquivos, registros,
identificadores e termos utilizados pelo Human Mapping Squad, garantindo
consistência e rastreabilidade em todo o ecossistema.

## Conteúdo

### Arquivos
- Nomes em kebab-case (minúsculas com hífen): `meu-arquivo.md`
- Fases de projeto com prefixo numérico: `00-intake.md`, `01-calibration.md`
- Resumos de framework: `<nome>-summary.md`
- Registros YAML: `<nome>-registry.yaml`

### Identificadores de registro
- Persona: `PER-YYYY-NNN` (ex: `PER-2026-001`)
- Projeto: `PRJ-<tipo>-YYYY-NNN` (ex: `PRJ-FPM-2026-001`)
- Insight: `INS-YYYY-NNN` (ex: `INS-2026-015`)
- Contradição: `CON-YYYY-NNN` (ex: `CON-2026-003`)
- Plano de desenvolvimento: `PDI-YYYY-NNN` (ex: `PDI-2026-007`)

### Termos padronizados
| Termo preferido | Evitar |
|----------------|--------|
| Persona | Perfil de pessoa, indivíduo |
| Framework | Ferramenta, teste, instrumento |
| Traço | Característica, atributo |
| Nível de confiança | Certeza, precisão |
| Proxy-inference | Estimativa, chute, dedução |
| Contradição | Erro, inconsistência |

### Estrutura de diretórios
- `authority/` — conteúdo autoritativo e de referência
- `projects/` — templates e guias de projeto
- `data/registries/` — registros operacionais
- `docs/` — documentação e guias

---

## Exemplos: Correto vs Incorreto

### Nomes de arquivos
| Correto | Incorreto | Motivo |
|---------|-----------|--------|
| `big-five-summary.md` | `BigFiveSummary.md` | Usar kebab-case, não CamelCase |
| `big-five-summary.md` | `big_five_summary.md` | Usar hífen, não underscore |
| `03-trait-assessment-flow.md` | `trait-assessment-flow.md` | Workflows precisam de prefixo numérico |
| `confidence-history.yaml` | `confidence-history.json` | Registries são YAML, não JSON |
| `hogan-bright-side-analyst.md` | `hogan-analyst-bright.md` | Framework primeiro, depois especificação |

### Identificadores de registro
| Correto | Incorreto | Motivo |
|---------|-----------|--------|
| `PER-2026-001` | `PER-26-1` | Usar ano com 4 dígitos e número com 3 dígitos |
| `PRJ-FPM-2026-001` | `PRJ-2026-FPM-001` | Tipo de projeto vem antes do ano |
| `CON-2026-003` | `CONTRA-2026-003` | Usar prefixo padronizado de 3 letras |
| `INS-2026-015` | `INSIGHT-15` | Usar formato completo com ano |

### Convenções de diretórios
| Diretório | Conteúdo esperado | Nomenclatura de arquivos |
|-----------|-------------------|------------------------|
| `authority/framework-summaries/` | Resumos de frameworks | `<framework>-summary.md` |
| `authority/workshop-kits/` | Kits de workshop | `<tema>-workshop.md` |
| `authority/models/` | Modelos formais | `<modelo>-model.md` |
| `authority/decision-trees/` | Árvores de decisão | `<tema>-decision-tree.md` |
| `projects/<tipo>/` | Templates de projeto | `NN-<fase>.md` |
| `workflows/` | Fluxos de trabalho | `NN-<descricao>-flow.md` |
| `agents/` | Definições de agentes | `<nome>-analyst.md` ou `<nome>-chief.md` |
| `data/registries/` | Registros operacionais | `<nome>-registry.yaml` |
| `docs/` | Documentação e guias | `<descricao>-guide.md` ou `<descricao>.md` |

> **Dica**: na dúvida sobre o nome de um arquivo, verifique se já existe um arquivo
> similar no mesmo diretório e siga o mesmo padrão.

## Referências
- `docs/glossary.md` — Glossário completo de termos
- `docs/contribution-guide.md` — Como contribuir com novos conteúdos
