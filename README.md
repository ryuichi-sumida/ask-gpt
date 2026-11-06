# Ask GPT

One-file web page that asks an OpenAI model (GPT-6.1 Sol by default) and shows, per answer: total time, time to first token, input/cached/output/reasoning tokens, and cost in USD. Session and all-time cost totals are shown in the header.

- No backend. The browser calls `api.openai.com` directly.
- Your API key is stored in `localStorage` of your browser only. Nothing secret is in this repo.
- Works opened as a local file, from `python3 -m http.server`, or on GitHub Pages.

## Host on GitHub Pages

```sh
gh repo create ask-gpt --public --source=. --push
gh api -X POST repos/{owner}/ask-gpt/pages -f 'source[branch]=main' -f 'source[path]=/'
```

Then open `https://<user>.github.io/ask-gpt/`, click **API key**, paste your key once.

## Prices

Hard-coded in `index.html` (`PRICES`) from developers.openai.com/api/docs/pricing, standard tier, checked 2026-11-07. Update there when OpenAI changes prices or ships a new model.
