<div align="center">

# 🌙 Nocturne — Aurora

**A cinematic, scroll-driven product site for a sleep instrument that doesn't exist — built like one that does.**

*React 18 · Vite · Framer Motion · React Three Fiber*

[![React](https://img.shields.io/badge/React-18.3-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-5.4-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev)
[![Three.js](https://img.shields.io/badge/react--three--fiber-8.17-000000?style=flat-square&logo=three.js&logoColor=white)](https://docs.pmnd.rs/react-three-fiber)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-11.11-0055FF?style=flat-square&logo=framer&logoColor=white)](https://www.framer.com/motion/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](./LICENSE)

[Live Demo](#) · [Getting Started](#-getting-started) · [Project Structure](#-project-structure) · [License](#-license)

</div>

---

## ✨ Overview

**Aurora** is a fictional bedside sleep instrument from **Nocturne Instruments** — and this repo is its promotional website, built as a portfolio-grade showcase of modern front-end craft rather than a template. It leans on scroll-linked storytelling, a real-time 3D hero object, and micro-interactions throughout, while staying performant and accessible.

Four routes, one content source of truth, zero disposable batteries (fictionally speaking).

## 🎬 Highlights

| | |
|---|---|
| 🪐 **Interactive 3D hero** | A `react-three-fiber` orb rendered live in the browser, with a static SVG fallback for low-power devices and reduced-motion users |
| 📜 **Scroll-driven storytelling** | A sticky "night phases" narrative and a horizontal-scroll materials showcase, both compositor-driven via Framer Motion's `useScroll` / `useTransform` |
| 🎯 **Micro-interactions** | Magnetic buttons, tilt cards, cursor glow, animated text reveals, and a scroll progress indicator |
| ⚡ **Performance-minded** | Single shared WebGL canvas capped at 1.6x DPR, `prefers-reduced-motion` respected globally, no layout-thrashing animations |
| 🧠 **Content/layout separation** | Every word of copy lives in one file (`src/data/content.js`) — restyle freely without touching content, or vice versa |

## 🗺️ Pages

| Route | What's there |
|---|---|
| `/` | Cinematic hero, press marquee, feature showcase, sticky "night phases" narrative, horizontal-scroll materials showcase, animated stats, testimonials, final CTA |
| `/product` | Product deep dive — alternating feature rows, full spec sheet, materials grid |
| `/technology` | Circadian science explainer with an animated SVG curve, company timeline |
| `/contact` | Pricing plans, a functional client-side pre-order form, FAQ accordion |

## 🧰 Tech Stack

- **[React 18](https://react.dev)** with **[React Router](https://reactrouter.com)** for routing
- **[Vite 5](https://vitejs.dev)** for the dev server and build pipeline
- **[Framer Motion](https://www.framer.com/motion/)** for scroll, gesture, and layout animation
- **[React Three Fiber](https://docs.pmnd.rs/react-three-fiber) + [drei](https://github.com/pmndrs/drei) + [Three.js](https://threejs.org)** for the 3D hero object

## 🚀 Getting Started

**Prerequisites:** Node.js 18+ and npm

```bash
# Clone the repo
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Install dependencies
npm install

# Start the dev server
npm run dev
```

Then open the local URL Vite prints (usually `http://localhost:5173`).

```bash
npm run build     # production build → /dist
npm run preview   # preview the production build locally
```

## 📁 Project Structure

```
src/
├── components/     Reusable UI — Navbar, Footer, Reveal / TextReveal motion
│                   wrappers, the 3D Orb (+ fallback), TiltCard,
│                   MagneticButton, CursorGlow, ScrollProgress, ErrorBoundary
├── sections/       Page sections — Hero, StickyStory, HorizontalScroll,
│                   Pricing, FAQ, SpecSheet, Testimonials, Timeline, ...
├── pages/          Home, Product, Technology, Contact — compose sections
├── data/           content.js — all copy, specs, pricing, FAQ, timeline
├── App.jsx         Route definitions
└── main.jsx        App entry point
```

Content lives in one place (`src/data/content.js`) so copy can be edited without touching layout code.

## 🎨 Performance & Accessibility Notes

- The only WebGL canvas (`Orb3D`) is capped to a max device pixel ratio of `1.6` and reused across the Home hero and Product page.
- Scroll-linked animations read from the compositor thread (Framer Motion's `useScroll` / `useTransform`) instead of triggering layout on every frame.
- `prefers-reduced-motion` is respected globally in `index.css`.
- A dedicated `OrbFallback` and `ErrorBoundary` keep the experience graceful when WebGL isn't available.

## 📦 Deploying

This is a static Vite build, so it ships anywhere that serves static files:

```bash
npm run build
```

Import the repo directly on **[Vercel](https://vercel.com/new)** or **[Netlify](https://app.netlify.com/start)** — both auto-detect Vite with zero configuration.

## 📜 License

Released under the **[MIT License](./LICENSE)** — free to use, modify, and build on.

---

<div align="center">

Built with 🌌 by <strong>Nocturne Instruments</strong> — a fictional brand, a very real front-end.

</div>
