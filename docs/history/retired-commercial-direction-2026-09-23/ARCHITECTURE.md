# Retired historical document

Retired on 2026-09-23. Preserved from `ARCHITECTURE.md` for provenance only.
This is not an active instruction, task list, target, purchasing plan,
or permission to act. Current guidance lives at the original path.

---

# first-customer-push — Acquisition Architecture

**Goal:** First paying customer ($29/mo Seed plan) within 7 days of launch.
**Product:** agenttool.dev — agent-memory, agent-tools, agent-verify, agent-economy
**Live at:** api.agenttool.dev | app.agenttool.dev | docs.agenttool.dev

---

## The Target

**Primary persona:** Indie hacker / solo founder building an AI agent product.
- Needs persistent memory for their agent (most common pain)
- Budget: $0–$100/mo discretionary for infra tools
- Decision time: fast (<24h if they feel the pain)
- Discovery: HN, Reddit, Twitter, Discord, GitHub

**Secondary persona:** Startup eng building internal AI tooling.
- Same pain, larger budget
- Discovery: LinkedIn, Slack communities, word of mouth

---

## Acquisition Channels (priority order)

### 1. Show HN post — Hacker News (highest ROI, one-shot)
- Format: "Show HN: AgentTool — persistent memory + verified actions for AI agents"
- Timing: Tuesday–Thursday, 9–11am EST (peak HN traffic)
- Target: 100+ upvotes → first page → 500+ visitors → 20+ signups → 2–5 upgrades

### 2. Reddit — r/LocalLLaMA + r/LLMDevs
- 2 posts, different framing (technical vs product)
- r/LocalLLaMA: "Built a persistent memory API for local LLM agents"
- r/LLMDevs: "Agent infrastructure that handles memory + tool calls + billing"

### 3. Twitter/X thread
- 6-tweet thread: problem → solution → demo → code snippet → pricing → CTA
- Target: AI builders following @swyx, @karpathy, @simonw orbit

### 4. Discord outreach — Latent Space, AI Engineer, Buildspace
- Personal message, not spam: "I built X, here's why, want early feedback?"
- Direct offer: first month free if they give feedback

### 5. GitHub public SDK repos
- Publish agenttool-sdk Python + TypeScript as public repos under `agenttool` org
- README with clear quick-start
- Discoverable by searching "agent memory python" on GitHub

---

## Onboarding Sequence (after signup)

No email capture exists yet. Short-term: manual outreach to signups.
Medium-term: add email field to project creation flow.

### Welcome email (Day 0)
- Sent when: project created (needs webhook from dashboard)
- Content: "Here's your key, here's the 60-second quickstart, I'm Yu — reply if stuck"
- Personal tone, founder-sends-email feel

### Nudge email (Day 3)
- Sent when: user has < 10 API calls
- Content: "Noticed you haven't tried the API yet — here's the simplest possible snippet"

### Upgrade nudge (Day 7 or on limit hit)
- Sent when: user hits 80% of free tier limit
- Content: "You're getting close to the free limit — upgrade to Seed ($29/mo) for 100x more"

---

## Conversion Mechanics (already built, needs activation)

- ✅ Free tier (100 memory ops/day) — taste
- ✅ Billing enforcement (tierGate) — hard stop at limit
- ✅ Upgrade modal in dashboard → Stripe Checkout
- ✅ Stripe webhook → subscription activation
- ⬜ Email capture in project creation flow
- ⬜ Welcome email on signup
- ⬜ Limit-hit email (requires email infra)

---

## Metrics to Track

| Metric | Target (Week 1) |
|--------|----------------|
| Landing page visits | 500 |
| Projects created | 50 |
| Active API callers | 20 |
| Paid conversions | 1–3 |
| MRR | $29–$87 |

---

## Execution Order

1. **Show HN post** — write and schedule (highest ROI, do first) [DONE: show-hn.md]
2. **Reddit posts** — two posts, two communities [DONE: reddit-posts.md]
3. **Twitter thread** — 6 tweets [DONE: twitter-thread.md]
4. **GitHub SDK repos** — create public org + repos with good READMEs
5. **Email capture** — add email field to index.html project creation form
6. **Welcome email** — simple Cloudflare Worker that sends on project create

Yu to review and approve before any post goes live.
