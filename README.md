# Azad Home Stay — Premium Website

A high-end, single-page website for Azad Home Stay, Mangalore. Static HTML/CSS/JS — no build step, deploys instantly on Vercel.

---

## 1. How to add YOUR images

The site currently shows **placeholder images** so everything works out of the box. To use your real photos, simply drop them into the `assets/` folders below using these **exact filenames** (lowercase, no spaces). Don't rename anything in the code — just match these names.

```
azad-home-stay/
├── index.html
├── favicon.png          ← auto-generated from logo (replace if you want your own)
├── vercel.json
├── lib/                 ← animation libraries (DON'T touch)
└── assets/
    ├── logo.png         ← YOUR logo (transparent PNG, square works best)
    ├── hero.jpg         ← YOUR main cover photo (wide landscape, 2000px+ wide)
    ├── gallery/
    │   ├── gallery-01.jpg   ← your 18 gallery photos,
    │   ├── gallery-02.jpg      numbered 01 through 18
    │   ├── ...                 (must be zero-padded: 01, 02 … not 1, 2)
    │   └── gallery-18.jpg
    └── nearby/
        ├── panambur-beach.jpg
        ├── tannirbhavi-beach.jpg
        ├── city-centre-mall.jpg
        ├── kadri-temple.jpg
        ├── st-aloysius-chapel.jpg
        ├── nosh-cafe.jpg
        ├── machali.jpg
        └── sultan-bathery.jpg
```

### Notes
- **Extensions:** the code expects `.jpg`. If your photos are `.png` or `.webp`, easiest is to rename/save them as `.jpg`.
- **Gallery:** must be `gallery-01.jpg` … `gallery-18.jpg`. The two photos shown in the About section reuse `gallery-02.jpg` and `gallery-05.jpg`.
- **Nearby places:** these are optional. Free-to-reuse photos can be downloaded from the "Explore" link on each card (Wikimedia Commons / Google Maps). Just save them with the names above into `assets/nearby/`. Until then, the branded placeholders show automatically.
- **Optimize for speed:** before uploading, compress photos at <https://squoosh.app> (aim for under ~400 KB each). Images are already lazy-loaded.

---

## 2. Deploy to Vercel

### Option A — Drag & drop (fastest, no GitHub needed)
1. Go to <https://vercel.com> and sign up / log in (free).
2. On your dashboard click **Add New → Project**.
3. Choose **Deploy** → at the bottom look for the option to deploy a folder, OR install the Vercel CLI:
   ```
   npm i -g vercel
   cd azad-home-stay
   vercel
   ```
   Follow the prompts (accept defaults). Your site goes live in seconds.

### Option B — GitHub (recommended for easy future edits)
1. Create a free GitHub account at <https://github.com>.
2. Create a new repository (e.g. `azad-home-stay`), keep it public or private.
3. Upload the whole `azad-home-stay` folder. Easiest way in your terminal:
   ```
   cd azad-home-stay
   git init
   git add .
   git commit -m "Initial Azad Home Stay website"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/azad-home-stay.git
   git push -u origin main
   ```
   (Or use GitHub's web "Upload files" button to drag the folder in.)
4. Go to <https://vercel.com> → **Add New → Project** → **Import** your GitHub repo.
5. Framework Preset: **Other** (it's a static site). Leave build settings empty. Click **Deploy**.
6. Done! Every time you push a change to GitHub, Vercel redeploys automatically.

### Custom domain (optional)
In your Vercel project → **Settings → Domains** → add `azadhomestay.com` (or your domain) and follow the DNS instructions.

---

## 3. What's included
- Smooth momentum scrolling (Lenis), scroll-reveal & parallax (GSAP), 3D tilt cards (vanilla-tilt), lightbox gallery (GLightbox).
- Animated counters, sticky shrinking navbar, scroll progress bar, animated hamburger, custom cursor (desktop), back-to-top, floating WhatsApp button.
- Booking form that validates and opens WhatsApp (+91 70229 93505) with all details pre-filled — no backend needed.
- Fully responsive (375 / 768 / 1280 / 1920px), touch-friendly, zero horizontal overflow.
- Respects `prefers-reduced-motion`. SEO meta + Open Graph tags + favicon.

## 4. Editing text / contact details
All content is in `index.html`. Search for text to change it. The WhatsApp number is the constant `WA_NUMBER` near the bottom `<script>`, and also appears in `wa.me/` and `tel:` links — update all if the number changes.
