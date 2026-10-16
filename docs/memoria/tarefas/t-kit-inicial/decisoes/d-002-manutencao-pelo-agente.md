# D-002 — Instalação e manutenção diretamente pelo agente

- Tarefa: t-kit-inicial.
- Data: 16/10/2026, America/Sao_Paulo.
- Situação: confirmada.
- Origem: pedido explícito do usuário para retirar o Python do projeto.
- Substitui: a parte de [D-001](d-001-estrutura-e-fluxo.md) que previa auxiliar opcional.

## Escolha e motivo

Distribuir apenas instruções, modelos e configuração. O próprio Codex ou Claude Code cria pastas, lê a memória, faz perguntas e mantém registros seguindo a skill. O Git transporta código e memória publicados para outro computador.

## Consequências

Remover o script, os testes exclusivos dele e o manifesto de hashes da instalação. Retirar seus comandos da documentação e configuração. A conferência de estrutura, links, branches e preservação passa a ser responsabilidade do agente, usando ferramentas já disponíveis no ambiente.

Não substituir o programa por outro instalador ou verificador. Permanecem o protocolo por tarefa/branch, os testes de regressão dos projetos de destino e as aprovações separadas para publicação e merge.

## Versão

O kit passa a 0.2.0; o formato da memória continua 1. A [arquitetura atual](../../../../ARQUITETURA.md) descreve o funcionamento. O histórico anterior fica identificado como substituído para evitar que outro agente reintroduza o auxiliar.
