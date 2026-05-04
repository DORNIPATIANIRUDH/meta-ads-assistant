# Meta Ads AI Assistant

An AI-powered Meta (Facebook & Instagram) advertising assistant that helps you build strategies, generate ad copy, and analyze campaign performance — for both **leads and sales**.

Available in **Desktop** and **Mobile** versions. Supports **Anthropic (Claude)** and **Groq (Llama / Gemma)** as AI providers.

---

## Live Demo

| Version | URL |
|---|---|
| Desktop | `https://yourusername.github.io/meta-ads-assistant` |
| Mobile | `https://yourusername.github.io/meta-ads-assistant/meta-ads-mobile.html` |

> Replace `yourusername` with your GitHub username.

---

## Features

### Three AI Modes

**Strategy Consultant**
- Full Meta Ads strategy for lead generation AND direct sales
- Audience targeting, campaign objectives, funnel stages
- Budget split recommendations between lead-gen and sales campaigns
- CPL, CPA, ROAS benchmarks and how to hit them

**Ad Copy Generator**
- 3 high-converting ad copy variations per request
- Lead-gen copy (soft CTAs) and sales copy (hard CTAs)
- Hook, primary text, headline, CTA, and placement for each
- Mobile-first, conversion-focused writing

**Campaign Analyzer**
- Full audit of your campaign metrics (CTR, CPC, CPM, ROAS, CPL, CPA)
- Industry benchmarks for leads and sales
- Lead quality vs sales gap diagnosis
- Top 5 prioritized fixes with estimated impact
- Retargeting play to convert leads into buyers

---

## AI Providers

| Provider | Models | Cost | Works In |
|---|---|---|---|
| **Anthropic** | Claude Sonnet 4.6, Haiku 4.5, Opus 4.6 | Pay per token | Preview + GitHub Pages |
| **Groq** | Llama 3.3 70B, Llama 3.1 8B, Gemma 2 9B | Free tier | GitHub Pages only |

> **Note:** Groq does not work in Claude's artifact preview due to browser restrictions. It works perfectly when deployed on GitHub Pages.

---

## Getting Started

### 1. Get an API Key

**Anthropic (works everywhere):**
- Go to [console.anthropic.com](https://console.anthropic.com)
- Sign up → API Keys → Create Key
- Key format: `sk-ant-api03-...`
- New accounts receive free credits

**Groq (free, GitHub Pages only):**
- Go to [console.groq.com](https://console.groq.com)
- Sign up → API Keys → Create Key
- Key format: `gsk_...`
- Completely free with generous rate limits

### 2. Open the App

**Desktop:**
```
https://yourusername.github.io/meta-ads-assistant
```

**Mobile:**
```
https://yourusername.github.io/meta-ads-assistant/meta-ads-mobile.html
```

### 3. Launch

1. Select your AI provider (Anthropic or Groq)
2. Choose a model
3. Enter your API key
4. Click **Launch**

---

## Add to Home Screen (Mobile App Experience)

Turn the mobile version into a home screen app in seconds.

**Android (Chrome):**
1. Open the mobile URL in Chrome
2. Tap the three-dot menu (top right)
3. Tap **Add to Home Screen**
4. Tap **Add**

**iPhone (Safari):**
1. Open the mobile URL in Safari
2. Tap the **Share** button (bottom center)
3. Scroll down → tap **Add to Home Screen**
4. Tap **Add**

The app will appear on your home screen and open full-screen like a native app.

---

## Deploying to GitHub Pages

### First Time Setup

1. Create a new repository on [github.com](https://github.com)
   - Name: `meta-ads-assistant`
   - Visibility: **Public**
   - Check "Add a README file"

2. Upload files:
   - Rename `meta-ads-desktop.html` → `index.html`
   - Upload both `index.html` and `meta-ads-mobile.html`

3. Enable GitHub Pages:
   - Go to **Settings** → **Pages**
   - Branch: `main` → click **Save**
   - Wait 1–2 minutes

4. Your app is live at:
   ```
   https://yourusername.github.io/meta-ads-assistant
   ```

### Updating Files

1. Go to your repository
2. Click the file you want to update
3. Click the **pencil icon** (Edit)
4. Make changes → click **Commit changes**

Changes go live within 1–2 minutes.

---

## Project Structure

```
meta-ads-assistant/
├── index.html              # Desktop version (main entry point)
├── meta-ads-mobile.html    # Mobile version
└── README.md               # This file
```

---

## How It Works

Both files are standalone HTML files with no external dependencies except:
- Google Fonts (DM Sans) — for typography
- Anthropic API — `https://api.anthropic.com/v1/messages`
- Groq API — `https://api.groq.com/openai/v1/chat/completions`

Your API key is stored **only in your browser session**. It is never saved to any server, database, or third party. It is sent directly to the provider you choose (Anthropic or Groq) with each message.

---

## Environment Compatibility

| Environment | Anthropic | Groq |
|---|---|---|
| Claude artifact preview | ✅ Works | ❌ Blocked by CSP |
| Local file (file://) | ✅ Works | ✅ Works |
| GitHub Pages | ✅ Works | ✅ Works |
| Any web server | ✅ Works | ✅ Works |

---

## Error Reference

| Error | Cause | Fix |
|---|---|---|
| `Key must start with sk-ant-` | Wrong Anthropic key format | Get key from console.anthropic.com |
| `Groq keys start with gsk_` | Wrong Groq key format | Get key from console.groq.com |
| `Invalid API key` | Key is wrong or expired | Generate a new key |
| `Rate limit hit` | Too many requests | Wait 30–60 seconds and retry |
| `Model not found` | Deprecated or unavailable model | Select a different model |
| `Groq is blocked in this preview` | Running inside Claude's artifact iframe | Deploy to GitHub Pages or switch to Anthropic |
| `Network error` | No internet connection | Check your connection and retry |

---

## Customization

### Change the AI System Prompts

Open either HTML file in a text editor and find the `MODES` object in the `<script>` section. Each mode has a `system` property — edit that text to change how the AI responds.

```javascript
const MODES = {
  consultant: {
    system: `Your custom instructions here...`
  },
  ...
}
```

### Add Your Own Models

In the `PROVIDERS` object, add entries to the `models` array:

```javascript
anthropic: {
  models: [
    { id: "claude-sonnet-4-6", label: "Claude Sonnet 4.6" },
    // add more here
  ]
}
```

### Change the Color Scheme

Edit the CSS variables at the top of the `<style>` block:

```css
:root {
  --blue: #0866FF;      /* primary accent color */
  --bg: #f0f2f5;        /* page background */
  --surface: #ffffff;   /* card background */
}
```

---

## Privacy & Security

- **No backend** — the app is purely client-side HTML/CSS/JavaScript
- **No data storage** — conversations are held only in browser memory and cleared on refresh
- **No tracking** — no analytics, no cookies, no telemetry
- **API keys** — stored in JavaScript variables only, never written to localStorage or sent anywhere except the chosen AI provider
- **Open source** — all code is visible in the HTML files, nothing is minified or hidden

---

## License

MIT License — free to use, modify, and distribute for personal or commercial projects.

---

## Built With

- Vanilla HTML, CSS, JavaScript — no frameworks
- [Anthropic API](https://docs.anthropic.com) — Claude models
- [Groq API](https://console.groq.com/docs) — Llama and Gemma models
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) — Google Fonts
- [GitHub Pages](https://pages.github.com) — free hosting
