# Brief to Backlog

AI-assisted requirements analysis and delivery planning.

- `index.html`: the app
- `evaluation.html`: the evaluation page (test set, scoring, before/after comparison)
- `api/plan.js`: Vercel function that calls the Gemini API; the key stays on the server
- `vercel.json`, `package.json`: Vercel settings

## Deploy on Vercel

1. vercel.com → **Add New… → Project** → import this GitHub repository.
2. Framework Preset: **Other**. Leave build settings empty. **Deploy**.
3. **Settings → Environment Variables**, add:
   - `GEMINI_API_KEY` = your Gemini API key
   - `GEMINI_FALLBACK_MODEL` = `gemini-3.1-flash-lite` (optional; used when the main model is busy)
4. **Deployments** → latest deployment → **⋯ → Redeploy**, so the function picks up the variables.

Optional variables: `GEMINI_MODEL` (default `gemini-3.8-flash`), `GEMINI_THINKING` (default `minimal`).
