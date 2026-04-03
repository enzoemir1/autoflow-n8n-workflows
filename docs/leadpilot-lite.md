# LeadPilot Lite — AI Cold Email Writer

Generate personalized cold emails for your leads using AI.

## How It Works

```
[Webhook] → [Validate Leads] → [AI: Research + Write Email] → [Save to Sheets] → [Return Results]
```

1. **Receive Leads** — POST a list of leads (name, email, title, company)
2. **Validate** — Checks required fields, generates unique IDs
3. **AI Research** — GPT-4o-mini analyzes each lead's role and company
4. **AI Write** — Generates a personalized cold email + follow-up for each lead
5. **Save** — All emails saved to Google Sheets
6. **Return** — JSON with all generated emails

## Setup

1. Import `workflows/leadpilot-lite.json` into n8n
2. Add OpenAI credentials
3. Add Google Sheets credentials
4. Create a sheet with columns: `Date | Name | Email | Company | Subject | Body | Follow-up`
5. Activate and test:

```bash
curl -X POST https://your-n8n-instance/webhook/leadpilot-lite \
  -H "Content-Type: application/json" \
  -d '{
    "leads": [
      {
        "name": "Sarah Chen",
        "email": "sarah@example.com",
        "title": "CTO",
        "company": "TechStartup Inc"
      }
    ],
    "sender_name": "Your Name",
    "sender_company": "Your Company",
    "value_prop": "We help companies automate workflows and save 10+ hours/week"
  }'
```

## Cost

~$0.005 per lead. Processing 100 leads costs approximately $0.50.

## Lite vs Full Version

| Feature | Lite (Free) | Full |
|---------|------------|------|
| Lead Source | Manual input | Apollo.io auto-search |
| AI Scoring | No | Yes — scores lead quality 1-10 |
| Auto-Send | No | Yes — sends via Gmail/SendGrid |
| Follow-up | 1 follow-up | 3-email sequence with timing |
| CRM Sync | No | Yes — HubSpot/Sheets |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
