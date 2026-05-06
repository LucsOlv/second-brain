<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Nome da pessoa");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const role = await tp.system.prompt("Papel / funcao", "");
const contact = await tp.system.prompt("Contato (opcional)", "");
const projectsInput = await tp.system.prompt("Projetos relacionados (separados por virgula, opcional)", "");
const projectItems = projectsInput
  ? projectsInput.split(",").map(item => item.trim()).filter(Boolean).map(item => item.startsWith("[[") ? item : `[[${item}]]`)
  : [];
const projectsYaml = projectItems.length ? "\n" + projectItems.map(item => `  - ${item}`).join("\n") : " []";
%>
---
title: <% noteTitle %>
type: person
name: <% noteTitle %>
role: <% role %>
contact: <% contact %>
projects:<% projectsYaml %>
last_contact:
tags: []
---

# <% noteTitle %>

## Contexto

<!-- Quem e essa pessoa e por que ela importa no vault -->

## Relacao Atual

<!-- Como voce interage com ela hoje -->

## Notas

<!-- Detalhes uteis para lembrar depois -->
