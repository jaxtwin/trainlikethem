# trainlikethem

Documented training splits and diets from actors, athletes, bodybuilders and everyday lifters. Static site — no build step, no dependencies.

## Deploying

Netlify serves this repo as-is: no build command, publish directory `.`. Every push to `main` redeploys.

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The whole site — every page, hash-routed. Real `<head>` metadata for crawlers. |
| `programs.js` | All program data: the 35 listings, five full write-ups, progression rules, meals. |
| `support.js` | Rendering runtime. Generated — do not edit. |
| `photos/` | Profile photos, 1400px WebP. |
| `netlify.toml` | Deploy config. |

Edit content in `programs.js`. Edit layout and copy in `index.html`.

## Before launch

- **Photo credits are unfilled.** Every profile hero displays "Photo credit pending — not cleared for publication". Fill the `credit` field per program in `programs.js`, or replace the photos with licensed ones.
- **The newsletter form collects nothing.** It renders but has no provider behind it. Netlify Forms is the shortest path: add the `netlify` attribute to the `<form>` and submissions appear in the Netlify dashboard.
- **Routing is hash-based** (`#/p/chris-hemsworth-thor-mass-block`), so profiles are not separately indexable. Given the traffic model is search, this is the biggest SEO gap.

## Content status

35 programs listed. Five written out in full — complete training week, macros, supplement stack, progression rules, and four-day / three-day / dumbbell-only adaptations:

- Chris Hemsworth — Thor mass block
- Hugh Jackman — Wolverine strength
- Arnold Schwarzenegger — golden era
- Dwayne Johnson — off-season week
- David Goggins — volume base

The remaining 30 are sourced and summarised, and show a "full week not written up yet" state on their profile page.
