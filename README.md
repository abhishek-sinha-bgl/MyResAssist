# MyResAssist

**Research intelligence. Knowledge that accumulates.**

[Live Demo](https://abhishek-sinha-bgl.github.io/MyResAssist/) · Single HTML file · No backend · No build tools · BYOK

---

## What it is

MyResAssist is a personal research assistant that treats knowledge as something worth keeping. Unlike a chat interface where conversations disappear, MyResAssist extracts claims from every response, lets you absorb them into a persistent knowledge base, and surfaces contradictions automatically as your understanding of a topic deepens.

The unit of value is a **claim**, not a message.

---

## How it works

**The Research Wall** is your home screen — a grid of topics you're actively researching, each showing its strongest finding, an average confidence level, and a flag if any claims contradict each other.

**Inside a topic**, your extracted knowledge lives on the left as a list of claims with confidence levels (high / medium / low) and contradiction markers. The research chat is on the right — a tool you reach for to add more.

**After every AI response**, MyResAssist automatically extracts 2–4 key claims and presents them in an absorb panel. You choose which ones are worth keeping, and they're filed into your topic with sources attached. If a new claim contradicts something you already know, it's flagged immediately.

---

## Features

### Knowledge base
- Claims persist across sessions — your research wall grows over time
- Automatic confidence ratings (high / medium / low) on every extracted claim
- Contradiction detection — new claims are checked against your existing knowledge
- Filter claims by confidence level or contradictions
- Edit topic titles in place, delete individual claims

### Research
- Full streaming responses from Claude, OpenAI, Gemini, or any OpenAI-compatible provider
- Web search toggle — live results via Anthropic (Claude), Google (Gemini), or provider default
- **Research Deeper** — structured multi-angle deep dive: core findings, supporting evidence, counterarguments, implications, and further angles
- **Summarise** — concise executive brief of the current session against your existing claims
- Follow-up question suggestions after each response
- Export topic to Markdown (claims + full conversation)

### Themes
Four built-in themes, switchable live from Settings with no reload required. Your choice persists across sessions.

| Theme | Character |
|---|---|
| **Parchment** | Warm cream paper, charcoal ink, Lora serif. Editorial and readable — the default. |
| **Obsidian** | Near-black with electric cyan accents, Outfit typeface. Dark mode with precision energy. |
| **Slate & Bone** | Cool off-white, blue-grey ink, IBM Plex Mono display. Clinical, architectural, low noise. |
| **Forest Codex** | Deep forest green, aged gold accents, Crimson Pro italic. The richest and most distinctive. |

### Providers
- Claude (Anthropic) — with web search support
- OpenAI — with streaming
- Google Gemini — with Google Search grounding
- Any OpenAI-compatible provider: Groq, Mistral, Together AI, Ollama, LM Studio, Perplexity
- Custom providers: live model fetch from `/v1/models`, dropdown selection, edit/update saved providers

### Voice
- Voice input via Web Speech API (Chrome and Safari on Android/iOS)
- Hands-free: speak your question, response streams automatically

### Mobile
- Responsive layout — claims panel full-screen on mobile
- Chat opens as a slide-up panel via a floating button
- Non-streaming API calls on mobile for reliable CORS handling with custom providers

---

## Getting started

1. Open the [live demo](https://abhishek-sinha-bgl.github.io/MyResAssist/) or host `index.html` anywhere static
2. Click **Configure API key** in the top bar
3. Select your provider, enter your API key, choose a model, and save
4. Optionally pick a theme from the Appearance row at the top of Settings
5. Create your first research topic from the wall
6. Ask a question — absorb the findings

Your API keys and all research data are stored in your browser's localStorage. Nothing leaves your device except the API calls you make directly to your chosen provider.

---

## Deployment

This is a single `index.html` file. Drop it anywhere that serves static files:

- **GitHub Pages** — push to your repo, enable Pages, done
- **Netlify / Vercel** — drag and drop
- **Local** — open the file directly in your browser

No server, no database, no accounts.

---

## API key setup

| Provider | Where to get a key |
|---|---|
| Claude | [console.anthropic.com](https://console.anthropic.com) |
| OpenAI | [platform.openai.com](https://platform.openai.com) |
| Gemini | [aistudio.google.com](https://aistudio.google.com) |
| Groq | [console.groq.com](https://console.groq.com) |
| Mistral | [console.mistral.ai](https://console.mistral.ai) |

For Groq, the correct endpoint is `https://api.groq.com/openai/v1/chat/completions`. After entering the endpoint and key, click **Fetch models** to populate the model dropdown automatically.

---

## Roadmap

- Multi-step deep research with sequential independent searches
- URL and document analysis — paste a link or attach a PDF
- Cross-device session sync via shareable URL or GitHub Gist
- Search within your knowledge base across topics
- Claim relationship mapping — visual connections between supporting and contradicting claims

---

## Built with

No frameworks, no bundler, no dependencies. Fonts via Google Fonts: Lora and Source Sans 3 (Parchment), Outfit and IBM Plex Mono (Obsidian), IBM Plex Mono (Slate), Crimson Pro (Forest). Everything else is vanilla HTML, CSS, and JavaScript.
