<p align="center">
  <h1 align="center">AutoFlow — Free AI Automation Workflows for n8n</h1>
  <p align="center">
    8 ready-to-import workflow templates that automate content, sales, support, email, and more.
    <br />
    Built by <a href="https://automatiabcn.com">Automatia BCN</a> · Barcelona
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/workflows-8-00D9FF?style=for-the-badge" alt="8 Workflows">
  <img src="https://img.shields.io/badge/platform-n8n-FF6D5A?style=for-the-badge" alt="n8n">
  <img src="https://img.shields.io/badge/AI-OpenAI%20gpt--4o--mini-10B981?style=for-the-badge" alt="OpenAI">
  <img src="https://img.shields.io/badge/cost-free-FFD700?style=for-the-badge" alt="Free">
</p>

---

## What's Included

| # | Workflow | What It Does | API Cost |
|---|---------|-------------|----------|
| 1 | **FlowScribe Lite** | 1 blog post → 4 platform posts (Twitter, LinkedIn, Instagram, Facebook) | ~$0.01/run |
| 2 | **LeadPilot Lite** | Paste leads → AI writes personalized cold emails | ~$0.005/lead |
| 3 | **SupportFlow Lite** | Simple AI chatbot (answers from your company info) | ~$0.002/msg |
| 4 | **InboxZero Lite** | Classifies Gmail emails as urgent / important / info / spam | ~$0.002/email |
| 5 | **SocialPulse Lite** | Monitors Reddit for trending posts + AI analysis | ~$0.03/scan |
| 6 | **ClientFlow Lite** | Client form → welcome email + Google Sheets pipeline | ~$0.003/client |
| 7 | **DataForge Lite** | POST any URL → AI extracts structured data | ~$0.003/page |
| 8 | **VoiceAgent Lite** | Logs phone calls from Vapi.ai/Bland.ai to Sheets | Free |

---

## Quick Start

### 1. Download a workflow
Click any `.json` file in the [`workflows/`](./workflows) folder and download it (or clone this repo).

### 2. Import into n8n
```
n8n → Workflows → Import from File → select the JSON
```

### 3. Connect your credentials
Most workflows need:
- **OpenAI API key** (gpt-4o-mini — [get one here](https://platform.openai.com/api-keys))
- **Google Sheets** (OAuth in n8n)

Some also need Gmail (InboxZero, ClientFlow).

### 4. Activate
Toggle the workflow active and test it. Each workflow has **Sticky Notes** inside explaining what every node does.

---

## Requirements

| Requirement | Details |
|------------|---------|
| **n8n** | Cloud or self-hosted ([n8n.io](https://n8n.io)) |
| **OpenAI API** | gpt-4o-mini, ~$0.002-0.01 per call ([platform.openai.com](https://platform.openai.com)) |
| **Google Sheets** | Free Google account |
| **Gmail** | For InboxZero + ClientFlow only |

All workflows use the most cost-effective API options. No expensive models required.

---

## Workflow Details

### FlowScribe Lite — Content Repurposing
Send a blog post via webhook → AI generates optimized content for 4 platforms in parallel → saves to Google Sheets.

**Input:**
```json
{
  "title": "Your Article Title",
  "content": "Your full article text...",
  "brand_voice": "professional yet approachable"
}
```

**Output:** Twitter thread (5-7 tweets) + LinkedIn post + Instagram caption (with hashtags) + Facebook post.

---

### LeadPilot Lite — Cold Email Writer
POST a list of leads → AI writes a personalized cold email + follow-up for each → saves to Sheets.

**Input:**
```json
{
  "leads": [
    { "name": "Jane Smith", "email": "jane@company.com", "title": "CTO", "company": "TechCo" }
  ],
  "sender_name": "Your Name",
  "value_prop": "We help companies automate workflows."
}
```

---

### SupportFlow Lite — AI Chatbot
Simple chatbot that answers customer questions using your company info (set via environment variable). No vector database needed.

---

### InboxZero Lite — Email Classifier
Polls Gmail every 5 minutes, classifies each new email into: urgent, important, informational, or spam. Logs to Sheets.

---

### SocialPulse Lite — Reddit Monitor
Fetches hot posts from a subreddit daily, ranks by engagement, AI identifies trends + suggests content ideas.

---

### ClientFlow Lite — Client Onboarding
Webhook receives client form data → sends welcome email via Gmail → logs to Google Sheets pipeline.

---

### DataForge Lite — URL Data Extractor
POST a URL + fields to extract → fetches page → AI extracts structured data → returns JSON.

```bash
curl -X POST YOUR_WEBHOOK \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com/pricing", "extract_fields": "plans,price,features"}'
```

---

### VoiceAgent Lite — Call Logger
Receives call data from Vapi.ai or Bland.ai webhook → logs caller, duration, transcript to Sheets.

---

## Full Versions

These are Lite versions of our **AutoFlow** product line. Each full version adds:

- More platforms / sources / integrations
- A/B testing and advanced analytics
- Complete documentation (6 guides per product)
- Bonus templates and examples
- Priority support

| Product | Price | What's Added |
|---------|-------|-------------|
| FlowScribe | $79 | 8 platforms + A/B testing + posting schedule |
| LeadPilot | $99 | Apollo.io search + AI scoring + auto-send |
| SupportFlow | $129 | RAG chatbot (Pinecone) + human handoff + chat widget |
| InboxZero | $79 | Auto-actions + draft replies + daily digest |
| SocialPulse | $89 | Reddit + HN + Dev.to + weekly reports |
| ClientFlow | $99 | Stripe invoice + Calendar + 7-day follow-up |
| DataForge | $129 | Batch scraping + change tracking + market reports |
| VoiceAgent | $149 | AI call analysis + Calendar booking + Slack alerts |

**Browse all products:** [automatiabcn.gumroad.com](https://automatiabcn.gumroad.com)

---

## About Automatia BCN

We're a Barcelona-based studio building AI automation products.

- **Website:** [automatiabcn.com](https://automatiabcn.com)
- **Products:** [automatiabcn.gumroad.com](https://automatiabcn.gumroad.com)
- **Twitter/X:** [@automatiabcn](https://x.com/automatiabcn)
- **Email:** support@automatiabcn.com

---

## License

These workflow templates are free to use for personal and commercial purposes. You may modify them for your own use. You may not resell or redistribute the files themselves.

Full product versions have their own license terms.

---

**If these workflows save you time, consider giving this repo a ⭐**
