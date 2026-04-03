# FlowScribe Lite — Content Repurposing

Turn one blog post into 4 platform-native social media posts automatically.

## How It Works

```
[Webhook] -> [Validate Input] -> [AI: Generate 4 Versions] -> [Save to Google Sheets] -> [Return Results]
```

1. **Receive Content** — A webhook receives your blog post (title + body text)
2. **Validate Input** — Checks content length (min 50 chars), generates a unique request ID
3. **AI Transform** — GPT-4o-mini generates optimized versions for Twitter thread, LinkedIn post, Instagram caption, Facebook post
4. **Save Results** — All 4 versions saved to a Google Sheets row
5. **Return** — JSON response with all generated content

## Setup

### Prerequisites
- n8n instance (cloud or self-hosted)
- OpenAI API key (gpt-4o-mini)
- Google Sheets account

### Step-by-Step

1. Import `workflows/flowscribe-lite.json` into n8n
2. Create OpenAI credentials in n8n (Settings > Credentials > OpenAI)
3. Create Google Sheets credentials (OAuth2)
4. Create a Google Sheet with columns: Date, Title, Twitter, LinkedIn, Instagram, Facebook
5. Update the Google Sheets node with your sheet ID
6. Activate the workflow
7. Test with a POST request:

```bash
curl -X POST https://your-n8n-instance/webhook/flowscribe-lite \
  -H "Content-Type: application/json" \
  -d '{
    "title": "How AI is Changing Content Creation",
    "content": "Your blog post text here (minimum 50 characters)...",
    "brand_voice": "professional yet approachable"
  }'
```

## Input Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| title | No | Untitled | Post title |
| content | Yes | — | Blog post text (min 50 chars) |
| brand_voice | No | professional yet approachable | Tone for generated content |

## Cost

About $0.01 per run (GPT-4o-mini). 100 posts/month costs approximately $1.

## Lite vs Full Version

| Feature | Lite (Free) | Full |
|---------|------------|------|
| Platforms | 4 | 8 (+ TikTok, YouTube, Newsletter, Pinterest) |
| A/B Testing | No | Yes |
| Scheduling | No | Yes — auto-post via Buffer/Hootsuite hooks |
| Analytics | No | Yes — tracks engagement per platform |
| Brand Voice | Basic | Advanced — learns from examples |

Full version: [automatiabcn.gumroad.com/l/flowscribe](https://automatiabcn.gumroad.com/l/flowscribe)
