# InboxZero Lite — Email Classifier

Automatically classify incoming Gmail emails into urgent, important, informational, or spam.

## How It Works

```
[Gmail Poll] -> [AI: Classify Email] -> [Log to Google Sheets]
```

1. **Poll Gmail** — Checks for new emails every 5 minutes
2. **AI Classify** — GPT-4o-mini categorizes each email: urgent, important, informational, spam
3. **Log** — Saves sender, subject, category, and AI reasoning to Google Sheets

## Setup

1. Import `workflows/inboxzero-lite.json` into n8n
2. Add OpenAI credentials
3. Add Gmail credentials (OAuth2)
4. Add Google Sheets credentials
5. Create a sheet: Date, From, Subject, Category, Reasoning
6. Activate — it runs automatically every 5 minutes

## Cost

About $0.002 per email. 500 emails/month costs approximately $1.

## Lite vs Full

| Feature | Lite | Full |
|---------|------|------|
| Classification | 4 categories | 4 categories + custom labels |
| Auto-actions | No | Yes — Slack alerts, draft replies, auto-archive |
| Daily Digest | No | Yes — morning summary email |
| Rules | No | Yes — custom classification rules |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
