# Pooja Subramanian — Portfolio

Live site: **https://poojasubu1.github.io/pooja-portfolio/**

A single self-contained `index.html` — no build step, no dependencies. The profile photo and downloadable résumé PDF are embedded directly in the file as base64 data, so the whole site is just one file.

## Deploying

This repo is served by **GitHub Pages**, configured to build from the `main` branch, root (`/`) folder.

Any push to `main` redeploys the live site automatically — usually live within 1–2 minutes.

```bash
git add index.html
git commit -m "Update site"
git push
```

That's it. No CI, no build process — GitHub Pages just serves `index.html` as-is.

## First-time setup (if forking or recreating this repo)

If Pages isn't already enabled on a repo:

1. Push `index.html` to the `main` branch.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. The site will be live at `https://<username>.github.io/<repo-name>/` within a minute or two.

(Or via the GitHub CLI: `gh api -X POST repos/<owner>/<repo>/pages -f "source[branch]=main" -f "source[path]=/"`)

## Making edits

Open `index.html` in any editor — it's plain HTML/CSS/JS with no framework. To preview locally before pushing:

```bash
open index.html
```

or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Updating the résumé PDF or photo

Both are embedded as base64 `data:` URIs inside `index.html` (search for `data:application/pdf;base64,` and `data:image/jpeg;base64,`). To swap either:

1. Convert the new file to base64: `base64 -i newfile.pdf | pbcopy` (macOS)
2. Replace the corresponding `data:...;base64,<...>` string in `index.html` with the new value.
