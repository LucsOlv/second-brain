<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Titulo da referencia");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const source = await tp.system.suggester(
  ["article", "book", "video", "podcast", "course", "concept", "meeting"],
  ["article", "book", "video", "podcast", "course", "concept", "meeting"]
);
const author = await tp.system.prompt("Autor (opcional)", "");
const url = await tp.system.prompt("URL (opcional)", "");
const relatedInput = await tp.system.prompt("Notas relacionadas (separadas por virgula, opcional)", "");
const relatedItems = relatedInput
  ? relatedInput.split(",").map(item => item.trim()).filter(Boolean).map(item => item.startsWith("[[") ? item : `[[${item}]]`)
  : [];
const relatedYaml = relatedItems.length ? "\n" + relatedItems.map(item => `  - ${item}`).join("\n") : " []";
const relatedBody = relatedItems.length ? relatedItems.map(item => `- ${item}`).join("\n") : "<!-- Linkar projetos, resumos ou dailies quando fizer sentido -->";
%>
---
title: <% noteTitle %>
type: reference
source: <% source || "concept" %>
url: <% url %>
author: <% author %>
date: <% tp.date.now("YYYY-MM-DD") %>
tags: []
summary: |
  
key_takeaways: []
related_notes:<% relatedYaml %>
---

# <% noteTitle %>

## Contexto

<!-- Onde isso apareceu e por que importa -->

## Resumo

<!-- Resumo em 2-3 linhas -->

## Pontos Importantes

- 

## Ligacoes

<% relatedBody %>
