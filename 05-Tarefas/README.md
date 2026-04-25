# ✅ Tarefas

Tarefas com contexto, deadline e projeto vinculado.

## Template

```yaml
type: task
status: # todo/in_progress/done/cancelled
priority: # high/medium/low
due: YYYY-MM-DD
project: [[nome-do-projeto]]
person: [[nome-da-pessoa]]
tags: []
created: YYYY-MM-DD
```

## Status

- `todo` — pendente
- `in_progress` — sendo feita
- `done` — concluída
- `cancelled` — cancelada

## Regras

- Toda tarefa linka a um projeto (exceto tarefas pessoais gerais)
- Tarefas de alta prioridade = link para projeto relevante
- Revisar semanalmente via [[MOC - Tarefas]]