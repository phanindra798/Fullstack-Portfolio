# Deploy to Vercel

Static site — no build step. Two ways. Pick one.

---

## Option A — GitHub + Vercel dashboard (recommended, auto-deploys on every push)

### 1. Create your GitHub repo
1. github.com → **+** (top-right) → **New repository**
2. Owner: `phanindra798`
3. Name: `phanindra-portfolio`
4. Visibility: **Public**
5. Do **NOT** add README / .gitignore / license (keep empty)
6. **Create repository**
7. Copy the repo URL: `https://github.com/phanindra798/phanindra-portfolio.git`

### 2. Push this folder
Run in the project folder (`c:\Users\Roshita\phani-portfolio`):
```bash
git remote add origin https://github.com/phanindra798/phanindra-portfolio.git
git push -u origin master
```
A browser opens once → sign in to GitHub → authorize. Push completes.

### 3. Import on Vercel
1. vercel.com → **Log in with GitHub**
2. **Add New → Project**
3. Find `phanindra-portfolio` → **Import** (authorize Vercel to read your repos if asked)
4. **Framework Preset: Other** · Build Command: *(empty)* · Output Directory: *(empty)*
5. **Deploy** → ~30s → live on a `*.vercel.app` URL

### 4. Set the subdomain
Project → **Settings → Domains** → edit project domain to `phanindra-pendela`
→ final URL: `https://phanindra-pendela.vercel.app`

> If `phanindra-pendela` is taken, pick another name and update these files to match:
> `index.html` (og:url, twitter:url, canonical, JSON-LD url), `sitemap.xml`, `robots.txt`.

---

## Option B — Vercel CLI (no GitHub needed)

```bash
npm i -g vercel
cd c:\Users\Roshita\phani-portfolio
vercel login      # one-time, browser/email
vercel --prod     # deploy; choose project name when asked
```

---

## Notes
- `vercel.json` already set (`cleanUrls`, no build).
- Pure static: `index.html`, `neo-styles.css`, `favicon.svg`, `image/`, `robots.txt`, `sitemap.xml`.
- Update later: edit files → `git push` (Option A auto-redeploys) or `vercel --prod` (Option B).
