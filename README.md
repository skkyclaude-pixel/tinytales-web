# Kid‑Aspire Demo

A **quick, front‑end‑only** prototype that shows how the *personalised interactive story* concept works.

## What it does today
- A tiny React app (Vite) lets a parent fill in a child profile (name, age, interests).
- When you click **Generate Story** a **mock story** is displayed.
- The story is broken into segments with **choice buttons** that simulate a "choose‑your‑own‑adventure" flow.
- All data lives locally in the browser – no backend, no real API keys needed.

## How to run it
```bash
# 1. Open a terminal in this workspace
cd kid-aspire-demo/frontend

# 2. Install deps (you need Node ≥22.19, npm is fine)
npm install

# 3. Start the dev server
npm run dev
```
The app will be available at `http://localhost:5173` (or the URL shown in the console).

## Next steps / swapping in a real LLM
1. **Add a backend** (Express, Fastify, etc.) that calls OpenAI’s `chat/completions` endpoint with a prompt built from the child profile.
2. Replace the `mockStory` function in `src/App.jsx` with a `fetch('/api/story', …)` call.
3. Hook up **ElevenLabs** or OpenAI TTS to get real audio for each segment.
4. Add Stripe Checkout for the $7.99 /mo subscription.

## Folder layout
```
kid-aspire-demo/
├─ README.md                # this file
└─ frontend/
   ├─ package.json          # npm deps
   ├─ vite.config.ts        # Vite config (TS, works for JS too)
   └─ src/
       ├─ main.jsx          # entry point
       ├─ App.jsx           # main UI logic
       └─ components/
           ├─ ProfileForm.jsx   # profile input form
           └─ StoryPlayer.jsx   # mock story display & branching UI
```

Feel free to modify the UI, replace the mock data, or add a backend later. Happy hacking!