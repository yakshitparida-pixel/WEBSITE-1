# Confluence AI

Confluence AI is a local, zero-dependency AI chat app that calls every configured free or trial API-key provider in parallel, then returns one synthesized answer.

## Supported Engines

- Google Gemini API
- Groq
- OpenRouter free router
- Hugging Face Inference Providers
- Cohere trial keys
- Cerebras free trial

Free tiers and trial quotas change, so the app keeps every provider optional. Add one key or all of them.

## Run It

1. Open `.env`.
2. Paste any API keys you want to use.
3. Start the app:

```powershell
npm start
```

4. Open:

```text
http://localhost:5177
```

No npm install is needed. The app uses only Node's built-in modules and `fetch`.

## How It Answers

1. Each enabled provider drafts an answer to the same prompt.
2. The server picks a working provider as the synthesizer.
3. The synthesizer merges the drafts into a single answer.
4. If synthesis fails, the server returns the strongest successful draft with cross-check notes.

Your API keys stay on the server in `.env`; they are never sent to the browser.

## Provider Notes

- Gemini API rate limits include a Free tier for active projects or free trials.
- Groq publishes Free Plan limits by model.
- OpenRouter supports `openrouter/free` and `:free` model variants.
- Hugging Face gives monthly credits for Inference Providers.
- Cohere offers free evaluation keys with limited usage.
- Cerebras documents free-trial rate limits.

## Official Docs

- Google Gemini API rate limits: https://ai.google.dev/gemini-api/docs/rate-limits
- Google Gemini text generation: https://ai.google.dev/gemini-api/docs/text-generation
- Groq rate limits: https://console.groq.com/docs/rate-limits
- Groq chat completions: https://console.groq.com/docs/text-chat
- OpenRouter quickstart: https://openrouter.ai/docs/quickstart
- OpenRouter free router: https://openrouter.ai/docs/cookbook/get-started/free-models-router-playground
- Hugging Face Inference Providers pricing: https://huggingface.co/docs/inference-providers/pricing
- Hugging Face chat completion: https://huggingface.co/docs/inference-providers/tasks/chat-completion
- Cohere API keys and rate limits: https://docs.cohere.com/docs/rate-limits
- Cohere Chat API: https://docs.cohere.com/docs/chat-api
- Cerebras quickstart: https://inference-docs.cerebras.ai/quickstart
- Cerebras rate limits: https://inference-docs.cerebras.ai/support/rate-limits
