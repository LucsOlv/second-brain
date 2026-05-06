<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Nome do MOC");
  if (prompted) {
    noteTitle = `MOC - ${prompted}`;
    await tp.file.rename(noteTitle);
  }
}
%>
---
title: <% noteTitle %>
type: moc
tags:
  - moc
---

# <% noteTitle %>

## Sobre

<!-- Qual contexto esse MOC organiza -->

## Links Principais

- 

## Navegacao

- [[MOC - Home]]
