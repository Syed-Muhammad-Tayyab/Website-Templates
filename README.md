# Nocturne — Aurora

A premium, cinematic promotional website for **Aurora**, a fictional
bedside sleep instrument by **Nocturne Instruments**. Built as a
portfolio piece: four pages, scroll-driven storytelling, a 3D hero
object, and Framer Motion throughout.

**Stack:** React 18 · Vite · React Router · Framer Motion · Three.js /
React Three Fiber (`@react-three/fiber`, `@react-three/drei`)

## Pages

| Route | Description |
|---|---|
| `/` | Cinematic hero, press marquee, feature showcase, sticky "night phases" storytelling section, horizontal-scroll materials showcase, animated stats, testimonials, final CTA |
| `/product` | Product deep dive — alternating feature rows, full spec sheet, materials grid |
| `/technology` | Circadian science explainer with an animated SVG curve, company timeline |
| `/contact` | Pricing plans, a functional (client-side) pre-order form, FAQ accordion |

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (usually `http://localhost:5173`).

```bash
npm run build     # production build to /dist
npm run preview   # preview the production build locally
```

## Project structure

```
src/
  components/   Reusable UI: Navbar, Footer, Reveal/TextReveal motion
                wrappers, the 3D Orb, TiltCard, MagneticButton, etc.
  sections/     Page sections (Hero, StickyStory, Pricing, FAQ, ...)
  pages/        Home, Product, Technology, Contact — compose sections
  data/         content.js — all copy, specs, pricing, FAQ, timeline
```

Content lives in one place (`src/data/content.js`) so copy can be
edited without touching layout code.

## Notes on performance

- The only WebGL canvas (`Orb3D`) is capped to a max device pixel
  ratio of 1.6 and reused on both the Home hero and the Product page.
- Scroll-linked animations use Framer Motion's `useScroll` /
  `useTransform`, which read from the compositor thread rather than
  triggering layout on every frame.
- `prefers-reduced-motion` is respected globally in `index.css`.

## Publishing this to GitHub

```bash
git init
git add .
git commit -m "Initial commit: Nocturne — Aurora landing site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

To get a live link, import the repo on [Vercel](https://vercel.com/new)
or [Netlify](https://app.netlify.com/start) — both auto-detect Vite and
need no configuration.

## License

MIT — see `LICENSE`.
