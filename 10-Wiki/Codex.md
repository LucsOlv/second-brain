---
title: Codex CLI
type: ferramenta
status: active
priority: high
start_date: 2026-04-27
tags: [ai, cli, coding, openai, ferramenta]
---

# Codex CLI

> Ferramenta de coding assistido da OpenAI — assistente AI via linha de comando.

```yaml
type: ferramenta
status: active
priority: high
start_date: 2026-04-27
tags: [ai, cli, coding, openai, ferramenta]
```

## 🎯 O Que É

Codex CLI é o assistente de coding da OpenAI, acessível via linha de comando. Executa tarefas de programação autónomo com base em prompts em linguagem natural.

## ⚙️ Configuração

```bash
# Localização
~/.hermes/hermes-agent/scripts/telegram-codex-linear-bridge/src/codex.js

# Modo actual: sandbox desativado
--dangerously-bypass-approvals-and-sandbox
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
- Melhor usar para tarefas concretas, não para explorar
- Configuração actual: `--dangerously-bypass-approvals-and-sandbox`
- Integra com Telegram via bridge (`telegram-codex-linear-bridge`)

## ⚠️ Limitações Conhecidas

- Cota limitada — esgotou rápido em testes (27/04)
- Não funciona bem para testes de estresse prolongados

## 📝 Notas

- Bridge em: `~/.hermes/hermes-agent/scripts/telegram-codex-linear-bridge/`
- Entry point: `bridge.js` → modular `src/` (TDD, 94% coverage)

---

## 🔗 Conectado a

- [[Hermes Agent]] — integração com agent
- [[MOC - Projetos]] (referência)