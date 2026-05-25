# Setup guide — get this site live in 30 minutes

Step-by-step from "files on disk" to "public site at github.io." Assumes you have a GitHub account and a working terminal.

## 1. Install Quarto

Download from https://quarto.org/docs/get-started/ for your OS. Verify:

```bash
quarto --version
```

You don't need R installed for the site to render *as it's currently set up* — all R chunks have `eval: false`. You only need R if you want code chunks to actually run during render. (For now, leaving them un-evaluated is fine and faster.)

## 2. Create the GitHub repo

1. Go to https://github.com/new.
2. Name it `learning-journey` (or whatever you want — just be consistent).
3. **Public.** Don't initialize with README, license, or .gitignore — we already have those.
4. Create repo. Copy the SSH or HTTPS URL.

## 3. Push the scaffold

From inside the `learning-journey/` folder I generated:

```bash
git init
git add .
git commit -m "Initial scaffold"
git branch -M main
git remote add origin git@github.com:YOURUSERNAME/learning-journey.git
git push -u origin main
```

## 4. Update placeholder URLs

Find-and-replace `YOURUSERNAME` with your actual GitHub username in:

- `_quarto.yml` (site-url, repo-url, footer)
- `index.qmd` (no change needed, but check)
- `about.qmd`
- `README.md`

Same for `YOURPROFILE` in the LinkedIn footer link.

Commit and push these.

## 5. Enable GitHub Pages

1. On GitHub, go to your repo → **Settings** → **Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions**.
3. That's it — the workflow in `.github/workflows/publish.yml` will fire on your next push.

## 6. Trigger a build

Either push a small change, or go to **Actions** tab → **Publish Quarto site** → **Run workflow**.

After 1–2 minutes, your site will be live at:

```
https://YOURUSERNAME.github.io/learning-journey/
```

## 7. Local workflow from here

Edit `.qmd` files in your editor. Preview locally:

```bash
quarto preview
```

This opens a live-reloading browser tab. Edit, save, see changes immediately. When you're happy:

```bash
git add .
git commit -m "Add entry: propensity score matching"
git push
```

GitHub Actions does the rest. Site updates in ~2 minutes.

## 8. Adding a new entry

```bash
cp _entry-template.qmd heor-rwe/methods-concepts/propensity-score-matching.qmd
# edit it
# add it to heor-rwe/methods-concepts/index.qmd's listing
# (optionally) add it to _quarto.yml sidebar
git add . && git commit -m "Add: PS matching entry" && git push
```

## 9. Optional but recommended

- **Custom domain** later — once you have ~20 entries, point a domain like `priya-stats.com` at the GitHub Pages site. Settings → Pages → Custom domain.
- **Analytics** — add a Plausible or umami snippet to `_quarto.yml` under `format.html.include-in-header` if you eventually want to see traffic.
- **RSS feed** — Quarto can generate one for any listing page. Useful when you start sharing.
- **Search** is already enabled in the navbar config — it indexes everything automatically.

## 10. The "public but quiet" plan

For the first 4–6 weeks:

- Site is public and indexable. ✅
- Don't link it from LinkedIn yet. ✅
- Aim for one new entry per week, plus updates to the R cheatsheet whenever you learn something.
- Build a small backlog (8–10 entries) before any active promotion.
- First share moment: after R/Pharma submission, or when you have a Resources Reviewed page that's actually got reviews on it.

By the time you announce, there's substance. Until then, it's quietly accumulating credibility.
