# Estado do guia visual

Identidade e branch: [tarefa.json](tarefa.json). Data: 16/10/2026, America/Sao_Paulo.

## Objetivo e critérios de aceitação

Pedido do usuário: criar um HTML bem visual para explicar todos os fluxos e o funcionamento do repositório. Entregar um arquivo independente, em português, com conteúdo fiel ao kit 0.2.1, navegação e exemplos interativos, sem instalar dependências no projeto.

## Resultado local

[GUIA_VISUAL.html](../../../GUIA_VISUAL.html) contém visão geral, fluxos passo a passo, árvore de arquivos clicável, simulação de branches e integração, regra de repositório do merge, prompt de instalação copiável e perguntas frequentes. Os exemplos são identificados como ilustrativos e a página não executa operações no projeto ou GitHub.

README inclui o acesso ao guia e explica como abrir o HTML baixado. Esta implementação foi integrada e publicada na main em 16/10/2026, com o HTML incluído explicitamente no escopo autorizado.

Complemento solicitado pelo usuário: o início do README explica por que a memória persistente é importante e credita a inspiração no ai-memory e no artigo de Fabio Akita. Destaca a proposta simples e por projeto, com arquivos e skill mantidos pelo agente. As fontes foram consultadas; Docker foi descrito como opção de implantação do ai-memory, sem afirmar que é obrigatório.

## Validação

Rodada final no Microsoft Edge headless/Playwright: sete fluxos e 33 etapas, 13 seleções de arquivos, alternativa manual de regressão, branches/merge/reinício, três situações de repositório, temas e cópia do prompt. Sem erros de JavaScript e sem overflow da página em 1440, 1024, 768, 390 e 360 pixels. Navegação dos fluxos pelo teclado aprovada; prompt copiável idêntico ao bloco do README; IDs únicos e âncoras locais existentes.

Revisão visual das capturas de desktop e celular realizada. Ferramentas e capturas de QA ficam fora do projeto, na pasta de trabalho da conversa; não são instaladores/verificadores distribuídos com o kit. Esses testes validam o guia, não a execução do protocolo por agentes em outros projetos.

## Entrega e próximo passo

Teste do usuário não informado. Os pedidos atuais autorizaram publicação e merge, incluindo o HTML. Commit de conteúdo `6863d950e9fe2d16d56693355c1379cfb131d8d4` publicado em docs/guia-visual; merge `08c9569c866ceccb585ff1adacedc8860edb7a9b` publicado e confirmado em origin/main. Não houve conflito. O arquivo HTML está no repositório; não foi configurada hospedagem GitHub Pages.

Próximo passo: usar o guia e testar a retomada do kit em conversas novas. Este registro documenta a entrega autorizada e não permite novas publicações sem escopo atual.
