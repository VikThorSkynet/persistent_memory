# Passagem de trabalho — destino do merge

- Tarefa: t-kit-inicial.
- Data: 16/10/2026, America/Sao_Paulo.
- Branch: feat/kit-inicial, sem commit inicial.

## Alteração

O usuário pediu guardar o link do repositório ao tratar um merge e perguntar o destino se não existir. Configuração, modelo, skill, README, arquitetura e roteiro de aceitação foram atualizados. A [D-003](../decisoes/d-003-repositorio-do-merge.md) registra a escolha. A versão atual é 0.2.1.

O repositório deste kit já foi informado pelo usuário e está salvo. O modelo para outros projetos usa null. Configurações antigas sem o campo continuam interpretadas como destino desconhecido.

Pedido seguinte: facilitar a instalação pelo link. O início do README agora contém um bloco pronto para copiar e colar no agente, autorizando baixar o kit em pasta separada e instalar no projeto atual, preservando sua memória e histórico. Se o destino não estiver claro, o agente pergunta. A publicação continua pendente; o README distingue uso local do uso futuro pelo link remoto.

## Verificação e publicação

Conferidos 28 arquivos e 43 links locais, configurações, metadados e conteúdo do ZIP arquivo a arquivo. Confirmado null no modelo e link conhecido na configuração deste projeto. A skill passou na validação de formato. O roteiro cobre destino ausente, armazenamento, reutilização e divergências, sem exigir merge real; esse comportamento ainda não foi testado em conversa nova. Não houve commit, push ou merge. Próximo passo: teste do usuário com os agentes.
