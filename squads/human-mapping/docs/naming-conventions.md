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

## Referências
- `docs/glossary.md` — Glossário completo de termos
- `docs/contribution-guide.md` — Como contribuir com novos conteúdos
