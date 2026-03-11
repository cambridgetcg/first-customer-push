# Twitter/X Thread

**Account:** @agenttool (to be created) or Yu's personal account

---

**Tweet 1 (hook):**
Every AI agent I built needed the same 4 things:
- Persistent memory between sessions
- Proof it actually did something
- Real tools (search, scrape, execute)
- Usage limits so it doesn't bankrupt me

So I built the API layer. 🧵

---

**Tweet 2 (memory):**
agent-memory: One endpoint for persistent semantic memory.

```
POST /v1/memories — store with embeddings
POST /v1/memories/search — retrieve by similarity
```

No vector DB to configure. No pgvector to run. Just your API key.

Free tier: 100 ops/day

---

**Tweet 3 (verify):**
agent-verify: Proof-of-work for agents.

When your agent completes a task, create a SHA-256 attestation with a timestamp. Verifiable by anyone. No blockchain needed (optional anchoring available).

Useful when agents report back to humans — or to each other.

---

**Tweet 4 (tools):**
agent-tools: Web search, scraping, browser automation, code execution.

The boring infrastructure so your agent can actually *do things* in the world.

Brave Search API + Playwright under the hood. You call one endpoint.

---

**Tweet 5 (economy):**
agent-economy: Wallets and micro-billing for agents.

Agents can:
- Hold credits
- Charge other agents for services
- Settle via Stripe

If you're building agent-to-agent marketplaces, this is the payment rail.

---

**Tweet 6 (CTA):**
It's live. One API key for all four.

Free tier, no credit card. Paid from $29/mo.

→ app.agenttool.dev (dashboard + API key)
→ docs.agenttool.dev (full reference)
→ pip install agenttool-sdk

What are you building? 👇

---

## Checklist
- [ ] Yu approves thread
- [ ] Post Tuesday–Thursday morning
- [ ] Reply to every reply in first 2 hours
- [ ] Quote-tweet if someone shares something interesting
