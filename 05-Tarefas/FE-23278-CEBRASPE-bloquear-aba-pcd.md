---
title: FE-23278 — CEBRASPE — bloquear aba PCD
type: task
status: todo
priority: high
due: 2026-05-07
project: [[CEBRASPE]]
person:
tags:
  - cebraspe
  - dev
  - pcd
  - pne
  - azure
created: 2026-05-06
---

# FE-23278 — CEBRASPE — bloquear aba PCD

> Status: ⬜ Pendente | Projeto: [[CEBRASPE]]

## Descricao

Bloquear a aba `PCD` quando o evento usar o metodo de avaliacao PNE com tres avaliadores, para evitar acesso a uma funcionalidade que nao se aplica a esse tipo de evento.

## Contexto

O metodo de avaliacao por 3 avaliadores para PNE nao sera mais utilizado no SiAtendimentoEspecifico.
Por isso, em eventos que usem esse metodo, a aba `PCD` nao deve ficar disponivel para acesso.

## Regras de Negocio

- Se `UsaNovoModeloAvaliacaoPCD=1`, a aba `PCD` nao deve estar habilitada.
- Nos demais casos, a aba `PCD` deve permanecer disponivel normalmente.
- A parte de `Recursos` deve permanecer habilitada independentemente do metodo de avaliacao.

## Passo a Passo

- [ ] Identificar onde a exibicao ou habilitacao da aba `PCD` e controlada
- [ ] Validar como o campo `UsaNovoModeloAvaliacaoPCD` chega na tela ou fluxo
- [ ] Implementar bloqueio da aba `PCD` quando `UsaNovoModeloAvaliacaoPCD=1`
- [ ] Garantir que `Recursos` continue habilitado em todos os cenarios
- [ ] Testar cenario com `UsaNovoModeloAvaliacaoPCD=1`
- [ ] Testar cenario com outros metodos de avaliacao
- [ ] Registrar resultado e proximos ajustes, se houver

## Link Externo

- https://dev.azure.com/Cebraspe/SiAtendimentosEspecificos/_workitems/edit/23278

## Recursos Necessarios

- [[CEBRASPE]]
- [[01-Daily/2026-05-06]]

## Notas

Tarefa criada a partir do planejamento da daily de 2026-05-06 para iniciar no dia 2026-05-07.
