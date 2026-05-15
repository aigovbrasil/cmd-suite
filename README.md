# Workflow: Cmd Suite - Orquestração e Refatoração de Comandos

## Objetivo
Oferecer um conjunto de skills CMD (Command) específicas para orquestração e refatoração, incluindo estratégias adversariais. Visa automatizar tarefas complexas e otimizar a execução de processos baseados em comandos.

## ICP (Ideal Customer Profile)
Engenheiros de automação, desenvolvedores, pesquisadores de IA, especialistas em segurança.

## Fases do Workflow

### Fase 1: Definição do Comando/Processo (What)
*   **O Quê:** Identificação do comando ou sequência de comandos a ser automatizada ou otimizada.
*   **Como:** Interação com o usuário para entender a lógica, os inputs e os outputs esperados do processo.
*   **Output:** Especificação detalhada do comando ou processo.

### Fase 2: Seleção e Configuração de Skills CMD (How)
*   **O Quê:** Escolha das skills CMD mais adequadas para a tarefa.
*   **Como:** Utiliza skills como `cmd-01-pps.skill.zip` (para processamento paralelo), `cmd-02-mirp.skill.zip` (para refatoração) e `cmd-03-maro.skill.zip` (para orquestração multiagente de comandos).
*   **Output:** Configuração das skills CMD e seus parâmetros.

### Fase 3: Execução e Monitoramento (Where)
*   **O Quê:** Execução dos comandos ou processos automatizados e monitoramento de seu desempenho.
*   **Como:** As skills CMD são orquestradas para executar as tarefas, com monitoramento em tempo real para identificar falhas ou desvios. Pode incluir estratégias adversariais (`CMD-06-ADVERSARIAL-v2.md`) para testar a robustez do sistema.
*   **Output:** Logs de execução, resultados dos comandos e relatórios de desempenho.

### Fase 4: Refatoração e Otimização (Why)
*   **O Quê:** Análise dos resultados e refatoração dos comandos ou processos para otimização.
*   **Como:** Utiliza skills de refatoração para melhorar a eficiência, a segurança e a resiliência dos workflows. Pode envolver a atualização de `forge-visual-canvas-v2.0.0 2.zip` para visualização de processos.
*   **Output:** Comandos e workflows otimizados e documentados.

## Skills Envolvidas (Exemplos)
*   `cmd-01-pps.skill.zip`
*   `cmd-02-mirp.skill.zip`
*   `cmd-03-maro.skill.zip`
*   `CMD-06-ADVERSARIAL-v2.md` (documento de estratégia)
*   `forge-visual-canvas-v2.0.0 2.zip` (ferramenta de visualização)

## Pontos de Controle
*   Precisão e segurança dos comandos executados.
*   Eficiência e escalabilidade dos processos automatizados.
*   Capacidade de adaptação a cenários adversariais.
*   Documentação clara dos workflows e refatorações.

## Interdependências
*   Pode ser acionado por `X-RAY-AGENTS` para orquestração de tarefas complexas.
*   Pode fornecer inputs para `X-RAY-ANALYTICS` para análise de desempenho de processos.
