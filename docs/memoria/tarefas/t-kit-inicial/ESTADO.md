# Estado da primeira versão do kit

Identidade e branch de origem: [tarefa.json](tarefa.json). Integrada na main em 16/10/2026, America/Sao_Paulo.

## Objetivo e etapa atual

Entregar kit de memória apenas em arquivos, instalado e mantido pelo agente. A v0.2.1 inclui o link persistente do repositório e a pergunta obrigatória quando um pedido de merge estiver sem destino conhecido. Publicada e integrada na main por autorização explícita do usuário. Teste de retomada nos agentes ainda pendente.

## Arquivos relevantes

- Skill canônica, adaptador Claude e modelos dentro das pastas de skills.
- [README](../../../../README.md), [arquitetura](../../../ARQUITETURA.md) e [roteiro local](../../../TESTE_LOCAL.md).
- A própria memória de desenvolvimento; outros projetos recebem os modelos, não estes registros.

## Decisões e histórico

[D-001: desenho inicial](decisoes/d-001-estrutura-e-fluxo.md). [D-002: manutenção pelo agente](decisoes/d-002-manutencao-pelo-agente.md) substitui a escolha do auxiliar. [Sessão inicial](sessoes/2026-10-16-inicial.md) é histórica. [Remoção do auxiliar](sessoes/2026-10-16-sem-auxiliar.md) registra a etapa anterior.

[D-003: repositório do merge](decisoes/d-003-repositorio-do-merge.md) e [passagem atual](sessoes/2026-10-16-repositorio-merge.md) registram a v0.2.1. O link deste projeto já está salvo; outros projetos recebem o campo como null.

## Validação

V0.2.1: 28 arquivos e 43 links locais conferidos, configurações e metadados válidos. Confirmado campo null no modelo e endereço informado salvo na configuração deste projeto. Skill aprovada na validação de formato e conteúdo do ZIP comparado arquivo a arquivo. O comportamento de perguntar/reutilizar ainda requer teste em conversa real, conforme o roteiro.

Conferência da v0.2.0: 26 arquivos e 39 links locais verificados, configurações e metadados de tarefas válidos, pacote conferido arquivo a arquivo. Nenhum programa ou cache antigo permanece no projeto. A skill canônica passou na validação de formato pela ferramenta externa de autoria. Os testes do auxiliar antigo não validam esta revisão e foram removidos junto com ele. Não há suíte executável própria do kit; a aceitação segue o roteiro local.

Teste real em novas conversas do Codex e Claude Code: pendente do usuário.

## Publicação e próximo passo

Pedido atual do usuário: fazer o merge. O repositório foi confirmado pelo link salvo. Como estava vazio, a entrega foi publicada inicialmente na main, com o commit `fda4657466359a2906eeef4720a2ec8afbb1478d` confirmado no remoto. Não houve PR nem merge entre histórias existentes. Consulte a [passagem da publicação](sessoes/2026-10-16-publicacao-main.md). Próximo passo: teste de retomada e eventuais ajustes em uma nova tarefa; a autorização desta entrega não autoriza novas publicações por conta própria.
