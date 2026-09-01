# bekiryavuzkoc — personal site

Static, single file, no build step. `index.html` + the CV PDF.

## Deploy for free

### Option A — GitHub Pages (recommended, gives you bekiryavuzkoc.github.io)
```bash
cd ~/cv/site
git init -b main
git add .
git commit -m "Personal site"
gh repo create bekiryavuzkoc.github.io --public --source=. --push
# GitHub → repo → Settings → Pages → Source: "Deploy from a branch", Branch: main / (root)
```
Live at https://bekiryavuzkoc.github.io within a minute or two.

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
