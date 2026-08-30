# Slack Slash-Command Task Creation

Turns a Slack slash command into a fully-formed Notion task with assignee and priority.

![n8n](https://img.shields.io/badge/-n8n-333?style=flat-square) ![Notion API](https://img.shields.io/badge/-Notion%20API-333?style=flat-square) ![Slack](https://img.shields.io/badge/-Slack-333?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-workflow-EA4B71?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

**[Open the visual project page →](./index.html)**

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Workflow](#workflow)
- [Tech Stack](#tech-stack)
- [Demo status](#demo-status)
- [Setup](#setup)
- [Repository Structure](#repository-structure)
- [Disclaimer](#disclaimer)

## Overview

**Trigger:** Webhook (Slack slash command payload)

Turns a Slack slash command into a fully-formed Notion task with assignee and priority.

### Key Features

- Free-text slash-command parsing
- Structured Notion task creation
- Inline Slack confirmation/error feedback

## Architecture

The diagram below represents the sanitized template flow. External services, credentials, and environment-specific identifiers must be configured before execution.

```mermaid
flowchart TD
    A["Slack command webhook"] --> B["Parse task, assignee, and priority"]
    B --> C["Create Notion task"]
    C --> D{"Creation succeeds?"}
    D -->|Yes| E["Confirm task in Slack"]
    D -->|No| F["Report failure in Slack"]
```

## Workflow

1. Slack command webhook receives the raw command text
2. Parse task name (quoted string), @assignee, and priority: tag
3. Create a Notion task with those properties and a To Do status
4. Confirm creation back in Slack, or report the failure

## Tech Stack

- n8n
- Notion API
- Slack

## Demo status

A configured live-run recording is not included yet. Credentials and service identifiers remain placeholders.


## Setup

1. Import `workflow/T11_Slack_Command_Task_Creation.json` into your n8n instance (**Workflows → Import from File**).
2. Replace every placeholder credential/URL in the workflow (e.g. `YOUR_..._API_KEY`, `YOUR_..._URL`) with your own service credentials.
3. Activate the workflow and point the relevant integration (webhook source, scheduled trigger, etc.) at the generated webhook URL.
4. Test with a sample payload before going live.

## Repository Structure

```text
.
├── index.html
├── README.md
├── LICENSE
├── .gitignore
└── workflow/
    └── T11_Slack_Command_Task_Creation.json
```


## Disclaimer

This workflow was built as a portfolio/template project to demonstrate n8n workflow automation and AI integration. API credentials and sensitive configuration have been removed before publication — replace all `YOUR_..._KEY` / `YOUR_..._URL` placeholders with your own before use.

---

Designed and engineered by

**Oyekola Ololade**

AI Systems & Integration Engineer

- LinkedIn: <http://linkedin.com/in/ololade-oyekola-5b1797397>
- Email: <oyekolaololade69@gmail.com>
