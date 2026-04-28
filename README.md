# sergei.site

Static one-page portfolio. Cream background, full-screen palm-shadow video overlay, two-column desktop / single-column mobile layout from Figma.

## Local preview

Any static server works. With Python:

```bash
python3 -m http.server 3000
```

Or with Node:

```bash
npx serve .
```

Open http://localhost:3000.

## Deploy to Vercel via GitHub

1. Create a new GitHub repo and push this folder:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin git@github.com:<you>/<repo>.git
   git push -u origin main
   ```

2. Go to https://vercel.com/new, import the repo. No build settings needed — Vercel will detect a static site, use `vercel.json`, and deploy.

3. Each `git push` to `main` triggers a new production deployment.

## Files

- `index.html` — markup
- `styles.css` — layout, typography, responsive rules
- `palms.mp4` — full-screen background video
- `vercel.json` — caching headers
