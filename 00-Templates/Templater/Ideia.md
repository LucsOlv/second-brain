<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Titulo da ideia");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}
%>
---
title: <% noteTitle %>
type: idea
status: raw
tags: []
created: <% tp.date.now("YYYY-MM-DD") %>
description: |
  
why_good: |
  
---

# <% noteTitle %>

## Descricao

<!-- Qual e a ideia? -->

## Por que ela e boa

<!-- O que torna isso promissor -->

## Proximos Passos

- [ ]

## Ligacoes

<!-- Relacionar com projetos, pessoas ou referencias se fizer sentido -->
