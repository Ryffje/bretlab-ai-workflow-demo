# BretLab AI Workflow Demo

AI workflow orchestrator built with n8n, OpenAI (GPT-4) and Supabase.

This project demonstrates an event-driven architecture capable of receiving user messages via webhook, processing them through a structured LLM pipeline, routing logic dynamically based on detected intent, querying a database, and generating formatted responses.

---

## Overview

The system is designed to:

- Receive incoming messages through a webhook
- Normalize and persist conversation history in Supabase
- Build contextual prompts dynamically
- Generate structured JSON output using GPT-4
- Route execution based on detected intent
- Fetch relevant workers from the database
- Format and return a final response via webhook

This repository focuses on workflow orchestration and system design rather than frontend implementation.

---

## Architecture

Webhook  
→ Normalize Input  
→ Persist Message (Supabase)  
→ Fetch Conversation History  
→ Build Prompt  
→ GPT-4 (Structured JSON Output)  
→ Router Logic  
→ Intent-Based Switch  
→ Fetch Workers (Supabase)  
→ Format Response  
→ Send Webhook Response  

---

## Key Features

- Structured LLM output with strict JSON schema
- Intent detection and next-step routing
- Database persistence using Supabase
- Dynamic worker filtering by skill and location
- Event-driven orchestration using n8n
- Separation of responsibilities within the workflow

---

## Screenshots

### Workflow Overview
![Architecture](./screenshots/01-architecture-workflow-overview.png)

### Webhook Trigger (Postman)
![Webhook Trigger](./screenshots/02-webhook-trigger-postman.png)

### GPT Node Configuration
![LLM Config](./screenshots/03-llm-node-config-json-output.png)

### Structured LLM Output
![LLM Output](./screenshots/04-llm-structured-output-intent.png)

### Routing and Switch Logic
![Routing](./screenshots/05-router-switch-branches.png)

### Supabase Message Persistence
![Supabase Insert](./screenshots/06-supabase-insert-messages.png)

### Supabase Worker Fetch
![Supabase Fetch](./screenshots/07-supabase-fetch-workers.png)

### Formatted Worker Response
![Formatted Response](./screenshots/08-formatted-workers-response.png)

### Final Webhook Response
![Final Response](./screenshots/09-webhooksite-final-response.png)

---

## Example Test Payload

```json
{
  "body": {
    "sender": "demo_user",
    "username": "demo_user",
    "message": "Necesito un cerrajero en San Ramón",
    "conversationId": "1",
    "channel": "Channel::WhatsApp"
  }
}
```

---

## Environment Variables

See `.env.example` for required configuration values.

---

## Security Notes

- API keys and tokens have been removed.
- Workflow JSON has been sanitized.
- This repository is for demonstration purposes only.

---

## Technologies

- n8n
- OpenAI (GPT-4)
- Supabase
- Postman
- Webhook.site

---

## Author

Jeffry León  
Full Stack Developer | Linux & Workflow Automation