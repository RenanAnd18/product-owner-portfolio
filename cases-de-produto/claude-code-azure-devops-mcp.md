# 🔗 Conexão Claude Code (CLI) ↔ Azure DevOps (MCP) via PAT

Este documento descreve o passo a passo que utilizei para conectar o **Claude Code (CLI)** ao **Azure DevOps** via **MCP (Model Context Protocol)** utilizando **Personal Access Token (PAT)**.

📅 Data da implementação: 25/02/2026  
💻 Ambiente: Windows + PowerShell  
🎯 Objetivo: Permitir que o Claude interaja com Work Items, queries WIQL e projetos diretamente no Azure DevOps.

---

# 📌 Contexto

Ao tentar adicionar o servidor `azure-devops` no Claude CLI, recebi o erro:
Failed to connect


Após alguns testes, ajustes de ordem de argumentos e validações, os passos abaixo resolveram definitivamente o problema.

---


# Conexão Claude CLI ↔ Azure DevOps (MCP) via **PAT** — Passo a passo que funcionou


Este guia registra exatamente os passos (1–5) que resolveram o erro **Failed to connect** ao adicionar o servidor **azure-devops** no Claude CLI usando **Personal Access Token (PAT)**.

---

## ✅ Pré-requisitos rápidos
- **PowerShell** (não use Git Bash/WSL)  
- **Node.js 18+** instalado  
- **Claude CLI** instalado globalmente: `npm i -g @anthropic-ai/claude-code`

> Dica: execute os comandos **fora de** `C:\Windows\System32`, por exemplo: `cd $HOME`.

---

## Passo a Passo:

## 1) Ir para a pasta do usuário
```powershell
cd $HOME
```

---

## 2) Remover qualquer configuração anterior do MCP Azure DevOps
```powershell
claude mcp remove azure-devops
```

---

## 3) Definir o PAT (somente nesta sessão)
> Substitua `SEU_PAT_AQUI` pelo seu token válido com escopos mínimos: **Project and Team: Read** e **Work Items: Read**.
```powershell
$env:AZURE_DEVOPS_PAT = "SEU_PAT_AQUI"
```

> Segurança: após concluir os testes, **rotacione** o PAT.

---

## 4) Adicionar o MCP com a **ordem correta** dos argumentos
> **Importante**: nesta versão do Claude CLI, o formato esperado é `claude mcp add <name> <commandOrUrl> [args...] [options]`.  
> Ou seja, primeiro vem o comando (`npx @azure-devops/mcp onclickbr`), **depois** as variáveis `-e`.

```powershell
claude mcp add azure-devops npx @azure-devops/mcp nome-organizacao   -e AZURE_DEVOPS_ORG_URL=https://dev.azure.com/nome-organizacao   -e AZURE_DEVOPS_AUTH_METHOD=pat   -e AZURE_DEVOPS_PAT=$env:AZURE_DEVOPS_PAT
```

Notas:
- Não use `-y` com `npx` aqui para evitar conflito de parsing.  
- Se o `npx` pedir confirmação na primeira execução, rode antes: `npx @azure-devops/mcp --version` e repita o passo.

---

## 5) Validar a conexão e as ferramentas
```powershell
claude mcp list
claude mcp tools
```
Resultados esperados:
- `claude mcp list` deve mostrar `azure-devops` como **running/connected**.  
- `claude mcp tools` deve listar ferramentas como `list-projects`, `run-wiql`, `get-work-item`, etc.

---

## Troubleshooting rápido
- **unknown option '-y'**: ocorre quando o `-y` do `npx` é interpretado pelo `claude`. Solução: **não usar `-y`** ou usar o comando no formato do passo 4 (ordem correta).
- **missing required argument 'commandOrUrl'**: a sua versão do CLI exige o **comando** logo após o nome do servidor; siga o passo 4.
- **Failed to connect**: verifique URL da org (`https://dev.azure.com/nome-organizacao`), método `pat`, e o valor de `AZURE_DEVOPS_PAT`. Confira também os escopos do PAT e validade.
- Logs: `claude mcp logs azure-devops`.

---

## Exemplos de uso (agora que está conectado)
- "Liste todos os projetos da minha organização no Azure DevOps."
- "Liste os work items ativos do projeto "ERP" agrupados por prioridade."
- "Execute uma consulta WIQL para listar bugs abertos mostrando ID, título e estado."

---

**Autor:** Renan Andrade Ribeiro — registro dos passos que funcionaram no ambiente Windows/PowerShell.
