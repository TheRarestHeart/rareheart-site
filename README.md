# Rare Heart — one‑page email signup (Netlify Forms)

This folder is a ready‑to‑deploy starter that uses **your colors** (crimson, charcoal, ivory), a centered logo image, and a simple email capture form powered by **Netlify Forms** (no backend needed).

## Quick start

1) Preview locally (optional):
```bash
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

2) Deploy with Netlify (recommended):
```bash
# If you don't have Node, install via Homebrew:  brew install node
npm install -g netlify-cli
netlify login            # opens a browser, grant access
netlify init             # pick 'Create & configure a new site'
netlify deploy --prod    # deploys live and prints your site URL
```
The CLI prints a URL like `https://your-site-name.netlify.app`. Use that link on your social profiles.

### Where do the emails go?
After the first production deploy, go to **Netlify Dashboard → Forms → rare-heart-signup** to see submissions and export CSV. You can connect to Google Sheets via Zapier/Make in **Integrations**.

### Custom domain (optional)
In the Netlify UI: **Site settings → Domain management → Add custom domain** and follow the DNS instructions.
