# Tiktense — Web (marketing + policy)

Static site with landing, support, privacy policy, terms of service.
Bilingual VI/EN. Zero JS. Dark-mode aware CSS.

## Structure

```
web/
├── index.html          Landing (VI)
├── support.html        Support + FAQ (VI)
├── support-en.html     Support + FAQ (EN)
├── privacy.html        Privacy Policy (VI)
├── privacy-en.html     Privacy Policy (EN)
├── terms.html          Terms of Service (VI)
├── terms-en.html       Terms of Service (EN)
├── style.css           Shared styles
├── vercel.json         Vercel config (clean URLs, security headers)
└── README.md           This file
```

## Deploy to Vercel

### One-time setup

1. Install Vercel CLI (once):
   ```
   npm i -g vercel
   ```
2. From this directory:
   ```
   cd web
   vercel
   ```
   Follow prompts. Pick a project name (e.g. `tiktense`), scope (personal or team).
   Vercel gives you a URL like `https://tiktense.vercel.app`.

### Custom domain (optional)

If you own `tiktense.app`:
```
vercel domains add tiktense.app
```
Then point DNS `CNAME` → `cname.vercel-dns.com`.

### Deploy updates

Any edit to files, then:
```
vercel --prod
```

## Local preview

Any static file server works. Simplest:
```
cd web && python3 -m http.server 8000
```
Open http://localhost:8000

## Before shipping to App Store

1. Replace `hello@tiktense.app` throughout with your real support email.
2. Deploy to Vercel to get a public URL.
3. Fill in App Store Connect:
   - Privacy Policy URL: `https://<your-vercel>.vercel.app/privacy`
   - Support URL:        `https://<your-vercel>.vercel.app/support`
   - Marketing URL:      `https://<your-vercel>.vercel.app/`

## Notes

- No tracking pixels, no analytics — matches app privacy posture.
- Vercel free tier is more than enough for a static policy site.
- All pages honour `prefers-color-scheme: dark`.
