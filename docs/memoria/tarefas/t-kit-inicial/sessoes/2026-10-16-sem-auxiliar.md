# Passagem de trabalho — kit mantido pelo agente

- Tarefa: t-kit-inicial.
- Data: 16/10/2026, America/Sao_Paulo.
- Agente: Codex.
- Branch local: feat/kit-inicial, ainda sem commit inicial.

## Pedido e resultado

O usuário pediu retirar o Python do projeto e deixar instalação e manutenção para Codex/Claude Code, com transporte pelo Git. A [D-002](../decisoes/d-002-manutencao-pelo-agente.md) registra a substituição da proposta anterior.

Foram removidos o programa auxiliar, seus testes, manifesto e configuração exclusiva. README, skill, arquitetura, formatos e roteiro de aceitação foram atualizados para operações diretas do agente. A versão é 0.2.0.

## Verificações

Conferidos 26 arquivos, 39 links locais, as duas configurações e os metadados das tarefas. O ZIP foi comparado arquivo a arquivo com o projeto e não contém programa nem caches antigos. A skill canônica passou na verificação de formato pela ferramenta externa de autoria; essa ferramenta não integra o kit. Os testes históricos da versão anterior não são validação desta revisão. Não houve execução de teste de retomada em conversas novas dos agentes.

## Próximo passo e publicação

Entregar o pacote atualizado e seguir o roteiro local com o usuário. Sem commit, push ou merge. A autorização atual cobre a mudança local solicitada, sem publicar no GitHub.
