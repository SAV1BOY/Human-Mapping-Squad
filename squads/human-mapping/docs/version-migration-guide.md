# Guia de Migracao entre Versoes

## Filosofia de Versionamento

O Human Mapping Squad evolui continuamente. Este guia ajuda a migrar
entre versoes maiores, preservando dados e adaptando processos.

## Convencao de Versao

- **Major (X.0)**: mudancas estruturais, possiveis breaking changes
- **Minor (x.Y)**: novos recursos, retrocompativeis
- **Patch (x.y.Z)**: correcoes e ajustes menores

## Migracao v1.x → v2.x

### Breaking Changes
- Estrutura de pastas reorganizada
- Formato de perfil unificado (JSON schema v2)
- Frameworks renomeados para consistencia
- Scripts de scoring refatorados

### Passos de Migracao
1. Fazer backup completo do diretorio atual
2. Executar script de migracao de estrutura
3. Converter perfis existentes para novo formato
4. Validar integridade dos dados migrados
5. Atualizar referencias em scripts customizados
6. Testar fluxo completo com caso de teste

### Mapeamento de Arquivos
```
v1: data/profiles/ → v2: data/profiles/
v1: templates/report-v1.md → v2: templates/reports/standard.md
v1: scripts/score.py → v2: scripts/scoring/composite-scorer.md
v1: config.json → v2: config.yaml
```

## Migracao de Dados

### Perfis de Assessment
- Campo `type` renomeado para `framework`
- Scores normalizados para escala 0-100
- Adicionado campo `confidence_level`
- Timestamps convertidos para ISO 8601

### Templates
- Variáveis de template agora usam sintaxe {{variavel}}
- Secoes condicionais suportadas
- Templates antigos funcionam com wrapper de compatibilidade

## Checklist Pre-Migracao

- [ ] Backup completo realizado
- [ ] Versao atual documentada
- [ ] Scripts customizados identificados
- [ ] Integracoes externas mapeadas
- [ ] Janela de migracao comunicada a equipe
- [ ] Plano de rollback definido

## Problemas Comuns

### Perfis nao convertem
- Verificar encoding (UTF-8 obrigatorio)
- Validar JSON/YAML antes da conversao
- Campos opcionais podem estar ausentes — adicionar defaults

### Scripts quebram apos migracao
- Verificar paths relativos vs absolutos
- Atualizar imports e dependencias
- Conferir nomes de funcoes/metodos renomeados

## Suporte

Em caso de problemas na migracao, documentar:
- Versao de origem e destino
- Mensagem de erro completa
- Arquivo/perfil problematico
- Passos para reproduzir
