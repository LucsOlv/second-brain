---
title: Hermes Agent
type: ferramenta
status: active
priority: high
start_date: 2026-04-27
tags: [ai, agent, cli, hermes, secondbrain]
relacionado: [[MOC - Projetos]], [[Codex]]
---

# Hermes Agent

> 🤖 Agente AI pessoal — Second Brain automatizado. Corre no servidor como serviço systemd.

```yaml
type: ferramenta
status: active
priority: high
start_date: 2026-04-27
tags: [ai, agent, cli, hermes, secondbrain]
```

## 🎯 Objetivo

Agente AI que funciona como second brain, fazendo:
- 📝 Gestão de notas Obsidian (criar, atualizar, linked notes)
- 🔄 Sincronização com GitHub (commit automático a cada mudança)
- 💬 Comunicação via Discord / Telegram / API Server
- 🔗 Criação automática de links e conexões entre notas
- 🔁 Tarefas recorrentes via cron jobs
- 🌐 Acesso a ferramentas (web, terminal, browser, etc.)

## ⚙️ Stack Técnica

| Componente | Tecnologia |
|---|---|
| Agente core | Hermes Agent (Node.js, ESM) |
| Modelo | gpt-5.4-mini (default) via OpenAI |
| Integrações | Discord, Telegram, API Server |
| Sincronização | GitHub (commits automáticos) |
| Cross-device | Syncthing |
| Hosting | Ubuntu 24.04, Docker (Portainer) |

## 📋 Ferramentas e Integrações

| Ferramenta | Status | Nota |
|---|---|---|
| Discord | ✅ Conectado | Canal `#geral`, thread `Obsidian` |
| Telegram | ✅ Conectado | Comandos `/codex`, `/health`, `/help` |
| API Server | ✅ Conectado | |
| Obsidian sync | ✅ Ativo | GitHub auto-commit |
| Syncthing | ✅ Configurado | Device: `HGWK4Y3...`, LAN: `192.168.1.242:8384` |
| Docker | ✅ Ativo | Portainer, AI Control Center |

## 📋 Cron Jobs Activos

| Horário | Tarefa | Destino |
|---|---|---|
| 09:00 | Mensagem a Ricardo (nutrologista) | Telegram/Discord |
| 21:00 | Mensagem a Ricardo (nutrologista) | Telegram/Discord |
| 12:00 | Auto-commit Obsidian | GitHub |
| 18:00 | Auto-commit Obsidian | GitHub |

## 📝 Notas

- Corre como serviço systemd no servidor
- Usa skills para tarefas recorrentes (Obsidian, GitHub, Telegram, etc.)
- Memory persistente: preferences, environment facts, tool quirks
- Skills carregadas automaticamente quando relevantes

## 🔧 Configurações Actuais

- Modelo default: `gpt-5.4-mini` (provider: `openai`, base_url: vazio)
- Codex: `--dangerously-bypass-approvals-and-sandbox` (sandbox desativado)

---

## 🔗 Conectado a

- [[Codex]] — Codex CLI para coding (bridge em `telegram-codex-linear-bridge/`)
- [[MOC - Projetos]]
- [[01-Daily/2026-04-27]] — Configuração e uso
- [[04-Saude-Mental/README| Saúde Mental]] — gestão de bem-estar