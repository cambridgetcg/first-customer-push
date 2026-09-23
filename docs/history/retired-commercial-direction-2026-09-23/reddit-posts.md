# Retired historical document

Retired on 2026-09-23. Preserved from `reddit-posts.md` for provenance only.
This is not an active instruction, task list, target, purchasing plan,
or permission to act. Current guidance lives at the original path.

---

# Reddit Posts

---

## Post 1: r/LocalLLaMA

**Title:** Built a persistent memory API for local LLM agents — one endpoint, semantic search, free tier

**Body:**

Been building local LLM agents and kept hitting the same problem: memory dies when the process restarts, and there's no easy way to do semantic retrieval across past conversations.

Built a simple REST API for this: `POST /v1/memories` stores with embeddings, `POST /v1/memories/search` retrieves by semantic similarity.

```python
import requests

API = "https://api.agenttool.dev"
KEY = "your_key"

# Store
requests.post(f"{API}/v1/memories",
    headers={"Authorization": f"Bearer {KEY}"},
    json={"agent_id": "my-agent", "content": "User said they're vegetarian", "tags": ["diet"]})

# Retrieve
results = requests.post(f"{API}/v1/memories/search",
    headers={"Authorization": f"Bearer {KEY}"},
    json={"query": "dietary restrictions", "limit": 5})
```

Works with any local model — just call the API from your agent loop. Free tier is 100 ops/day, no credit card needed.

`pip install agenttool-sdk` if you want the Python wrapper.

Site: agenttool.dev, feedback welcome.

---

## Post 2: r/LLMDevs (or r/MachineLearning)

**Title:** I built the API layer I wish existed when I started building AI agents (memory + verification + tools)

**Body:**

Every AI agent project needs the same boring infrastructure: somewhere to store memories, a way to prove the agent did what it claimed, and tools it can actually use. I kept rebuilding this from scratch.

So I built AgentTool — four APIs, one key:

**agent-memory:** Persistent semantic memory. Store facts, retrieve by similarity. Survives restarts.

**agent-verify:** Proof-of-work for agents. Create SHA-256 attestations with timestamps. Useful when your agent needs to prove it completed a task.

**agent-tools:** Web search, page scraping, code execution. The agent's hands.

**agent-economy:** Wallets and micro-billing. Agents can charge each other for services.

Free tier on everything. Dashboard at app.agenttool.dev.

What's your current solution for agent memory? Curious if people are rolling their own or using something I haven't found.

---

## Checklist
- [ ] Yu approves both posts
- [ ] Post r/LocalLLaMA first, gauge reaction
- [ ] Post r/LLMDevs 2 days later (so not same-day spam)
- [ ] Reply to every comment within 1 hour
