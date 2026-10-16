# Contexto integrado do persistent_memory

## Objetivo e público

Kit reutilizável para o usuário colocar memória persistente em seus projetos, com foco em programação e uso por Codex e Claude Code, no terminal e nos aplicativos que abrem o repositório. A memória e a skill devem acompanhar o código no GitHub e permitir retomada em outro computador.

## Base integrada conhecida

O remoto estava vazio em 16/10/2026. Ainda não há versão integrada/publicada na main. A primeira implementação local está na tarefa [t-kit-inicial](tarefas/t-kit-inicial/ESTADO.md), branch `feat/kit-inicial`; não confundir seu estado com uma release disponível no GitHub.

## Requisitos confirmados

- Pasta organizada e uma fonte de procedimento comum aos agentes.
- Registrar decisões e descobertas durante o trabalho e resumir etapas concluídas.
- Bugs com causa, solução e regressão; quando automatizar não for viável, motivo e roteiro manual explícitos.
- Implementações por branch, com checkouts/worktrees separados para agentes simultâneos.
- Entregar para teste humano antes de publicar; commit/push e merge possuem autorizações separadas. Um pedido explícito já autoriza seu próprio escopo.
- Inicializar por investigação e perguntas para obter contexto útil; aproveitar memórias existentes preservando a origem.
- Instalação e manutenção diretamente pelo agente, apenas com arquivos; sem programa auxiliar ou dependência de execução.
- Nome do repositório escolhido: `VikThorSkynet/persistent_memory`; textos em pt-BR.
- Guardar o link do repositório em `projeto.repositorio_url`; ao tratar um merge sem destino conhecido, perguntar e salvar a resposta. Reutilizar nas próximas conversas.

## Fontes e decisões

[README](../../README.md) contém instalação e uso. A [arquitetura](../ARQUITETURA.md) descreve os componentes e limites. A [decisão inicial](tarefas/t-kit-inicial/decisoes/d-001-estrutura-e-fluxo.md) registra a origem; a [D-002](tarefas/t-kit-inicial/decisoes/d-002-manutencao-pelo-agente.md) define a manutenção pelo agente. A [D-003](tarefas/t-kit-inicial/decisoes/d-003-repositorio-do-merge.md) acrescenta o destino persistente do merge na versão atual 0.2.1. As listas de comandos do kit estão vazias porque não há programa próprio para executar.

## Limitações e pendências

A implementação e suas verificações pertencem à branch da tarefa. Teste de retomada em conversas novas do Codex e Claude Code ainda precisa ser realizado pelo usuário. macOS/Linux não foram executados nesta entrega. Nenhuma licença foi atribuída em nome do autor.
