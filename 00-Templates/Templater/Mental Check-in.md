<%*
const today = tp.date.now("YYYY-MM-DD");
let fileTitle = tp.file.title;

if (fileTitle.startsWith("Untitled")) {
  fileTitle = `Check-in ${today}`;
  await tp.file.rename(fileTitle);
}
%>
---
title: <% fileTitle %>
type: mental_checkin
date: <% today %>
energy:
mood:
stress_level:
sleep_hours:
exercise:
social_interaction:
related_daily: [[01-Daily/<% today %>]]
tags:
  - mental-health
---

# <% fileTitle %>

## Como estou

- Energia:
- Humor:
- Estresse:

## Corpo

- Sono:
- Exercicio:
- Sensacoes fisicas:

## Social

- Interacao social:

## Reflexao

<!-- O que estou sentindo agora -->

## Sinais de Alerta

- [ ]

## Proxima Acao

- [ ]
