# HR-ASSIST — Agentic HR Automation 🧭🤖

[![Release](https://img.shields.io/badge/release-v1.0.0-blue.svg)](#)
[![Python](https://img.shields.io/badge/python-3.10%2B-orange.svg)](#)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](#)
[![Issues](https://img.shields.io/github/issues/yourorg/hr-assist)](#)

> **HR ASSIST** is an *agentic* AI system designed to help HR teams automate routine workflows — onboarding, ticketing, meeting scheduling, leave management and more.  
> This repo contains the MCP **server** code used by the Claude Desktop MCP client.

---

## 📑 Table of contents
- [✨ Highlights](#-highlights)
- [🏗️ Architecture](#️-architecture)
- [⚙️ Setup](#️-setup)
- [🔧 Configuration](#-configuration)
- [🚀 Usage](#-usage)
- [📂 Examples](#-examples)
- [📖 Docs / GitHub Pages](#-docs--github-pages)

---

## ✨ Highlights
- Agentic workflows for HR automation (onboarding flow example included)
- MCP server with tools for email, ticketing, meetings, and leave requests
- Example config for Claude Desktop MCP client
- Can run locally or be deployed with GitHub Pages for styled docs

---

## 🏗️ Architecture (high level)

- `mcp` server exposes tools (Python functions decorated with `@mcp.tool()`)  
- Services:
  - **EmployeeManager** — CRUD + search and reporting  
  - **LeaveManager** — balances, history, apply/cancel  
  - **MeetingManager** — schedule/cancel/list meetings  
  - **TicketManager** — request/track equipment  
- Email integration via `EmailSender` (SMTP)  
- Seed utilities for demo/test data  

📌 *Diagram placeholder (add `docs/architecture.png` if available)*  

---

## ⚙️ Setup

> **Prerequisites:** Python 3.10+, pip, and optionally a virtualenv.

```bash
# clone
git clone https://github.com/yourorg/hr-assist.git
cd hr-assist

# create venv (recommended)
python -m venv .venv
source .venv/bin/activate    # macOS / Linux
.\.venv\Scripts\activate     # Windows

# install deps
pip install -r requirements.txt
```

## 🔧 Configuration
> **Update your claude_desktop_config.json with the mcpServers entry for HR Assist:
```
{
  "mcpServers": {
    "hr-assist": {
      "command": "C:\\Users\\mrs\\.local\\bin\\uv",
      "args": [
        "--directory",
        "C:\\code\\hr-assist",
        "run",
        "server.py"
      ],
      "env": {
        "EMAIL": "YOUR_EMAIL",
        "EMAIL_PWD": "YOUR_APP_PASSWORD"
      }
    }
  }
}
```

## 🚀 Usage
```

Start the MCP server:

uv run server.py


or:

python server.py


In Claude Desktop:

Click ➕

Select Add from hr-assist

Claude connects and exposes available tools

Try HR automation prompts:

“Onboard a new employee”

“List pending leave requests”

“Search employee by name”
```

## 📂 Examples
✅ Onboarding a new employee
Onboard a new employee:
- Name: Jane Doe
- Manager: Sarah Johnson
- Email: jane.doe@example.com

Tasks:
- Add to HRMS
- Send welcome email
- Notify manager
- Create tickets for laptop & ID card
- Schedule intro meeting

🔍 Search employees by name
Find employee by name: "John"

📋 Get direct reports
Show all direct reports of E001
