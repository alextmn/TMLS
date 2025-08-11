# Hello OpenAI Agent

## Summary
A tiny, reproducible n8n agent demonstrating a simple pattern: webhook → LLM call → JSON response. No n8n credential objects are required; the HTTP Request node reads `OPENAI_API_KEY` from the container environment.

## Use Cases
- Boilerplate for new AI agents
- Base for adding retrieval, tools, or routing
- Demo for webhook-to-LLM pattern

## Architecture / Approach
- Webhook (POST `/webhook/hello-agent`): receives `{ question }`
- HTTP Request: POST to OpenAI Chat Completions using `{{$env.OPENAI_API_KEY}}`
- Function: map OpenAI response to `{ answer }`
- Respond to Webhook: returns final JSON

## Setup & Run
1. Copy `.env.example` to `.env` and set `OPENAI_API_KEY`
2. From this folder, run `docker compose up -d`
3. Open n8n (`http://localhost:5678`), import `workflow.hello-openai-agent.json`, and activate it
4. POST to `http://localhost:5678/webhook/hello-agent`

## Configuration
- `OPENAI_API_KEY` (required)
- `model` (in the HTTP Request JSON body; defaults to `gpt-4o-mini`)

## Security, Privacy & Ethics
- No secrets in repo; uses environment variable
- Do not send sensitive data to third-party APIs
- Document model limitations for production scenarios

## Performance & Limitations
- Stateless (no memory)
- No retry/backoff or streaming

## References & Credits
- OpenAI Chat Completions API
- n8n HTTP Request, Webhook, Respond to Webhook nodes
