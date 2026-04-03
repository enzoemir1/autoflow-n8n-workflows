# SocialPulse Lite — Reddit Trend Monitor

Monitor any subreddit for trending topics and get AI-powered content ideas.

## How It Works

```
[Daily Schedule] -> [Fetch Reddit Posts] -> [AI: Analyze Trends] -> [Save to Sheets]
```

1. **Daily Trigger** — Runs once per day at your chosen time
2. **Fetch Posts** — Gets hot posts from your target subreddit (no API key needed)
3. **AI Analysis** — GPT-4o-mini identifies trends and suggests content ideas
4. **Save** — Logs trends and suggestions to Google Sheets

## Setup

1. Import `workflows/socialpulse-lite.json` into n8n
2. Add OpenAI credentials
3. Add Google Sheets credentials
4. Set the target subreddit in the HTTP Request node (default: r/n8n)
5. Activate

## Cost

About $0.03 per daily scan. Running daily costs approximately $0.90/month.

## Lite vs Full

| Feature | Lite | Full |
|---------|------|------|
| Sources | Reddit only | Reddit + Hacker News + Dev.to |
| Reports | Daily log | Weekly trend report with charts |
| Alerts | No | Yes — Slack/email for viral topics |
| History | No | Yes — trend tracking over time |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
