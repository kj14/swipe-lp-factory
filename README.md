# swipe-lp-factory

Static, dependency-free demo for a **TikTok-like swipe LP**.

- `swipe.html`: full-screen vertical swipe experience (mobile-first)
- `slides.json`: content source (titles/body/cta/bg image path)

## GitHub Pages
- Home: `/`
- Swipe demo: `/swipe.html`

## Replace images
Put your generated images under `slides/` and reference them in `slides.json`:

```json
{ "bg": "slides/01.jpg" }
```

## Notes
- Designed to work on iOS Safari (touch handlers + translate3d).
- Minimal analytics hooks are `console.log` only.
