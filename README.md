# Aditya Gautam — Cloud Engineer Portfolio

A scroll-driven, single-page portfolio site built as a "pipeline" narrative — a WebGL (Three.js) background scene that responds to scroll position, layered under glassmorphic content panels animated in with GSAP ScrollTrigger.

**Live demo:** _add your deployed URL here once published_

## ✨ Features

- **3D "Pipeline" background** — a Three.js scene (a tube/spline with animated data packets and cluster nodes) whose camera moves along the pipe as you scroll.
- **Hero "gem" scene** — a second, self-contained Three.js scene (a faceted icosahedron core with orbiting rings) that gently tracks the cursor.
- **Scroll-driven reveals** — GSAP + ScrollTrigger fade/slide content in as each section enters the viewport, and drive a top progress bar.
- **Single content source** — all real copy (projects, experience, certifications, etc.) lives in one `CONTENT` JavaScript object. Update that object and the render functions rebuild the DOM automatically — no need to touch markup or the WebGL code.
- **Accessible by default** — respects `prefers-reduced-motion`, keyboard-focusable nav links, semantic headings.
- **No build step** — plain HTML/CSS/JS. Fonts and libraries (Three.js, GSAP) are loaded from CDNs.

## 📁 Project structure

```
.
├── index.html      # Entire site: markup, styles, content data, and scripts
├── README.md        # This file
└── LICENSE           # MIT license
```

Everything — CSS, content data, render logic, and the two Three.js scenes — lives inside `index.html`, organized into clearly labeled sections (see the comment block at the top of the file for a map).

## 🚀 Getting started

No build tools or dependencies to install. Just serve the file statically.

### Option 1 — Open directly
Double-click `index.html`, or open it in a browser. (Some browsers restrict certain features under the `file://` protocol — a local server is more reliable, see below.)

### Option 2 — Local server (recommended)
```bash
# Python 3
python3 -m http.server 8000

# Node (npx)
npx serve .
```
Then visit `http://localhost:8000`.

## ✏️ Updating content

All real content (name, roles, projects, work history, certifications, links, etc.) lives inside the `CONTENT` object, defined in a `<script id="content-data">` block near the bottom of `index.html`. Edit values there — the render logic that follows rebuilds the DOM (and associated 3D waypoints) from that object automatically.

You should not need to touch the WebGL/Three.js code unless you want to change the *visual style* of the pipeline itself (colors, geometry, node counts, etc.). Color tokens are also centralized as CSS custom properties (`:root` variables) at the top of the `<style>` block, so palette changes can usually be made in one place.

## 🌐 Deploying

This is a static site, so it can be hosted anywhere that serves static files:

- **GitHub Pages** — Settings → Pages → Deploy from branch → `main` / root. Your site will be live at `https://<username>.github.io/<repo>/`.
- **Netlify / Vercel** — drag-and-drop the folder or connect the repo; no build command needed (or set the build command to a no-op and publish directory to `/`).
- **Any static host** — S3 + CloudFront, Azure Static Web Apps, Cloudflare Pages, etc.

## 🛠️ Built with

- [Three.js](https://threejs.org/) (r128) — WebGL 3D scenes
- [GSAP](https://gsap.com/) + [ScrollTrigger](https://gsap.com/docs/v3/Plugins/ScrollTrigger/) — scroll-driven animation
- [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk), [Inter](https://fonts.google.com/specimen/Inter), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) — via Google Fonts

## 📄 License

MIT — see [LICENSE](LICENSE).
