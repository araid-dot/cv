# cv.araid.au

Interactive, single-file HTML resume for Upul Senanayake. Hosted as a static
site on GitHub Pages at **cv.araid.au**.

## Files

- `index.html` — the whole site (self-contained: fonts load from Google Fonts CDN, everything else is inline).
- `CNAME` — tells GitHub Pages which custom domain serves this repo. Already set to `cv.araid.au` — leave it as is.
- `Upul_Senanayake_CV.pdf` — **add this yourself.** The "Download CV" buttons on the page link to this exact filename in the same folder, so drop your PDF here with this name (or edit the links in `index.html` if you name it differently).

## One-time setup

### 1. Create the repo

On github.com, click **New repository**. Suggested name: `cv` (or anything you like — the repo name doesn't affect the URL once the custom domain is wired up). Keep it **Public** (GitHub Pages on the free plan requires public repos, unless you're on a paid plan with private Pages).

### 2. Upload the files

Drag `index.html`, `CNAME`, and your CV PDF into the repo via the GitHub web UI ("Add file" → "Upload files"), or clone the repo locally and `git add` / `git commit` / `git push` them — either works.

### 3. Enable GitHub Pages

Repo → **Settings** → **Pages** → under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.

### 4. Point the DNS

At your domain registrar (wherever araid.au's nameservers are managed), add:

| Type  | Host | Value |
|-------|------|-------|
| CNAME | cv   | `<your-github-username>.github.io` |

Replace `<your-github-username>` with your actual GitHub username (the one that owns this repo). It can take a few minutes to a few hours to propagate.

### 5. Confirm HTTPS

Back in repo → Settings → Pages, once the DNS is detected, tick **Enforce HTTPS**. GitHub issues a free certificate automatically — this can take up to 24 hours after the DNS resolves, so don't worry if it's greyed out at first.

## Updating the site later

Edit `index.html` (or swap the PDF), commit, push. GitHub Pages redeploys automatically within a minute or two — no build step, since this is plain static HTML.
