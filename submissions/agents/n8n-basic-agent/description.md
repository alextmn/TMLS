# n8n Basic Agent (Hello OpenAI Agent)

## Summary
A tiny, reproducible n8n agent demonstrating a simple pattern: chat → agent → tools → response. It uses the n8n Chat Trigger to receive messages, an OpenAI Chat Model as the LLM, a short-term Buffer Window memory, and a simple Code Tool (uppercases text) that the agent can invoke.

## Use Cases
- Boilerplate for new chat-based AI agents in n8n
- Base for adding retrieval, more tools, or routing
- Demo for chat-to-agent orchestration

## Architecture / Approach
- Chat Trigger: receives user messages from the n8n chat panel
- OpenAI Chat Model: LLM (default `gpt-4o-mini`)
- AI Agent: LangChain Agent that decides when to call tools
- Simple Memory: buffer window memory for short-term context
- Code Tool: a simple tool to uppercase text

## Setup & Run
1. From this folder, run `docker compose up -d`
2. Open n8n (`http://localhost:5678`), create an OpenAI credential, and paste your API key
3. Import `workflow.hello-openai-agent.json`
4. Open the `OpenAI Chat Model` node and select your credential
5. Activate the workflow and use the Chat panel to converse with the agent

## Configuration
- Model: set in the `OpenAI Chat Model` node (defaults to `gpt-4o-mini`)
- Memory: adjust the `Simple Memory` window as needed
- Tools: extend the `Code Tool` or add more tools for richer behaviors

## Security, Privacy & Ethics
- Store API keys in n8n credentials, not in workflows
- Avoid sending sensitive data to third-party APIs
- Document model limitations for production scenarios

## Performance & Limitations
- Short-term memory only; no vector retrieval
- No retry/backoff or streaming by default

## References & Credits
- OpenAI Chat Completions via n8n OpenAI Chat Model node
- n8n Chat Trigger, Agent, Memory, and Tool nodes
