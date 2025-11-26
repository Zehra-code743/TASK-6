# 🚀 GitHub MCP Server — Gemini CLI Integration (Hosted Method)

This guide explains how to securely connect the **GitHub MCP Server** with **Google Gemini CLI** using the hosted method.  
No Docker. No manual server setup. Only a token + configuration file → instant GitHub automation through AI.

---

## 📘 Table of Contents
- [🔹 Step 1 — Create GitHub Personal Access Token (PAT)](#-step-1--create-github-personal-access-token-pat)
- [🔹 Step 2 — Save Token in `.env`](#-step-2--save-token-in-env)
- [🔹 Step 3 — Configure Gemini MCP](#-step-3--configure-gemini-mcp)
- [🔹 Step 4 — Restart Terminal](#-step-4--restart-terminal)
- [🔹 Step 5 — Verify MCP Connection](#-step-5--verify-mcp-connection)
- [🔹 Step 6 — Test GitHub MCP](#-step-6--test-github-mcp)
- [📸 Screenshot Placeholder](#-screenshot-placeholder)
- [💡 Reflection](#-reflection)

---

## 🔹 Step 1 — Create GitHub Personal Access Token (PAT)

1. Open:  
   **https://github.com/settings/personal-access-tokens/new**
2. Create a **Fine-Grained Personal Access Token** with:
   - ✔ `repo` (Read & Write)
3. Copy the token and keep it somewhere safe.

---

## 🔹 Step 2 — Save Token in `.env`

Create a new `.env` file and add: 

## 🔹 Step 3 — Configure Gemini MCP

Open or create the following file:

```bash
~/.config/gemini/settings.json
Paste this configuration:

json
Copy code
{
  "mcpServers": {
    "github": {
      "httpurl": "https://api.githubcopilot.com/mcp",
      "headers": {
        "Authorization": "Bearer $GITHUB_MCP_PAT"
      }
    }
  }
}
## 🔹 Step 4 — Restart Terminal

Close your terminal completely and reopen it.  
This reloads Gemini CLI with the new settings.

---

## 🔹 Step 5 — Verify MCP Connection

Run the following command:

```bash
gemini /mcp list
You should see output similar to:

java
Copy code
github   Ready   (90+ tools)

## 🔹 Step 6 — Test GitHub MCP

Ask Gemini:

List my GitHub repositories

yaml
Copy code

If everything is correct, Gemini will use MCP tools to fetch your GitHub repository list.

---

## 📸 Screenshot Placeholder

> *(Add your GitHub MCP connection screenshot here)*

---

## 💡 Reflection

Setting up GitHub MCP with Gemini using the hosted method showed me how powerful and simple modern AI integrations can be. With just a token and a configuration file, Gemini gained access to 90+ GitHub tools — without running any servers locally.

This task helped me understand:

- ✔ Secure token management  
- ✔ How hosted MCP servers work  
- ✔ How AI tools interact with GitHub repositories  
- ✔ Real-world automation powered by MCP technology



```bash
GITHUB_MCP_PAT=your_token_here
