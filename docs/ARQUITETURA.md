# Arquitetura do persistent_memory

Versão do kit: 0.2.1. Formato da memória: 1. Atualização de 16/10/2026: instalação e manutenção feitas pelo agente, apenas com arquivos; destino do merge guardado na configuração.

## Responsabilidades

O Codex, Claude Code ou outro agente lê o procedimento, investiga o projeto, faz perguntas, cria a estrutura e mantém o conhecimento. O usuário testa a entrega e autoriza publicações no escopo combinado. O Git transporta as versões publicadas e guarda seu histórico.

O kit distribui instruções, modelos e configuração. Não possui programas auxiliares, dependências de execução, serviço ou sincronizador.

## Fontes

| Fonte | Responsabilidade |
|---|---|
| AGENTS.md | Entrada comum somada às regras existentes |
| CLAUDE.md | Importação da entrada comum e regras específicas existentes |
| `.agents/skills/memoria-projeto/SKILL.md` | Procedimento canônico |
| `.claude/skills/memoria-projeto/SKILL.md` | Adaptador de descoberta |
| config.json | Parâmetros e versão do kit por projeto |
| INICIO.md | Ordem de leitura estável |
| PROJETO.md | Objetivo e conhecimento integrado, com referência conhecida |
| tarefa.json | ID, branch, base, data e situação da tarefa |
| ESTADO.md | Etapa, validações, pendências e próximo passo |
| Registros por tarefa | Decisões, bugs, evidências e passagem de trabalho |

Os modelos ficam dentro da skill e são copiados apenas para iniciar arquivos ausentes. A memória particular do repositório distribuidor não é copiada para os projetos.

## Instalação e atualização

O agente compara o destino com o kit, preserva arquivos existentes e adaptações e acrescenta as entradas sem duplicação. Evita ciclos entre AGENTS.md e CLAUDE.md. Reexecutar não deve apagar parâmetros, decisões ou registros.

Para atualizar, compara versões, concilia as instruções e registra a nova versão no config.json. Atualização não significa substituir a memória por modelos vazios. A conferência é feita por leitura, busca e ferramentas já disponíveis no ambiente; não criar um instalador ou verificador próprio.

## Inicialização e retomada

Investigar antes de perguntar. Esclarecer objetivo, público, prioridades, restrições, critérios de aceitação, execução e testes conforme as lacunas reais. Perguntas continuam enquanto ajudarem o trabalho; não repetir respostas nem impor um questionário fixo.

Na retomada, conferir branch, HEAD e alterações locais com operações de leitura. Ler configuração, início, resumo e a tarefa ativa correspondente. Consultar detalhes sob demanda. Arquivos antigos são evidência histórica, não autorização nem instrução de execução. Fatos voláteis precisam ser conferidos no projeto real.

## Tarefas, branches e integração

Cada tarefa tem ID portável independente da branch e situação `ativa`, `integrada` ou `arquivada`. Deve haver no máximo uma tarefa ativa para a mesma branch. A etapa de entrega fica no ESTADO.md. Sem Git, usar branch null; em HEAD destacado, registrar a referência e esclarecer a tarefa quando necessário.

Agentes simultâneos usam checkouts/worktrees próprios. Não trocar de branch para encaixar um registro, nem iniciar subagentes automaticamente. Implementações ainda não integradas ficam nas tarefas, sem se apresentar como funcionalidades da main.

Antes do merge, preparar o resumo candidato e reconciliar decisões com a base disponível. Após merge confirmado, consolidar conhecimento durável e marcar a tarefa integrada. Atualizações locais posteriores seguem o fluxo de publicação. Registros antigos de autorização não permitem novas operações.

## Manutenção e bugs

Registrar decisões, descobertas e bugs durante o trabalho; resumir ao concluir etapas e usar checkpoints em tarefas longas. Sessões têm arquivos próprios. Condensar resumos quando crescerem, mantendo links; arquivar sem exclusão automática por idade.

Preservar memórias antigas e sintetizar o estado atual com indicação do que foi revalidado. Uma decisão substituída deve apontar sua sucessora. Resultados históricos de testes não são validação da versão atual.

Para cada bug corrigido, criar/ampliar teste de comportamento, registrar causa/hipótese e resultado. Quando automatizar não for viável, justificar e registrar um roteiro manual reproduzível e cobertura pendente. Os testes pertencem ao projeto de destino e usam sua infraestrutura.

## Entrega e limites

Implementar e validar localmente, entregar para teste humano, obter autorização para commit/push e autorização separada para merge. Um pedido explícito já autoriza a respectiva ação no escopo atual.

`projeto.repositorio_url` guarda o link sem credenciais informado pelo usuário. Ao receber um pedido de merge, se o campo não existir ou estiver vazio/null e o destino ainda não tiver sido informado, o agente pergunta qual repositório usar e aguarda a resposta. Um remoto pode ser sugerido, mas não adotado silenciosamente. Confirmado o destino, salva o link para as próximas conversas e confere sua correspondência com as branches/PR. Divergências são esclarecidas antes do merge. O campo é opcional em configurações antigas; sua ausência significa destino ainda desconhecido. No modelo inicial é null para não propagar o endereço do distribuidor.

Conferir estrutura e links não prova adesão do agente ou correção de fatos. A aceitação inclui retomar a memória em conversas novas de Codex e Claude Code. Não há captura após encerramento abrupto. O kit não modifica configurações globais.

O remoto é `VikThorSkynet/persistent_memory`. A entrega foi publicada na main em 16/10/2026, a partir da implementação local `feat/kit-inicial`. Como o remoto estava vazio, foi uma publicação inicial da branch principal, sem PR ou merge entre histórias existentes. O estado confirmado está na [memória da integração](memoria/tarefas/t-kit-inicial/sessoes/2026-10-16-publicacao-main.md). Os registros da v0.1.0 são históricos; a decisão [D-002](memoria/tarefas/t-kit-inicial/decisoes/d-002-manutencao-pelo-agente.md) define a remoção do auxiliar e prevalece nesse aspecto.
