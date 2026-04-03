# SupportFlow Lite — AI Customer Support Chatbot

A simple AI chatbot that answers customer questions using your company context.

## How It Works

```
[Webhook] → [Load Context] → [AI: Generate Answer] → [Log to Sheets] → [Return Response]
```

1. **Receive Question** — Webhook receives a customer message
2. **Load Context** — Reads your company info from environment variables
3. **AI Answer** — GPT-4o-mini generates a helpful response using your company context
4. **Log** — Saves question + answer to Google Sheets
5. **Return** — JSON response with the AI answer

## Setup

1. Import `workflows/supportflow-lite.json` into n8n
2. Add OpenAI credentials
3. Add Google Sheets credentials
4. Set environment variable `SUPPORTFLOW_CONTEXT` with your company info:
   ```
   We are Acme Corp, a SaaS company that builds project management tools.
   Our pricing: Free ($0), Pro ($29/mo), Enterprise ($99/mo).
   Support hours: Mon-Fri 9am-6pm EST.
   Refund policy: 30-day money-back guarantee.
   ```
5. Activate and test:

```bash
curl -X POST https://your-n8n-instance/webhook/supportflow-lite \
  -H "Content-Type: application/json" \
  -d '{
    "message": "What are your pricing plans?",
    "user_id": "user-123"
  }'
```

## Cost

~$0.002 per message. 1,000 messages/month costs approximately $2.

## Lite vs Full Version

| Feature | Lite (Free) | Full |
|---------|------------|------|
| Context | Environment variable | RAG with Pinecone vector DB |
| Memory | No conversation memory | Full conversation history |
| Handoff | No | Yes — escalate to human agent |
| Widget | No | Yes — embeddable chat widget |
| Analytics | Basic logging | Satisfaction scores + response times |

Full version: [automatiabcn.gumroad.com/l/autoflow-starter](https://automatiabcn.gumroad.com/l/autoflow-starter)
