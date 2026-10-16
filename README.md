# persistent_memory

Memória de projeto em Markdown, versionada junto do código, para retomar trabalho no Codex, Claude Code e outros agentes que consigam ler o repositório. Versão do kit: **0.2.1**.

O próprio agente cria as pastas, lê a memória e atualiza os registros seguindo a skill. O Git leva as versões publicadas para outro computador. O kit contém apenas instruções, modelos e configuração: não há programa para instalar ou executar.

## Instalar com um pedido ao agente

Abra seu projeto no Codex, Claude Code ou outro agente com acesso à internet e aos arquivos. Copie e cole este bloco na conversa:

```text
Instale a memória persistente neste projeto usando este repositório:
https://github.com/VikThorSkynet/persistent_memory

Baixe o repositório em uma pasta temporária separada, leia o README e
.agents/skills/memoria-projeto/SKILL.md e execute a instalação completa
no projeto aberto nesta conversa. Se a pasta de destino não estiver clara,
pergunte qual projeto deve receber a memória antes de instalar.

Crie as pastas, copie as skills e inicialize a memória seguindo os modelos.
Preserve as instruções, memórias e o histórico Git existentes. Não copie
a memória particular nem a pasta .git do kit para o projeto de destino.
Faça a instalação diretamente pelos arquivos, sem criar scripts auxiliares.

Investigue o projeto e me faça perguntas para completar objetivos,
prioridades, restrições e critérios de aceitação ainda desconhecidos.
Confira os arquivos e links e informe o que foi instalado e o que falta definir.
Não faça commit, push ou merge sem autorização no escopo atual.
```

O agente baixa e instala o kit; você não precisa baixar ou copiar os arquivos manualmente. O projeto de destino mantém seu próprio repositório e passa a conter a skill e a memória.

Enquanto esta versão estiver apenas local, substitua o link no bloco pela pasta do kit ou pelo ZIP desta entrega. A instalação pelo endereço do GitHub estará disponível depois que os arquivos forem publicados nesse repositório.

## Instalar em um projeto

O agente deve seguir este procedimento, que também pode ser executado por cópia manual:

1. Inspecionar as instruções e memórias existentes no destino.
2. Copiar `.agents/skills/memoria-projeto/` e `.claude/skills/memoria-projeto/` para as mesmas posições no projeto. Comparar arquivos existentes antes de atualizar; preservar adaptações.
3. Criar `docs/memoria/` e copiar os três modelos de `.agents/skills/memoria-projeto/assets/base/`: `INICIO.md`, `PROJETO.md` e `config.json`. Não sobrescrever registros ou configuração existentes. Não copiar a memória particular deste repositório para outro projeto.
4. Acrescentar ao AGENTS.md, sem duplicar uma orientação equivalente:

   ```markdown
   ## Memória persistente

   Antes de trabalhar, leia `.agents/skills/memoria-projeto/SKILL.md`
   e `docs/memoria/INICIO.md`. Identifique a branch e a tarefa, consulte
   os registros relevantes e atualize a memória durante as etapas importantes.
   ```

5. Acrescentar `@AGENTS.md` ao CLAUDE.md da raiz, fora de blocos de código, quando ainda não existir. Preservar as regras anteriores e evitar importações circulares.
6. Investigar o projeto, perguntar o contexto que falta e preencher a configuração e o resumo com fatos confirmados. Comandos desconhecidos ficam pendentes, sem serem inventados.
7. Criar uma tarefa para a branch real usando [os modelos e o formato dos registros](.agents/skills/memoria-projeto/references/registros.md). Conferir arquivos e links antes de entregar.

Reinstalar deve preservar conteúdo, não duplicar entradas e não reiniciar o histórico. Para atualizar a versão, comparar o procedimento novo com adaptações locais e registrar a conciliação.

## Estrutura no projeto

```text
AGENTS.md e CLAUDE.md                entrada para as instruções
.agents/skills/memoria-projeto/      procedimento e modelos
.claude/skills/memoria-projeto/      adaptador curto para o Claude
docs/memoria/
  INICIO.md                         ordem de leitura
  PROJETO.md                        conhecimento integrado
  config.json                       parâmetros por projeto
  tarefas/<id>/
    tarefa.json                     branch e identificação da tarefa
    ESTADO.md                       progresso e próximo passo
    decisoes/                       escolhas e motivos, conforme necessário
    bugs/                           causas, soluções e regressões
    sessoes/                        passagens de trabalho
  arquivo/                          histórico, quando necessário
```

O ID da tarefa permanece estável se sua branch mudar de nome; atualize o tarefa.json. Crie registros apenas quando houver conteúdo útil.

## Retomar em outra conversa

AGENTS.md orienta a leitura inicial. O agente confere a branch e as alterações reais, lê o resumo do projeto e retoma a tarefa ativa correspondente. Abre os detalhes conforme o pedido, sem carregar todo o histórico.

Se a leitura não iniciar, peça:

> Leia AGENTS.md, .agents/skills/memoria-projeto/SKILL.md e docs/memoria/INICIO.md. Confira a branch, encontre a tarefa ativa e me diga onde paramos antes de continuar meu pedido atual.

No Codex, pode invocar `$memoria-projeto`. No Claude Code, `/memoria-projeto`. A aplicação no Claude desktop é à aba Code com acesso à pasta do projeto. Outros agentes podem usar AGENTS.md quando suportado ou receber a orientação explícita acima; não há garantia universal de descoberta.

## Branches e computadores

Cada implementação tem memória própria por tarefa/branch. Agentes simultâneos usam pastas ou worktrees diferentes. Branches não isolam sessões que editam a mesma pasta.

Ao integrar o código, concilie o conhecimento durável no resumo do projeto e preserve os registros relevantes. Para continuar em outro computador, publique e baixe a mesma branch; alterações ainda locais não estarão disponíveis lá.

## Bugs, teste e publicação

Para cada bug corrigido, criar/ampliar um teste de comportamento e registrar reprodução, causa e correção. Quando viável, demonstrar que detecta a falha anterior e passa depois. Se automatizar não for viável, registrar motivo, roteiro manual e cobertura pendente. Os testes seguem a infraestrutura do projeto de destino.

O fluxo padrão é: implementar e validar localmente, entregar para teste do usuário, obter autorização para commit/push e autorização separada para merge. Um pedido explícito já autoriza sua própria ação no escopo atual. Permissões antigas não autorizam novas publicações.

## Repositório do GitHub e merge

O agente guarda o link do repositório do projeto em `docs/memoria/config.json`, no campo `projeto.repositorio_url`. Quando você pedir um merge, ele consulta esse campo. Se não estiver preenchido e você ainda não tiver indicado o destino, pergunta qual repositório usar e salva a resposta antes de continuar.

Com o link já registrado, ele o reutiliza nas próximas conversas e confere o destino das branches/PR. Divergências precisam ser esclarecidas. O modelo inicial traz o campo como null: projetos novos não herdam o endereço deste kit. O link guardado não substitui a autorização de merge.

## Conferir e testar o kit

O próprio agente confere as entradas, os arquivos e links, a configuração e a correspondência entre tarefas e branches. O roteiro de aceitação está em [TESTE_LOCAL.md](docs/TESTE_LOCAL.md). Veja também [a arquitetura](docs/ARQUITETURA.md) e [o estado desta entrega](docs/memoria/tarefas/t-kit-inicial/ESTADO.md).

O kit depende da leitura e escrita do agente enquanto ele trabalha. Não há captura em segundo plano nem garantia de gravação depois de um encerramento abrupto. A retomada real em conversas novas deve ser verificada nos agentes usados.

## Referências

Ideias adaptadas da [arquitetura do ai-memory](https://github.com/akitaonrails/ai-memory/blob/main/docs/ARCHITECTURE.md): Markdown como fonte de conhecimento, resumo limitado, consolidação e passagem de trabalho.

Descoberta: [skills no Codex](https://learn.chatgpt.com/docs/build-skills), [AGENTS.md no Codex](https://learn.chatgpt.com/docs/agent-configuration/agents-md), [memória/instruções no Claude Code](https://code.claude.com/docs/en/memory) e [skills no Claude Code](https://code.claude.com/docs/en/skills). Consultadas em 16/10/2026.
