# letmeshock.com

Static one-page portfolio. Cream background, full-screen palm-shadow video overlay, single column on small/medium viewports, two-column layout at the 1440px Figma frame.

## Live

- Production (Vercel alias): https://letmeshock-com.vercel.app
- Custom domain: https://letmeshock.com (pending Cloudflare DNS — see below)

## Local preview

Any static server works.

```bash
python3 -m http.server 3000
# or
npx serve .
```

Open http://localhost:3000.

## Deploy pipeline (already wired up)

- GitHub repo: https://github.com/letmeshock-uae/letmeshock.com
- Vercel project: `letmeshock-com` (team `letmeshock-9343s-projects`)
- The GitHub repo is connected to the Vercel project: every push to `main` triggers a production deployment.

To trigger a deploy, just commit and push:

```bash
git add .
git commit -m "your message"
git push
```

## Cloudflare DNS for `letmeshock.com`

Dashboard: https://dash.cloudflare.com/e7ee214071361fe42aa72515edaa5714/letmeshock.com/dns/records

Add these records (proxy = DNS only, the gray cloud — Vercel handles SSL/edge):

| Type  | Name | Content              | Proxy status |
| ----- | ---- | -------------------- | ------------ |
| A     | @    | 76.76.21.21          | DNS only     |
| CNAME | www  | cname.vercel-dns.com | DNS only     |

After saving, Vercel will automatically issue an SSL cert (a few minutes). If you keep Cloudflare proxy ON, set the SSL/TLS encryption mode to **Full (strict)** to avoid redirect loops.

Verify:

```bash
vercel domains inspect letmeshock.com
```

## Files

- `index.html` — markup
- `styles.css` — layout, typography, responsive rules
- `palms.mp4` — full-screen background video
- `vercel.json` — caching headers
