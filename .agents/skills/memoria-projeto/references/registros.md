# Formatos de registro

Os modelos ficam em `../assets/`. Copie apenas o necessário e preencha com fatos; campos não conhecidos permanecem como `A confirmar`. Os modelos não são registros do projeto enquanto estiverem em assets.

| Registro | Modelo | Destino no projeto |
|---|---|---|
| Estado de uma tarefa | [ESTADO.md](../assets/tarefa/ESTADO.md) | `docs/memoria/tarefas/<id>/ESTADO.md` |
| Decisão | [decisao.md](../assets/registros/decisao.md) | `docs/memoria/tarefas/<id>/decisoes/<id>.md` |
| Bug | [bug.md](../assets/registros/bug.md) | `docs/memoria/tarefas/<id>/bugs/<id>.md` |
| Sessão ou checkpoint | [sessao.md](../assets/registros/sessao.md) | `docs/memoria/tarefas/<id>/sessoes/<id-unico>.md` |

## Metadados da tarefa

Ao lado de ESTADO.md, mantenha `tarefa.json` com:

```json
{
  "schema_version": 1,
  "id": "t-exemplo",
  "titulo": "Descrição da implementação",
  "branch": "feat/exemplo",
  "base_commit": null,
  "situacao": "ativa",
  "criada_em": "2026-10-16T12:00:00-03:00"
}
```

Use o commit real de base quando conhecido. `null` significa desconhecido/sem commit. Sem Git, `branch` é `null`; em HEAD destacado use `detached:<SHA>`. `situacao` admite `ativa`, `integrada` e `arquivada`. Só uma tarefa deve estar ativa para a mesma branch; ao iniciar outro escopo nessa branch, arquive a anterior ou continue a tarefa existente.

O próprio agente cria a pasta da tarefa, copia o modelo ESTADO.md e grava o tarefa.json com os dados reais. Antes de criar, confira se já existe tarefa ativa correspondente à branch; retome-a quando for o mesmo trabalho. Preserve o conteúdo de uma tarefa existente. Não troque de branch para ajustar a memória.

## Evidência e tamanho

Escreva a data com fuso, use referências relativas ao projeto e diferencie resultado histórico de verificação atual. Não copie logs extensos se um comando, resultado e caminho de evidência forem suficientes. O roteiro de teste deve permitir que alguém reproduza o caso sem depender da conversa original.

Registros antigos podem continuar na tarefa ou ir para `arquivo/`, desde que os links sejam ajustados. Não mova um arquivo apenas para mudar sua classificação se uma marcação de situação resolver o problema.
