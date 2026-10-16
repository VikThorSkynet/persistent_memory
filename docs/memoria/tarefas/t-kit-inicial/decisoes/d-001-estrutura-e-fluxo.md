# D-001 — Kit de memória em arquivos e fluxo por branch

Registro histórico do desenho inicial. A escolha de distribuir um auxiliar foi substituída por [D-002](d-002-manutencao-pelo-agente.md), por pedido explícito do usuário. As demais regras de memória e publicação continuam válidas.

- Tarefa: t-kit-inicial.
- Data: 16/10/2026, America/Sao_Paulo.
- Situação: confirmada quanto aos requisitos; implementação local sujeita a teste.
- Origem: respostas do usuário na conversa que iniciou este repositório.

## Contexto

O usuário usa memória Markdown no game-zombie e quer reaproveitar o método em outros projetos sem operar o servidor do ai-memory. Pretende alternar ferramentas e computadores, levando skill e memória pelo GitHub.

## Escolha e motivo

Memória em pasta organizada, com resumo de projeto e registros por tarefa/branch. Uma skill canônica ensina a leitura e manutenção; Codex e Claude Code têm entradas para o mesmo procedimento. Templates e auxiliar ficam disponíveis dentro de cada projeto para evitar dependência do caminho do kit original.

O usuário escolheu registrar decisões e descobertas durante o trabalho e resumir etapas; bugs devem ter causa, solução e teste. Foi aceita a alternativa manual documentada quando automatizar não for viável.

O usuário quer investigação e perguntas relevantes para maximizar o contexto útil na inicialização. Memórias antigas podem ser sintetizadas, preservando o original e identificando fatos não revalidados.

## Fluxo aprovado

Preparar e validar localmente; entregar para teste humano; obter autorização para commit/push e autorização separada para merge. Um pedido explícito já é autorização para sua ação e não exige confirmação repetida. Registros de permissões antigas não autorizam novas alterações.

## Consequências

O usuário precisa publicar/baixar a mesma branch para transportar alterações entre computadores. Uma skill não garante captura em encerramento abrupto. A estratégia por tarefa reduz colisões, mas integração de código e decisões exige revisão. Cada agente simultâneo usa um checkout/worktree próprio.

## Fontes e estado

Requisitos sintetizados na [memória do projeto](../../../PROJETO.md). Detalhes do desenho na [arquitetura](../../../../ARQUITETURA.md). A memória antiga de referência é [MEMORIA_PERSISTENTE_V42.md](https://github.com/VikThorSkynet/game-zombie/blob/main/docs/MEMORIA_PERSISTENTE_V42.md); sua migração não foi executada.
