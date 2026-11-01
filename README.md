# PromptDeck

**Free, private, BYOK multi-model chat workbench.** One HTML file. No server. No account. Your API keys never leave your browser.

Live: **https://promptdeck.vercel.app**

## Why

Existing chat UIs fail at three things:

1. **Prompt management** — your best prompts are buried in chat history
2. **Local storage** — conversations locked on someone else's server
3. **Multi-model** — comparing two models means copy-pasting between tabs

PromptDeck fixes all three:

- **Prompt library** with `{{variable}}` templates — one click to inject, fill in a dialog, send
- **Everything local** — chats, prompts, keys: 100% in your browser's localStorage; JSON export/import anytime
- **Compare mode** — select 2–4 models, one prompt runs on all of them in parallel, answers side-by-side
- **Streaming** — real SSE token streaming, all models at once

## BYOK — bring your own key

Built-in presets (all OpenAI-compatible `/chat/completions`):

| Preset | Base URL |
|---|---|
| Zhipu GLM (glm-4-flash is **free**) | `https://open.bigmodel.cn/api/paas/v4` |
| DeepSeek | `https://api.deepseek.com/v1` |
| SiliconFlow | `https://api.siliconflow.cn/v1` |
| Moonshot Kimi | `https://api.moonshot.cn/v1` |
| iFlytek Spark-X2.6 | `https://maas-api.xfyun.cn/v1` |
| OpenAI | `https://api.openai.com/v1` |
| Groq | `https://api.groq.com/openai/v1` |
| Ollama (local) | `http://localhost:11434/v1` |
| Custom | any OpenAI-compatible endpoint |

> **Ollama note:** set `OLLAMA_ORIGINS=*` so the browser is allowed to call it.

## Zero-cost model

- No GPU, no backend, no database — it's one static HTML file
- Users supply their own keys (free tiers: glm-4-flash, Groq, Spark-X2.6 free quota)
- Deploy anywhere: Vercel / GitHub Pages / any static host — or just open the file

## Run locally

```
python -m http.server 8080
# open http://localhost:8080
```

Or host the single `index.html` on any static hosting.

## Privacy

Keys and chats are stored only in your browser's `localStorage`. There is no telemetry, no analytics, no server. Export wipes nothing; deleting a chat deletes it everywhere (it was never anywhere else).

MIT License.
