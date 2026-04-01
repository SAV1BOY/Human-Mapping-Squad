---
type: task
squad: human-mapping
version: "2.0.0"
agent: session-manager
workflow: intake-workflow
---

# Task: Mapear Contexto do Respondente

## Objetivo

Mapear o contexto completo do respondente, identificando se a análise é pessoal, profissional, de liderança, contratação ou equipe, para direcionar as perguntas e interpretações corretamente.

## Pré-condições

- Profundidade da análise selecionada (`select-depth.md` concluída)
- Objetivo e modo definidos no session record
- Respondente disponível para interação

## Passos

1. Identificar o contexto primário da análise:
   - **Pessoal**: Autoconhecimento, desenvolvimento individual
   - **Profissional**: Carreira, desempenho no trabalho atual
   - **Liderança**: Estilo de liderança, gestão de equipe
   - **Contratação**: Avaliação para vaga específica
   - **Equipe**: Dinâmica de time, complementaridade
2. Coletar informações contextuais relevantes:
   - Área de atuação / indústria
   - Nível hierárquico (júnior, pleno, sênior, gestão, executivo)
   - Tempo de experiência na função atual
   - Tamanho da equipe (se aplicável)
3. Para contexto de contratação, capturar adicionalmente:
   - Descrição da vaga ou papel pretendido
   - Competências-chave requeridas
   - Cultura da empresa/equipe
4. Para contexto de equipe, capturar:
   - Composição atual da equipe
   - Gaps identificados pelo líder
   - Objetivos do time
5. Registrar todos os dados contextuais no session record
6. Selecionar o template de interpretação adequado ao contexto
7. Ajustar frameworks prioritários conforme contexto (ex: Belbin para equipe, RIASEC para carreira)
8. Finalizar intake e preparar handoff para calibração

## Outputs

- `context-map`: Mapa completo do contexto do respondente
- `interpretation-template`: Template selecionado para interpretação
- `framework-priorities`: Frameworks priorizados por contexto
- `intake-summary`: Resumo consolidado de todo o intake

## Checklist de Conclusão

- [ ] Contexto primário identificado
- [ ] Informações contextuais coletadas
- [ ] Dados adicionais capturados (se contratação/equipe)
- [ ] Template de interpretação selecionado
- [ ] Frameworks priorizados conforme contexto
- [ ] Session record atualizado com mapa de contexto
- [ ] Intake summary gerado

## Próxima Task

`tasks/calibration/calibrate-respondent.md` — Calibrar respondente

## Subtask Breakdown
1. **Identificar contexto primário** — Agente: `session-manager`. Input: respostas do usuário. Output: tipo de contexto selecionado. Gate: contexto pertence às 5 categorias válidas.
2. **Coletar dados contextuais** — Agente: `session-manager`. Input: perguntas contextuais. Output: área, nível, experiência, equipe. Gate: campos obrigatórios preenchidos.
3. **Coletar dados específicos** — Agente: `session-manager`. Input: tipo de contexto. Output: dados de contratação ou equipe (se aplicável). Gate: dados mínimos para o contexto.
4. **Selecionar template e frameworks** — Agente: `session-manager`. Input: `context-map`. Output: `interpretation-template` + `framework-priorities`. Gate: template existe e frameworks priorizados.
5. **Gerar intake summary** — Agente: `session-manager`. Input: todos os dados de intake. Output: `intake-summary`. Gate: resumo cobre objetivo + profundidade + contexto.

## Quality Gate
- [ ] `context-map` completo no session record
- [ ] Template de interpretação válido selecionado
- Threshold: >= 3 campos contextuais preenchidos
- Se FAIL: prosseguir com template genérico e flag de cautela

## Rework Trigger
- Contexto ambíguo entre 2 categorias → retornar ao passo 1 com perguntas de desempate
- Dados insuficientes para contratação/equipe → retornar ao passo 3
