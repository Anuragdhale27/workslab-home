# Works Lab — home (workslab.in)

Static site: HTML + CSS + vanilla JS. No build step. Deploys automatically via GitHub Actions.

## Deploy
1. Create repo `workslab-home` on GitHub, upload all files (including the hidden `.github` folder and `CNAME`).
2. Repo → Settings → Pages → Source: **GitHub Actions**.
3. Push to `main` → the workflow deploys. Custom domain `workslab.in` is read from `CNAME`.

## Edit
- Contact links: search `CONFIG` in `index.html` (mailto / WhatsApp / Calendly).
- Accent colour: `--accent` in `css/style.css`.
- Featured product block: `#products` section in `index.html`.
- Add `og.png` (1200×630) to the root for social previews.
