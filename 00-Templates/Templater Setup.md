# Templater Setup

Configuracao exata sugerida para o plugin `Templater` neste vault.

## Fontes

- Docs oficiais de instalacao: https://silentvoid13.github.io/Templater/installation.html
- Docs oficiais de settings: https://silentvoid13.github.io/Templater/settings.html

## 1. Instalar

No Obsidian:

1. `Settings`
2. `Community plugins`
3. Procurar por `Templater`
4. `Install`
5. `Enable`
6. Reiniciar o Obsidian

## 2. Configuracao Geral

No Obsidian:

1. `Settings`
2. `Templater`

Definir:

- `Template folder location`: `00-Templates/Templater`
- `Trigger Templater on new file creation`: `ON`
- `Automatic jump to cursor`: `ON` opcional
- `Syntax Highlighting on Desktop`: `ON`
- `Syntax Highlighting on Mobile`: `OFF` por padrao

Observacao:

- `Folder Templates` so aparece depois de ligar `Trigger Templater on new file creation`.
- `Folder Templates` e `File Regex Templates` sao mutuamente exclusivos. Para este vault, usar `Folder Templates`.

## 3. Folder Templates

Adicionar estas regras em `Templater -> Folder Templates`:

| Folder | Template |
| --- | --- |
| `01-Daily` | `Daily.md` |
| `02-Projetos` | `Projeto.md` |
| `03-Pessoas` | `Pessoa.md` |
| `04-Saude-Mental` | `Mental Check-in.md` |
| `05-Tarefas` | `Tarefa.md` |
| `07-Ideias` | `Ideia.md` |
| `07-Ideias/Resumos` | `Resumo.md` |
| `08-Referencias` | `Referencia.md` |
| `09-MOCs` | `MOC.md` |

Observacoes:

- A regra mais profunda vence. Entao `07-Ideias/Resumos` pode ter `Resumo.md`, mesmo com `07-Ideias` usando `Ideia.md`.
- Se quiser um template curado especial, use `Hub.md` manualmente, sem folder template automatico.

## 4. Comportamento Esperado

### Daily

- Ao criar uma nota nova em `01-Daily`, se ela nascer como `Untitled`, o template renomeia para a data de hoje em `YYYY-MM-DD`.
- O titulo humano e o dia da semana tambem sao preenchidos.

### Projeto

- Ao criar em `02-Projetos`, o template pergunta:
  - nome do projeto
  - area
  - prioridade
  - deadline
  - related notes

### Pessoa

- Ao criar em `03-Pessoas`, o template pergunta:
  - nome
  - papel
  - contato
  - projetos relacionados

### Tarefa

- Ao criar em `05-Tarefas`, o template pergunta:
  - titulo
  - projeto
  - prioridade
  - due date
  - pessoa relacionada

### Referencia

- Ao criar em `08-Referencias`, o template pergunta:
  - titulo
  - source
  - autor
  - URL
  - notas relacionadas

### Resumo

- Ao criar em `07-Ideias/Resumos`, o template pergunta:
  - titulo
  - projeto
  - data
  - hub relacionado

## 5. Recomendacao de Uso

- Criar dailies diretamente dentro de `01-Daily`
- Criar tasks diretamente dentro de `05-Tarefas`
- Evitar usar `Untitled` fora da pasta certa, para nao disparar o template errado
- Usar `Hub.md` manualmente para hubs curados
- Manter o plugin nativo `Templates` desligado ou sem uso, para nao confundir com o `Templater`

## 6. Opcional

Se quiser evitar conflito mental entre os dois sistemas:

- deixar `Core plugin: Templates` desativado
- usar apenas `Templater`

Hoje no vault o plugin nativo `Templates` esta ativo e o `Templater` ainda nao esta instalado.
