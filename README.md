# Rare Heart — GitHub Pages Starter

This is a no‑build static site you can deploy on **GitHub Pages** in minutes.

## Quick start
1. Create a new repo on GitHub (e.g. `rareheart-site`).
2. Upload this whole folder’s contents to the repo (or push via Git).
3. In GitHub: **Settings → Pages → Build and deployment**  
   - **Source:** GitHub Actions  
   - It should detect `.github/workflows/pages.yml` automatically and deploy.
4. Visit the Pages URL (e.g. `https://<username>.github.io/rareheart-site/`).

## Custom domain (rareheart.foundation)
- Add your domain in **Settings → Pages → Custom domain** (we recommend `rareheart.foundation` or `www.rareheart.foundation`).
- In your DNS provider:
  - **Root domain**: set A records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
  - **or** use `www` with a CNAME to `<username>.github.io`.
- Enable **Enforce HTTPS** once the certificate is issued.

## Forms via Make (Integromat)
- In your Make scenario add a **Custom Webhook** module and copy the webhook URL.
- Replace `WEBHOOK_URL_FROM_MAKE` in `index.html` for both forms.
- Map fields (`name`, `email`, `message`, `amount`, `form`) in the scenario to route donations/contacts.  
- Optional: add a confirmation email step and Google Sheet logging.

## Local edits (optional)
Open `index.html` and `styles.css` to update copy, colors, and sections.

## Deploy via Git (SSH suggested)
```bash
# from your project folder
git init
git add .
git commit -m "Initial"
git branch -M main
git remote add origin git@github.com:<username>/rareheart-site.git
git push -u origin main
```

## Troubleshooting GitHub auth
- **SSH (recommended):**
  ```bash
  ssh-keygen -t ed25519 -C "your_email@example.com"
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_ed25519
  pbcopy < ~/.ssh/id_ed25519.pub   # paste into GitHub → Settings → SSH and GPG keys
  ssh -T git@github.com            # should say 'Hi <username>!'
  ```
- **Personal Access Token (PAT):**
  - GitHub → **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)**.
  - Scopes: `repo` is enough. Copy it once.
  - When pushing over HTTPS, use the token as the password.

## Structure
- `index.html` — single‑page site with sections and Make‑connected forms
- `styles.css` — red/black/white aesthetic
- `404.html` — friendly not found page
- `.github/workflows/pages.yml` — deploys automatically to Pages
