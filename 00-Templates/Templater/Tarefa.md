<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Titulo da tarefa");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const project = await tp.system.suggester(
  ["CEBRASPE", "PRION", "CI&T", "ONFIAP", "AUVP", "PESSOAL"],
  ["[[CEBRASPE]]", "[[PRION]]", "[[CI&T]]", "[[ONFIAP]]", "[[AUVP]]", "[[PESSOAL]]"]
);
const priority = await tp.system.suggester(
  ["high", "medium", "low"],
  ["high", "medium", "low"]
);
const due = await tp.system.prompt("Due date (YYYY-MM-DD, opcional)", "");
const personInput = await tp.system.prompt("Pessoa relacionada (opcional)", "");
const person = personInput ? (personInput.startsWith("[[") ? personInput : `[[${personInput}]]`) : "";
const resources = [project, person].filter(Boolean);
const resourcesBody = resources.length ? resources.map(item => `- ${item}`).join("\n") : "<!-- Adicionar links, pessoas ou referencias -->";
%>
---
title: <% noteTitle %>
type: task
status: todo
priority: <% priority || "medium" %>
due: <% due %>
project: <% project || "" %>
person: <% person %>
tags: []
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% noteTitle %>

> Status: ⬜ Pendente | Projeto: <% project || "" %>

## Descricao

<!-- O que precisa ser feito? -->

## Contexto

<!-- Por que isso existe e por que importa -->

## Passo a Passo

- [ ] Entender o problema
- [ ] Executar
- [ ] Validar
- [ ] Registrar resultado

## Recursos Necessarios

<% resourcesBody %>

## Notas

<!-- Observacoes, erros, decisoes -->
