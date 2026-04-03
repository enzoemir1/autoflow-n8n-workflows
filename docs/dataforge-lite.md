# DataForge Lite — URL Data Extractor

Extract structured data from any web page using AI.

## How It Works

```
[Webhook] -> [Fetch Page] -> [AI: Extract Data] -> [Return JSON]
```

1. **Receive Request** — POST a URL and the fields you want to extract
2. **Fetch Page** — Downloads the HTML content
3. **AI Extract** — GPT-4o-mini reads the page and extracts structured data
4. **Return** — Clean JSON with your requested fields

## Setup

1. Import `workflows/dataforge-lite.json` into n8n
2. Add OpenAI credentials
3. Activate and test:

```bash
curl -X POST https://your-n8n-instance/webhook/dataforge-lite \
  -H "Content-Type: application/json" \
  -d '{
    "url": "https://example.com/product-page",
    "fields": ["product_name", "price", "description", "rating"]
  }'
```

## Cost

About $0.003 per page. Scraping 100 pages costs approximately $0.30.

## Lite vs Full

| Feature | Lite | Full |
|---------|------|------|
| Input | Single URL | Batch URLs (up to 100) |
| Scheduling | No | Yes — daily/weekly auto-scrape |
| Change Tracking | No | Yes — alerts when data changes |
| Reports | No | Yes — weekly summary reports |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
