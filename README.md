# HR-ASSIST — Agentic HR Automation 🧭🤖

[![Release](https://img.shields.io/badge/release-v1.0.0-blue.svg)](#)
[![Python](https://img.shields.io/badge/python-3.10%2B-orange.svg)](#)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](#)
[![Issues](https://img.shields.io/github/issues/yourorg/hr-assist)](#)

> **HR ASSIST** is an *agentic* AI system designed to help HR teams automate routine workflows — onboarding, ticketing, meeting scheduling, leave management and more. This repo is the MCP **server** code used by the Claude Desktop MCP client.

---

## Table of contents
- [Highlights](#highlights)
- [Architecture](#architecture)
- [Setup](#setup)
- [Configuration](#configuration)
- [Usage](#usage)
- [Examples](#examples)
- [Docs / GitHub Pages](#docs--github-pages)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Highlights
- Agentic workflows for HR automation (onboarding flow example included)
- MCP server with tools for email, ticketing, meetings, and leave requests
- Simple example config for Claude Desktop MCP client
- Can run locally or be published to GitHub Pages for styled docs

---

## Architecture (high level)
- `mcp` server exposes tools (Python functions decorated with `@mcp.tool()`) that the MCP client (Claude Desktop) calls.
- Services:
  - `EmployeeManager` — CRUD + search and reporting
  - `LeaveManager` — balances, history, apply/cancel
  - `MeetingManager` — schedule/cancel/list meetings
  - `TicketManager` — request/track equipment
- Email integration via `EmailSender` (SMTP)
- Seed utilities for demo/test data

---

## Setup

> Prerequisites: Python 3.10+, pip, and optionally a virtualenv.

```bash
# clone
git clone https://github.com/yourorg/hr-assist.git
cd hr-assist

# create venv (optional but recommended)
python -m venv .venv
source .venv/bin/activate    # macOS / Linux
.\.venv\Scripts\activate     # Windows

# install
pip install -r requirements.txt
