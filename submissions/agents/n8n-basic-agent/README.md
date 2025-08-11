# Hello OpenAI Agent (n8n)

A minimal n8n agent that:
- Exposes a POST webhook at `/webhook/hello-agent`
- Sends the user's `question` to OpenAI Chat Completions
- Returns a JSON response like `{ "answer": "..." }`

Uses the n8n HTTP Request node with `{{$env.OPENAI_API_KEY}}` so you don’t need to create n8n credentials.

## Prerequisites
- Docker and Docker Compose
- An OpenAI API key

## Quickstart (recommended)
1) Copy the example env file next to the compose file and set your key:
```bash
cp .env.example .env
# If your OS hides dotfiles, use the provided env.example instead:
# cp env.example .env
# edit .env and set OPENAI_API_KEY=...
```

2) Start the local stack from this folder:
```bash
docker compose up -d
# n8n UI: http://localhost:5678
```

3) Import the workflow into n8n:
- Open the n8n UI → Workflows → Import from File
- Select `workflow.hello-openai-agent.json`
- Toggle the workflow to Active

4) Test the webhook:
```bash
curl -X POST "http://localhost:5678/webhook/hello-agent" \
  -H "Content-Type: application/json" \
  -d '{"question":"Give me a one-sentence productivity tip."}'
```
Expected response:
```json
{"answer":"<model reply here>"}
```

## Notes
- Default model: `gpt-4o-mini` (change in the HTTP Request node body if desired)
- The compose file injects `OPENAI_API_KEY` into the n8n container environment
- Webhook URL when active: `http://localhost:5678/webhook/hello-agent`

## Troubleshooting
- If you get a 404 on the webhook, ensure the workflow is Active in n8n
- Check container logs: `docker compose logs -f n8n`
- Confirm the env var is visible in the container: the HTTP Request node header uses `Authorization: Bearer {{$env.OPENAI_API_KEY}}`
