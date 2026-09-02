# LidNote landing page

One self-contained static page (`index.html`) plus `CNAME`. No build step, no dependencies
beyond two Google Fonts loaded at runtime.

## Deploy to GitHub Pages

1. Create a public repo (e.g. `lidnote-site`), commit `index.html`, `CNAME`, this README.
2. Repo Settings → Pages → Source: "Deploy from a branch" → branch `main`, folder `/ (root)`.
3. Settings → Pages → Custom domain: `lidnote.com` (the `CNAME` file keeps this setting
   pinned across deploys). Tick "Enforce HTTPS" once the certificate is issued (can take
   up to an hour after DNS resolves).

## DNS (at your registrar)

- Apex `lidnote.com` → four A records:
  185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- `www.lidnote.com` → CNAME record → `<your-github-username>.github.io`
  (then add www as an additional Pages domain or let GitHub redirect it).

## Before going live — placeholders to swap

- `hello@lidnote.com` appears in three places (two CTA mailtos + footer). Replace with the
  real address, or swap the "Book a demo" href for a Calendly/Cal.com link once you have one
  (a scheduling link converts better than mailto for investor traffic).
- If the company is renamed, the wordmark, `<title>`, meta description, and copy all say
  LidNote — search-and-replace, and re-issue the domain/CNAME accordingly.

## Design notes (for future edits)

- Brand tokens are CSS custom properties at the top of the inline stylesheet
  (ink #1B2137, ice #C7D6EF, green #2EC79B) — matched to the pitch deck.
- Fonts: Sora (display/UI) + STIX Two Text (body; the math-publishing typeface — deliberate).
- The hero canvas animation is the dodecahedron–icosahedron dual from the demo: the
  icosahedron seats itself every ~11s and gets a solver-verified pulse. It honours
  `prefers-reduced-motion` by rendering a static seated frame with the caption shown.
- No analytics included. If you add any, prefer a cookieless option (e.g. Plausible/GoatCounter)
  so no consent banner is needed.
