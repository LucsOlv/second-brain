<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Nome do projeto");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const area = await tp.system.suggester(
  ["work", "study", "personal"],
  ["work", "study", "personal"]
);
const priority = await tp.system.suggester(
  ["high", "medium", "low"],
  ["high", "medium", "low"]
);
const deadline = await tp.system.prompt("Deadline (YYYY-MM-DD, opcional)", "");
const relatedInput = await tp.system.prompt("Notas relacionadas (separadas por virgula, opcional)", "");
const relatedItems = relatedInput
  ? relatedInput.split(",").map(item => item.trim()).filter(Boolean).map(item => item.startsWith("[[") ? item : `[[${item}]]`)
  : [];
const relatedYaml = relatedItems.length ? "\n" + relatedItems.map(item => `  - ${item}`).join("\n") : " []";
%>
---
title: <% noteTitle %>
type: project
area: <% area || "work" %>
status: active
priority: <% priority || "medium" %>
start_date: <% tp.date.now("YYYY-MM-DD") %>
deadline: <% deadline %>
tags: []
related:<% relatedYaml %>
---

# <% noteTitle %>

> Status: 🔄 Ativo | Prioridade: <% priority || "medium" %>

## Sobre

<!-- O que e este projeto? -->

## Contexto

<!-- Por que existe, qual o escopo e o momento atual -->

## Proxima Acao

- [ ]

## Tarefas Ativas

<!-- Linkar tarefas realmente abertas -->

## Notas

<!-- Decisoes, logs, observacoes -->
