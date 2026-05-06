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
- Linkar pessoa apenas quando ela fizer parte real da execucao
- Linkar daily apenas quando a tarefa foi criada, trabalhada ou concluida naquele dia
- Manter `Recursos Necessarios` enxuto: projeto, pessoa, referencia externa e dailies relevantes
- Evitar usar cada task como mini-MOC; backlinks e a nota do projeto devem fazer a navegacao principal
- Revisar semanalmente via [[MOC - Tarefas]]
