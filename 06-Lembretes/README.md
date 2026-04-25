# ⏰ Lembretes

Lembretes recorrentes e únicos — não são tarefas, são eventos/compromissos.

## Template

```yaml
type: reminder
title: 
frequency: # once/daily/weekly/monthly/yearly
next_date: YYYY-MM-DD
category: # health/work/personal/financial
notes: 
```

## Categorias

- `#saúde` — medicação, consulta, exercício
- `#trabalho` — deadline, reunião, entrega
- `#pessoal` — aniversário, evento, compromisso
- `#financeiro` — conta, pagamento, fatura

## Regras

- Recurring reminders devem ter lógica de renovação
- Linkar ao calendário ou projeto quando aplicável
- Revisar mensalmente em [[MOC - Lembretes]]