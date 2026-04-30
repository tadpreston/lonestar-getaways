# Lonestar Getaways

Marketing website for **Lonestar Getaways**, a Texas-based travel advisory affiliated with [Fora Travel](https://www.foratravel.com/advisor/tad-preston).

> Journeys that last a lifetime

**Live site:** _add your URL once deployed (e.g. `https://lonestargetaways.com`)_
**Owner:** Tad Preston · tad.preston@fora.travel · (972) 832-6284

---

## What's in this repository

```
.
├── index.html        ← the entire single-page site
├── images/
│   ├── lsg-logo.png  ← logo (also used as favicon)
│   ├── cruise-hero.jpg ← hero background + "Cruises" inspiration tile + OG share image
│   └── tad.jpg       ← portrait used in the About section
├── .nojekyll         ← tells GitHub Pages to skip Jekyll processing
└── README.md         ← this file
```

The site is a single static HTML file — no build step, no server, no database.

---

## Tech stack

- **HTML5** — single-file structure
- **[Tailwind CSS](https://tailwindcss.com)** via CDN with a custom theme for the brand palette
- **[Lucide icons](https://lucide.dev)** via CDN, with three brand/category icons inlined as SVG (Facebook, Instagram, palm tree — Lucide removed these in late 2024)
- **[Formspree](https://formspree.io)** AJAX SDK for the "Plan Your Trip" intake form
- **[Google Analytics 4](https://analytics.google.com)** with custom `cta_click` and `generate_lead` events
- **[Google Fonts](https://fonts.google.com)** — Playfair Display (display) + Inter (body)

### Brand palette

| Color | Hex | Usage |
|---|---|---|
| Brand red | `#B3001B` | Primary CTAs, accents |
| Charcoal | `#262626` | Body text, dark sections |
| Brand blue | `#255C99` | Secondary accents |
| Sky | `#7EA3CC` | Eyebrow text on dark backgrounds |
| Sand | `#CCAD8F` | Tertiary, all-inclusive icon |

---

## How to make edits

### Quick edits (web UI)

1. Go to the repo on github.com.
2. Click `index.html`, then click the pencil icon to edit.
3. Make your changes, scroll down, and click **Commit changes**.
4. Wait ~1 minute for GitHub Pages to redeploy. Refresh the live site.

### Bigger edits (download → edit → upload)

1. Click the green **Code** button on the repo and choose **Download ZIP**.
2. Unzip and edit `index.html` in any text editor.
3. Drag the modified file back into the repo on github.com (it will replace the existing file).
4. Commit, wait, refresh.

---

## Deployment

This repository is configured to deploy via **GitHub Pages**. Any commit to the `main` branch triggers a redeploy automatically (typically live within 1–3 minutes).

### Initial setup (already done if you can see this site live)

1. Repo Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)**
4. Save

### After your first deploy — update social-share placeholders

The Open Graph / Twitter Card / JSON-LD tags in `index.html` use `SITE_URL_PLACEHOLDER` as a stand-in for your real URL. After deploy, do a find-and-replace on `SITE_URL_PLACEHOLDER` and replace with your full live URL (no trailing slash), e.g. `https://lonestargetaways.com`. Commit and you're done.

---

## Third-party services to keep in sync

When the live URL changes (e.g. you add a custom domain), update three places:

1. **Formspree** dashboard → form `mzdynvrk` → Allowed Domains
2. **Google Analytics 4** → Admin → Data Streams → Web stream URL
3. The `SITE_URL_PLACEHOLDER` strings inside `index.html`

---

## Custom domain (optional)

To serve the site at a custom domain like `lonestargetaways.com`:

1. Buy the domain from a registrar (Namecheap, Cloudflare, Squarespace).
2. Add a `CNAME` file at the root of this repo containing just your bare domain (e.g. `lonestargetaways.com`).
3. In repo Settings → Pages, enter the custom domain and save.
4. At your registrar, configure DNS:
   - Apex (`lonestargetaways.com`) → four A records:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - `www` → CNAME pointing to `<your-username>.github.io`
5. Wait for DNS to propagate (10 min – a few hours), then check **Enforce HTTPS** in Pages settings.

---

## License

All rights reserved. Brand assets and copy are property of Lonestar Getaways / Tad Preston.
