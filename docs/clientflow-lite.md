# ClientFlow Lite — Client Onboarding

Automate new client onboarding: form submission to welcome email + pipeline log in 10 seconds.

## How It Works

```
[Webhook] -> [Validate Client] -> [AI: Generate Welcome Email] -> [Send via Gmail] -> [Log to Sheets]
```

1. **Form Submission** — Any form tool (Typeform, Google Forms, Tally) sends data to webhook
2. **Validate** — Checks required fields (name, email), generates client ID
3. **AI Email** — GPT-4o-mini writes a personalized welcome email
4. **Send** — Sends the welcome email via Gmail
5. **Log** — Records client details in Google Sheets pipeline

## Setup

1. Import `workflows/clientflow-lite.json` into n8n
2. Add OpenAI credentials
3. Add Gmail credentials
4. Add Google Sheets credentials
5. Create a sheet: Date, Client ID, Name, Email, Company, Project, Status
6. Connect your form tool to the webhook URL
7. Test by submitting the form

## Cost

About $0.003 per client (AI email generation). The Gmail send is free.

## Lite vs Full

| Feature | Lite | Full |
|---------|------|------|
| Welcome Email | AI-generated | AI-generated + branded HTML template |
| Invoice | No | Yes — auto-creates Stripe invoice |
| Calendar | No | Yes — books kick-off call via Google Calendar |
| Follow-up | No | Yes — 7-day automated follow-up sequence |
| CRM | Google Sheets | Google Sheets + HubSpot sync |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
