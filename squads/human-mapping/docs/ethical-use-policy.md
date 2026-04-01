# Política de Uso Ético

## Visão Geral
Este documento estabelece os princípios e diretrizes éticas que regem todas as
atividades do Human Mapping Squad. Leitura obrigatória para todos os membros
e colaboradores antes de iniciar qualquer operação.

## Conteúdo

### Princípios fundamentais
1. **Consentimento informado**: o indivíduo deve saber que está sendo avaliado,
   quais instrumentos serão utilizados e como os resultados serão usados
2. **Confidencialidade**: dados de perfil são confidenciais por padrão
3. **Não discriminação**: perfis não devem ser usados para discriminar
4. **Transparência**: limitações e níveis de confiança sempre comunicados
5. **Beneficência**: avaliações devem beneficiar o avaliado, não apenas terceiros

### Proibições
- Usar perfis para excluir pessoas de oportunidades sem base legítima
- Compartilhar dados de perfil sem consentimento explícito
- Apresentar proxy-inference como resultado direto de avaliação
- Usar frameworks com viés cultural conhecido sem adaptação
- Rotular pessoas com base em um único instrumento

### Uso responsável em contratação
- Avaliação de personalidade como complemento, nunca como fator único
- Foco em fit para o cargo, não em características pessoais irrelevantes
- Feedback sempre oferecido ao candidato, independente do resultado

### Armazenamento e retenção
- Dados armazenados com controle de acesso
- Retenção máxima de 3 anos sem reavaliação
- Direito do indivíduo de solicitar exclusão de seus dados

---

## 5 Princípios Éticos Detalhados

### 1. Autonomia e Consentimento Informado
O respondente tem direito de saber exatamente o que será avaliado, por quais
instrumentos e quem terá acesso aos resultados. O consentimento deve ser:
- **Específico**: para cada propósito de uso (contratação, desenvolvimento, etc.)
- **Revogável**: o respondente pode retirar consentimento a qualquer momento
- **Documentado**: registrado com data e escopo no intake do projeto

### 2. Minimização de Dados
Coletar e compartilhar apenas os dados estritamente necessários para o propósito
declarado. Não avaliar dimensões irrelevantes ao objetivo. Exemplo: para hiring
assessment, não é necessário mapear motivações profundas (Eneagrama/Reiss) se o
objetivo é apenas fit comportamental.

### 3. Precisão e Transparência
Toda afirmação no relatório deve incluir nível de confiança. Resultados de
proxy-inference devem ser marcados como [proxy]. Limitações metodológicas devem
ser explicitadas na seção de disclaimers do relatório.

### 4. Não-Maleficência
Avaliações não devem causar dano ao avaliado. Isso inclui: não patologizar traços
normais, não rotular pessoas de forma reducionista, não usar resultados para
exclusão arbitrária.

### 5. Justiça e Equidade
Considerar vieses culturais dos instrumentos. Adaptar interpretações para o
contexto cultural do respondente. Não comparar resultados entre culturas sem
normalização adequada.

## Conformidade com a LGPD
- **Base legal**: consentimento explícito do titular (Art. 7, I da LGPD)
- **Direito de acesso**: o respondente pode solicitar cópia de todos os dados
- **Direito de exclusão**: dados devem ser eliminados em até 15 dias após solicitação
- **Encarregado**: toda comunicação sobre dados passa pelo DPO designado
- **Relatório de Impacto**: projetos com dados sensíveis requerem RIPD prévio

## Retenção de Dados
| Tipo de dado | Retenção máxima | Ação após vencimento |
|-------------|----------------|---------------------|
| Dados brutos de instrumentos | 1 ano | Exclusão definitiva |
| Perfil integrado (relatório) | 3 anos | Solicitar renovação de consentimento |
| Dados agregados/anonimizados | Indefinido | Manter para calibração |
| Registros de consentimento | 5 anos | Arquivamento legal |

## Quando Recusar um Assessment
O squad deve recusar ou interromper uma avaliação quando:
1. O respondente não deu consentimento informado
2. O propósito declarado é discriminatório ou punitivo
3. O solicitante quer usar o perfil para demissão sem base legítima
4. Há conflito de interesse não declarado entre solicitante e respondente
5. Os dados disponíveis são insuficientes para atingir confiança mínima (0.50)

## Referências
- Código de Ética do CRP (Conselho Regional de Psicologia)
- APA Ethical Principles of Psychologists
- LGPD (Lei Geral de Proteção de Dados)
- `docs/confidence-scoring-guide.md` — Threshold de confiança mínima
