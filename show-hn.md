# Show HN: AgentTool — Persistent Memory + Tool APIs for AI Agents

**Title:** Show HN: AgentTool – persistent memory, verified actions, and micro-billing for AI agents

**URL:** https://agenttool.dev

---

## Post body

Hi HN,

I built AgentTool after hitting the same wall every time I tried to build an AI agent that needed to *remember things between conversations* and *prove it did what it claimed*.

The problem: every agent project I started needed:
1. **Persistent memory** — store facts, retrieve them semantically, survive restarts
2. **Verified actions** — timestamped proofs that the agent actually did the thing
3. **Tool access** — web search, page scraping, code execution
4. **Usage limits** — so I don't accidentally bankrupt myself

All of these exist as parts of other systems, but there's no single API that gives you all four with a single key.

**What I built:**

- `POST /v1/memories` — store a memory with semantic embeddings, retrieve by similarity search
- `POST /v1/verify` — create a SHA-256 attestation of any agent action
- `GET /v1/search` — web search, scrape, browse, execute — the agent's hands
- `POST /v1/wallets` — micro-billing and credit transfer between agents

Free tier: 100 memory ops/day, 10 tool calls/day, 5 verifications/day. Paid plans from $29/mo.

The whole thing is one API key from [app.agenttool.dev](https://app.agenttool.dev). No config files, no infra to set up.

**60-second quickstart:**

```bash
# Store a memory
curl -X POST https://api.agenttool.dev/v1/memories \
  -H "Authorization: Bearer YOUR_KEY" \
  -H "Content-Type: application/json" \
  -d '{"agent_id": "my-agent", "content": "User prefers dark mode", "tags": ["preference"]}'

# Search it later
curl -X POST https://api.agenttool.dev/v1/memories/search \
  -H "Authorization: Bearer YOUR_KEY" \
  -d '{"query": "what does the user prefer?", "limit": 5}'
```

Python SDK: `pip install agenttool-sdk`
TypeScript SDK: `npm install @agenttool/sdk`

Happy to answer questions about the architecture. The memory service uses pgvector for semantic search, the verify service uses GPT-4o to assess claims against live web evidence, and the tool service wraps Google Search + Playwright.

---

## Checklist before posting
- [ ] Yu reviews and approves
- [ ] Post Tuesday–Thursday 9–11am EST for peak HN traffic
- [ ] Monitor comments for first hour, respond to every reply
- [ ] Have dashboard ready to handle signup spike
- [ ] Have docs ready (docs.agenttool.dev is live)
