# AI Automation Workflows — Production-Style n8n Automations Powered by AI

![n8n](https://img.shields.io/badge/Platform-n8n-EA4B71.svg)
![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991.svg)
![Type](https://img.shields.io/badge/Type-Workflow%20JSON%20Exports-blue.svg)

A curated collection of **n8n workflow exports (JSON)** that combine AI agents, LLM chat models, vector stores, and everyday business tools — webhooks, email, Google Sheets/Docs/Drive, Supabase, Slack, and CRMs — to automate real operational tasks: HR onboarding, lead qualification, a voice agent, revenue/signal monitoring, and more.

## Overview

Each file in this repository is a complete, importable n8n workflow. Together they demonstrate practical workflow engineering patterns:

- **Event-driven design** — webhook and MCP-server triggers that react to incoming signals
- **AI decision steps** — OpenAI chat models and AI agents that analyze, qualify, or draft content
- **Structured routing** — AI output is parsed into structured data and routed to actions (Slack alert, CRM task, escalation, support ticket, email)
- **Tool integration** — Google Sheets, Google Docs, Google Drive, Supabase, Pinecone vector store, and email nodes

## Workflows Included

| File | What it does |
|---|---|
| `hr_automation_workflow.json` | HR onboarding automation — webhook receives employee data, an OpenAI step processes it, and a welcome email is sent |
| `lead_qualification_generation.json` | Lead qualification & content generation — AI agent with OpenAI, Supabase read/write, and Google Docs/Sheets tools |
| `ai_voice.json` | AI voice/restaurant agent — AI agent backed by OpenAI embeddings, a Pinecone vector store, and a Google Sheets menu tool |
| `email_sender.json` | Reusable email-sender sub-workflow — triggered by other workflows, pulls files from Google Drive, and sends email |
| `AI Contract & Policy Watchdog.json` | Signal → action pipeline — an AI signal analyzer routes contract/policy signals to Slack, a CRM task, management escalation, or a support ticket |
| `Revenue Leak Detector.json` | Signal → action pipeline focused on revenue-leak signals, using the same analyzer-and-routing pattern |
| `HR Employee Risk & Engagement Monitor.json` | Signal → action workflow for HR risk/engagement signals |
| `AI-Powered “Signal → Action” Decision Engine.json` | The generic decision-engine version of the signal-analysis and routing pattern |
| `Smart CV → Job → Interview Auto-Pipeline.json` | Signal → action workflow applied to a CV-to-interview hiring pipeline |
| `Reddit MCP Server Workflow.json` | An MCP server workflow exposing Reddit operations (create/get/delete posts and comments) to MCP clients |

## Tech Stack

- **n8n** — workflow automation platform (all files are standard n8n export JSON)
- **OpenAI** — chat models, embeddings, and AI agent nodes
- **Pinecone** — vector store for the voice-agent knowledge base
- **Supabase** — database read/write in the lead workflow
- **Google Workspace tools** — Sheets, Docs, Drive
- **Slack, email (SMTP), webhooks, and MCP** — triggers, notifications, and actions

## Project Structure

```
AI_Automation_workflow/
├── hr_automation_workflow.json
├── lead_qualification_generation.json
├── ai_voice.json
├── email_sender.json
├── AI Contract & Policy Watchdog.json
├── Revenue Leak Detector.json
├── HR Employee Risk & Engagement Monitor.json
├── AI-Powered “Signal → Action” Decision Engine.json
├── Smart CV → Job → Interview Auto-Pipeline.json
└── Reddit MCP Server Workflow.json
```

## Getting Started

### Prerequisites

- A running **n8n** instance (self-hosted or n8n Cloud)
- Accounts/API keys for the services a given workflow uses (e.g. OpenAI, and Google/Supabase/Slack/Pinecone where applicable)

### Import a workflow

1. Open n8n → **Workflows** → **Import from File** (or paste the JSON).
2. Select any `.json` file from this repository.
3. Open each node with a warning badge and connect your own credentials (exports never contain working secrets).
4. Activate the workflow and call its webhook/production URL where the workflow is webhook-triggered.

## Usage

Start with `hr_automation_workflow.json` for the clearest end-to-end example (webhook → AI → email), then explore the **Signal → Action** family to see how one analyzer-and-routing template is adapted to contracts, revenue, HR risk, and hiring. Use `email_sender.json` as a shared sub-workflow called by other automations.

## Author

**Muhammad Dawood** — AI & Data Science Engineer
- GitHub: https://github.com/datascientist970
- Location: Mardan, Pakistan

## License

This project is shared for learning and portfolio purposes. Add a license file before reusing it commercially.
