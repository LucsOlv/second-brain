---
title: Codex CLI
type: projeto
status: active
priority: high
start_date: 2026-04-27
tags: [ai, cli, coding, openai, priority-high]
relacionado: [[MOC - Projetos]], [[Hermes Agent]]
---

# Codex CLI

> Status: 🟢 Ativo | Prioridade: 🔴 Alta | Iniciado: 27/04/2026

```yaml
type: projeto
status: active
priority: high
start_date: 2026-04-27
tags: [ai, cli, coding, openai]
```

## 🎯 Objetivo

Usar o Codex CLI da OpenAI como assistente de coding via linha de comando. Integrar com o fluxo de trabalho do Hermes Agent.

## ⚙️ Configuração

```bash
#Localização
~/.hermes/hermes-agent/scripts/telegram-codex-linear-bridge/src/codex.js

#Modo: --dangerously-bypass-approvals-and-sandbox (sandbox desativado)
```

## 📋 Uso

| Comando | Descrição |
|---|---|
| `codex <prompt>` | Executar tarefa de coding |
| `codex --help` | Ver opções |

## 📋 Testes Realizados

| Data | Teste | Resultado | Cota |
|---|---|---|---|
| 2026-04-27 | Testes de estresse | Não funcionou bem — esgotou cota rapidamente | ⚠️ Alta consumo |

## 💡 Insights

- Cota esgota-se rapidamente com testes de estresse
- É melhor usar para tarefas concretas, não para explorar
- Configuração actual: `--dangerously-bypass-approvals-and-sandbox` (sem restriçoes)
- Integra com Telegram via bridge (`telegram-codex-linear-bridge`)

## 🔧 Otimização

| Estratégia | Status | Nota |
|---|---|---|
| Limitar uso a tarefas críticas | 🔜 Por implementar | |
| Usar como fallback, não como primeira opção | 🔜 Por implementar | |
| Monitorar consumo de cota | 🔜 Por implementar | |

## ⚠️ Limitações Conhecidas

- Cota limitada — esgotou rápido em testes (27/04)
- Não funciona bem para testes de estresse prolongados

## 📝 Notas

- Bridge em: `~/.hermes/hermes-agent/scripts/telegram-codex-linear-bridge/`
- Entry point: `bridge.js` → modular `src/` (TDD, 94% coverage)

---

## 🔗 Conectado a

- [[Hermes Agent]] — integração com agent
- [[Codex]] — esta nota (auto-referência)
- [[MOC - Projetos]]
- [[01-Daily/2026-04-27]] — Testes do dia 27/04