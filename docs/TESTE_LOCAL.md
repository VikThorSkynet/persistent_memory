# Testar o kit com um agente

Use uma pasta vazia ou um projeto descartável. O agente precisa conseguir ler a pasta/ZIP do kit e editar a pasta de destino. Não é necessário publicar o repositório para testar esta entrega local.

## 1. Instalar por instrução

Abra a pasta de teste no Codex ou Claude Code e indique a localização do kit:

> Instale a memória deste kit nesta pasta usando suas ferramentas de arquivos. Siga o README e a skill, preserve arquivos existentes e não publique nada. Quero planejar uma lista de tarefas simples, ainda sem implementar. Investigue o projeto e me faça perguntas para definir objetivo, escopo e critérios de aceitação.

Esperado: skills e memória criadas, AGENTS.md e CLAUDE.md conectados sem duplicação e contexto esclarecido com perguntas. Sem inventar comandos de teste, resultados ou decisões do usuário.

## 2. Conferir preservação

Registre uma preferência do projeto no AGENTS.md, fora da entrada do kit, e uma decisão na memória. Peça para conferir/reinstalar o kit preservando adaptações.

Esperado: a regra, a decisão e os parâmetros permanecem. Não há instruções ou registros duplicados. O agente não substitui a memória pelos modelos.

## 3. Retomar com outro agente

Abra uma conversa nova, de preferência no outro agente, na mesma pasta:

> Retome o contexto pela memória. Me diga o objetivo, as decisões confirmadas, onde paramos e o próximo passo. Aguarde meu próximo pedido de implementação.

Esperado: contexto coerente com os registros, sem acesso à conversa anterior. Se não carregar sozinho, use a frase explícita de retomada do README e informe ferramenta/versão.

## 4. Conferir branches

Em repositório descartável, use duas branches com checkouts/worktrees separados. Cada implementação deve ter tarefa ligada à sua branch. Peça a cada agente para informar qual tarefa está retomando.

Esperado: cada um retoma sua própria implementação. Não trata outra branch como integrada nem troca a branch automaticamente.

## 5. Conferir bugs

Em um projeto com testes existentes, peça a correção de um bug reproduzível. Confira registro de reprodução, causa/hipótese, correção e teste de regressão. Quando viável, o teste deve detectar a falha anterior e passar depois.

Sem automação viável, deve haver motivo, roteiro manual e cobertura pendente. Teste não executado não pode ser apresentado como aprovado.

## 6. Conferir o destino do merge

Em projeto descartável, deixe `projeto.repositorio_url` ausente ou null e peça ao agente para preparar um merge, sem executá-lo. Ele deve perguntar qual repositório usar quando você ainda não tiver informado o destino. Após sua resposta, deve guardar o link em config.json. Em uma conversa nova, deve reutilizar o link, sem pedir a mesma informação de novo. Se houver divergência com o destino da branch/PR, deve esclarecê-la.

Confirme que o endereço salvo é o do projeto de teste, e não o do distribuidor do kit. Não é necessário executar um merge real para conferir esse comportamento.

## 7. Retornar o resultado

Informe sistema, ferramenta/versão, se leu a memória sozinho, se fez perguntas úteis e se o outro agente retomou corretamente. Depois dos ajustes e de sua autorização, a entrega pode ser commitada e enviada à branch remota. O merge será tratado separadamente.
