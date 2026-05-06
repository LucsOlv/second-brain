<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Nome do hub");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const projectInput = await tp.system.prompt("Projeto relacionado (opcional)", "");
const project = projectInput ? (projectInput.startsWith("[[") ? projectInput : `[[${projectInput}]]`) : "";
%>
---
title: <% noteTitle %>
type: hub
project: <% project %>
tags: []
---

# <% noteTitle %>

## Sobre

<!-- Para que esse hub existe -->

## Indice

- 

## Proximo Passo

- [ ]
