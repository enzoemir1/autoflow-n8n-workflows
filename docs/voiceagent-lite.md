# VoiceAgent Lite — Call Logger

Log AI phone call data from Vapi.ai or Bland.ai to Google Sheets.

## How It Works

```
[Webhook] -> [Parse Call Data] -> [Log to Sheets]
```

1. **Receive Call Data** — Vapi.ai or Bland.ai sends call completion webhook
2. **Parse** — Extracts caller info, duration, transcript, and outcome
3. **Log** — Saves everything to Google Sheets

## Setup

1. Import `workflows/voiceagent-lite.json` into n8n
2. Add Google Sheets credentials
3. Create a sheet: Date, Caller, Duration, Transcript, Outcome
4. Copy the webhook URL from n8n
5. Paste it into your Vapi.ai or Bland.ai webhook settings
6. Activate

## Cost

Free — no AI API calls needed. Just logging.

## Lite vs Full

| Feature | Lite | Full |
|---------|------|------|
| Logging | Basic call data | Full transcript + AI summary |
| Analysis | No | Yes — sentiment analysis + key topics |
| Calendar | No | Yes — auto-book follow-up meetings |
| Alerts | No | Yes — Slack notification per call |
| Reports | No | Yes — weekly call analytics |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
