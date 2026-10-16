# D-003 — Guardar e consultar o repositório do merge

- Tarefa: t-kit-inicial.
- Data: 16/10/2026, America/Sao_Paulo.
- Situação: confirmada por pedido explícito do usuário.

## Escolha

Guardar o link do repositório em `projeto.repositorio_url` no config.json da memória. Quando houver pedido de merge sem destino conhecido, perguntar qual repositório usar, aguardar a resposta e salvá-la. Reutilizar a informação nas próximas conversas e esclarecer divergências com o destino das branches/PR.

## Consequências

O modelo inicial usa null; a ausência do campo em versões antigas também significa desconhecido. O repositório do distribuidor não é um default para projetos novos. Guardar o link não concede autorização para publicar ou integrar mudanças.

Neste próprio projeto, o usuário já forneceu `https://github.com/VikThorSkynet/persistent_memory.git`; o endereço foi salvo como link HTTPS sem sufixo .git. Não foi necessário perguntar novamente e nenhum merge foi executado. O kit passa a 0.2.1 mantendo o formato 1.
