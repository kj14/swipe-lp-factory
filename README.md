# swipe-lp-factory

Dependency-free demo for a **swipe-style LP** (TikTok-like full-screen vertical feed).

## What’s included

- `swipe.html`
  - Full-screen **vertical** slides (`100vh`)
  - Smooth touch swipe with **inertial feel** (velocity + distance threshold)
  - GPU-friendly transforms (`translate3d`) + snap transition
  - Subtle **parallax/scale** while dragging
  - Right-side **progress indicator** (dots)
  - Optional haptic feedback via **Vibration API** (guarded; no-op on iOS Safari)
  - “Rich” CTA overlay (glass card + primary CTA + copy)

- `slides.json`
  - Simple data file used to render slides (no frameworks)

## Run locally

Because `swipe.html` fetches `slides.json`, use a local web server (opening the file directly may block `fetch()` in some browsers).

Examples:

```bash
# from this repo root
python3 -m http.server 8080
# then open
# http://localhost:8080/swipe.html
```

## Editing content (slides.json)

`slides.json` format:

```json
{
  "meta": { "title": "Swipe LP demo", "direction": "vertical" },
  "slides": [
    {
      "id": "intro",
      "eyebrow": "Swipe LP Factory",
      "title": "Slide title",
      "body": "Slide body",
      "bg": "slides/01.jpg",
      "cta": { "label": "今すぐ相談する", "href": "#cta" }
    }
  ]
}
```

### Full-bleed background image placeholder

Each slide uses `bg` (string path) and applies it as a CSS variable:

- `--bg-img: url('slides/01.jpg')`

So you can replace `slides/*.jpg` with generated images and just update the paths.

## Patch steps (what changed)

1. Replaced the old card-based `/swipe demo` with a **full-screen feed** layout.
2. Added touch swipe handling (iOS-friendly `touchmove` + `preventDefault`, `passive:false`).
3. Implemented snap + inertia (velocity/distance based).
4. Added progress dots, parallax/scale while dragging, and a CTA overlay.
5. Added `slides.json` and updated `swipe.html` to render from it.

## Notes

- iOS Safari does not support the Vibration API → haptics are safely ignored.
- For accessibility and reduced motion, transitions are disabled when `prefers-reduced-motion: reduce` is enabled.
