# bekiryavuzkoc — personal site

Static, single file, no build step. `index.html` + the CV PDF.

## Deploy for free

### Option A — GitHub Pages (this repo, recommended)
Repo: https://github.com/bekiryavuzkoc/personalwebsite (already pushed, branch `main`).

1. GitHub → repo → **Settings → Pages**
2. Source: **Deploy from a branch** · Branch: **main** · Folder: **/ (root)** → Save
3. Live in a minute at **https://bekiryavuzkoc.github.io/personalwebsite/**

Root URL instead (`https://bekiryavuzkoc.github.io/`): Settings → General → rename the repo to `bekiryavuzkoc.github.io`. Nothing else changes.

Custom domain: Settings → Pages → Custom domain, then a CNAME record at your DNS pointing to `bekiryavuzkoc.github.io`.

Update the site:
```bash
cd ~/cv/site && git add -A && git commit -m "Update" && git push
```

### Option B — Cloudflare Pages (drag and drop)
Cloudflare dashboard → Workers & Pages → Create → Pages → "Upload assets" → drop the `site/` folder.
Free custom domain if you already manage a domain on Cloudflare.

### Option C — Vercel
```bash
cd ~/cv/site && npx vercel --prod
```

## Updating the CV
Regenerate the PDF from `~/cv/cv.html` and copy it here as `Bekir_Yavuz_Koc_CV.pdf`:
```bash
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --disable-gpu \
  --no-pdf-header-footer --print-to-pdf=$HOME/cv/site/Bekir_Yavuz_Koc_CV.pdf "file://$HOME/cv/cv.html"
```
