<p align="center">
  <a href="https://dcision.io">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/DcisionIO/.github/main/assets/banner-dark.png">
      <img alt="Dcision — the decision layer for AI" src="https://raw.githubusercontent.com/DcisionIO/.github/main/assets/banner-light.png" width="100%">
    </picture>
  </a>
</p>

<p align="center">
  <a href="https://app.dcision.io"><img alt="Start free" src="https://img.shields.io/badge/start%20free-1M%20decisions%2Fmonth-34d399?style=for-the-badge"></a>
  <a href="https://docs.dcision.io"><img alt="Docs" src="https://img.shields.io/badge/docs-docs.dcision.io-111827?style=for-the-badge"></a>
  <a href="https://x.com/dcisionio"><img alt="Follow on X" src="https://img.shields.io/badge/follow-%40dcisionio-111827?style=for-the-badge&logo=x"></a>
</p>

<p align="center"><b>Decide first. Reason when it matters.</b><br>
Send any state, get typed answers with a confidence for each — and the next action — before your agent or LLM runs.</p>

---

## ✨ Why Dcision

| | |
| --- | --- |
| 🧭 **Use it before the LLM** | Classify, score and route every event first. The expensive reasoning only runs on the cases that need it. |
| ✂️ **Not everything needs an LLM** | Routing a ticket or flagging a transaction is a microdecision, not an essay: answer it with a typed decision instead of a prompt and free text. |
| 🧱 **No hallucinated labels** | Every answer is one of your options, a score or a probability, validated against your schema before it reaches your code. Low confidence? Your policy escalates, blocks or falls back. |
| ⚡ **One call, many questions** | All the questions of a decision are answered in a single call to the engine — extra questions add little latency. |
| 🤖 **Built for machine-to-machine** | Typed JSON in, typed JSON out — the format APIs, agents, workflows and automations already speak. |
| 🎯 **An action for every answer** | Per option, level or threshold: call an agent, an LLM, an API, a workflow or a webhook — or reply right away with a fixed text. No glue code. |
| 📊 **Managers in control** | Every run is logged with its version, confidence and action. Tune options and thresholds in the visual builder and deploy a new version — no app redeploy. |

## 🔁 How it works

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/DcisionIO/.github/main/assets/flow-dark.png">
  <img alt="An agent without Dcision spends an LLM call and parses free text to pick the next action; with Dcision a typed answer with confidence picks it — calling an agent, LLM, API, workflow, webhook or function, or answering directly" src="https://raw.githubusercontent.com/DcisionIO/.github/main/assets/flow-light.png" width="100%">
</picture>

1. **Send the state** — any event, message or JSON context from your app or agent.
2. **Define decisions** — choice, score and probability questions in a versioned Decision Schema.
3. **Run** — Dcision validates the state and answers every question in one call.
4. **Act** — typed answers plus an action (`continue`, `block`, `escalate`, `fallback`) and the destinations you set per result.

## 🚀 Quickstart — your first decision in 5 minutes

1. **Sign up** at [app.dcision.io](https://app.dcision.io) (Google or an e-mail code). You get the free **Genesis** plan: 1M decisions a month.
2. **Create a decision** from a template — *Lead Qualification*, *Support Routing*, *Spam Detection*… — and test it in the **Playground** (Playground runs are free).
3. **Deploy** it and create an **API key** (`API keys → New key`).
4. **Call it:**

```bash
export DCISION_API_KEY=dcs_live_...

curl -X POST https://api.dcision.io/v1/decisions/lead-qualification \
  -H "Authorization: Bearer $DCISION_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"state": {"message": "We need pricing for 500 users and want to start next month.", "company_size": 500, "source": "website"}}'
```

```jsonc
{
  "result":     { "purchase_intent": 0.9412, "priority": "high", "route": "sales" },
  "confidence": { "purchase_intent": 0.8824, "priority": 0.69, "route": 0.85 },
  "action": "continue",
  "action_reason": { "type": "default" }
  // + decision_id, execution_id, version, composites, metrics…
}
```

## 🔌 Use it from anywhere

| Where | How |
| --- | --- |
| **Any language** | `POST https://api.dcision.io/v1/decisions/{slug}` with your API key — [cURL, Node.js and Python examples](https://github.com/DcisionIO/examples) |
| **No-code / CRMs / forms** | Turn on the decision's **webhook URL** and call it from n8n, Make, Zapier or any form — no API key needed. [Docs](https://docs.dcision.io/docs/api/webhook-trigger) |
| **AI agents (MCP)** | Remote MCP server at `https://api.dcision.io/mcp` |
| **Claude Code** | MCP + a ready-made skill (below) |
| **TypeScript / Python SDKs · CLI** | Coming soon |

**Connect Claude Code** (MCP):

```bash
claude mcp add --transport http dcision https://api.dcision.io/mcp \
  --header "Authorization: Bearer $DCISION_API_KEY" --scope user
```

**Install the Dcision skill** (Claude Code and other agents that read `SKILL.md`):

```bash
mkdir -p ~/.claude/skills/dcision
curl -fsSL https://docs.dcision.io/skills/dcision/SKILL.md -o ~/.claude/skills/dcision/SKILL.md
```

## 🧩 Ready-made decisions

Lead qualification · support routing · spam detection · agent routing · RAG relevance · ticket triage · voice banking commands · resume screening · customer-service router — schemas and sample states in **[DcisionIO/examples](https://github.com/DcisionIO/examples)**.

## 💳 Pricing in one line

**Genesis is free** — 1M decisions a month. Past the included volume, every plan keeps running on prepaid credits — and adding a card gives you **$20 in free credits** (valid 90 days). Details at [dcision.io](https://dcision.io/en#pricing).

---

<p align="center">
  <a href="https://dcision.io"><b>dcision.io</b></a> · <a href="https://docs.dcision.io">Docs</a> · <a href="https://app.dcision.io">App</a> · <a href="https://x.com/dcisionio">X</a> · <a href="mailto:contact@dcision.io">contact@dcision.io</a>
</p>
