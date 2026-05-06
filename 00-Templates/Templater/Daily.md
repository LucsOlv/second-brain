<%*
const today = tp.date.now("YYYY-MM-DD");
let fileDate = tp.file.title;

if (fileDate.startsWith("Untitled")) {
  fileDate = today;
  await tp.file.rename(fileDate);
}

const prettyTitle = moment(fileDate, "YYYY-MM-DD").locale("pt-br").format("D [de] MMMM [de] YYYY");
const day = moment(fileDate, "YYYY-MM-DD").locale("pt-br").format("dddd");
%>
---
title: <% prettyTitle %>
date: <% fileDate %>
day: <% day %>
type: daily
energy:
mood:
stress_level:
sleep_hours:
exercise:
tags:
  - daily
---

# <% prettyTitle %>

> :calendar: <% day %>

---

## :brain: Resumo do Dia

<!-- Como foi seu dia? O que aconteceu? -->

## :dart: Tarefas de Hoje

<!-- Linkar apenas tarefas reais do dia -->
- [ ]

---

## :bulb: Insights

<!-- Ideias, reflexoes, descobertas -->

## :books: Estudos

<!-- O que aprendeu hoje? -->

## :peaceful_face: Saude Mental

### :sunrise: Variacoes ao Longo do Dia

| Horario | Energia | Humor | Estresse | Observacoes |
|---------|---------|-------|----------|-------------|
| **07:00** | - | - | - | - |
| **11:00** | - | - | - | - |
| **18:00** | - | - | - | - |
| **22:00** | - | - | - | - |

> :light_bulb: Regista quando sentires mudanca significativa.

| Campo         | Valor |
| ------------- | ----- |
| **Energia**   |       |
| **Humor**     |       |
| **Estresse**  |       |
| **Sono**      |       |
| **Exercicio** |       |

### :pray: Gratidao

<!-- 3 coisas boas do dia -->

### :thought_balloon: Reflexao

<!-- Como estou me sentindo? -->

### :warning: Sinais de Alerta

<!-- Algo que precisa de atencao? -->
- [ ]

### :next_track_button: Acao para Amanha

<!-- Uma coisa que posso fazer melhor amanha -->
- [ ]
