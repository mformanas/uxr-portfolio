# Ready for people? — A Shakti story

A scrollytelling website explaining how a product manager uses Shakti
(synthetic user orchestration) to explore the human experience of an agentic
agentic app before launch.

## Files

- `index.html` — page structure, narrative cards, environment panel
- `css/styles.css` — shareable stylesheet (design tokens, layout, mobile rules)
- `js/app.js` — locally generated SVG artwork + scroll-driven choreography
- `shakti-story-standalone.html` — single offline file with CSS and JS embedded
- `serve.py` — optional local server: `python3 serve.py 8765`

No external assets, fonts, or libraries are required. Open `index.html`
directly or serve the folder.

## How it works

- Global scroll position `g` runs from chapter 1 to 15. Chapter `n` is
  settled for `g ∈ [n, n+0.5]`; transitions to the next chapter happen for
  `g ∈ [n+0.55, n+0.95]`. Every element's position, size and opacity is a
  pure function of `g` (see `track()` in `js/app.js`), so scrolling up
  reverses every transition.
- Chapter 12 (six synthetic users) has 3× scroll distance.
- Autonomous animation is limited to the hero reveal, the three product
  checks (2.4 s, replayed on re-entry), and the evaluation arrowheads.
  `prefers-reduced-motion` disables those.
- Hand-drawn look: seeded jitter (`rng()`), rough rectangles/circles, a fine
  hatch pattern over fills, pencil outlines.
- The environment panel is a real form; its choices are handwritten beside the
  Environment input and do not change the page's own accessibility settings.
