<%*
let noteTitle = tp.file.title;
if (noteTitle.startsWith("Untitled")) {
  const prompted = await tp.system.prompt("Titulo do resumo");
  if (prompted) {
    noteTitle = prompted;
    await tp.file.rename(noteTitle);
  }
}

const project = await tp.system.suggester(
  ["ONFIAP", "AUVP", "CEBRASPE", "PRION", "CI&T", "PESSOAL"],
  ["[[ONFIAP]]", "[[AUVP]]", "[[CEBRASPE]]", "[[PRION]]", "[[CI&T]]", "[[PESSOAL]]"]
);
const summaryDate = await tp.system.prompt("Data do resumo (YYYY-MM-DD)", tp.date.now("YYYY-MM-DD"));
const hubInput = await tp.system.prompt("Hub relacionado (opcional)", "");
const hub = hubInput ? (hubInput.startsWith("[[") ? hubInput : `[[${hubInput}]]`) : "";
const linksBody = [project, hub].filter(Boolean).length
  ? [project, hub].filter(Boolean).map(item => `- ${item}`).join("\n")
  : "<!-- Linkar projeto, hub ou daily se fizer sentido -->";
%>
---
title: <% noteTitle %>
type: summary
project: <% project || "" %>
date: <% summaryDate || tp.date.now("YYYY-MM-DD") %>
tags: []
---

# <% noteTitle %>

## Resumo

<!-- O que foi estudado / observado -->

## Pontos Importantes

- 

## Proximo Passo

- [ ]

## Ligacoes

<% linksBody %>
