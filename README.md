# trainlikethem

Documented training splits and diets from actors, athletes, bodybuilders and everyday lifters. Static site — no build step, no dependencies.

## Deploying

Netlify serves this repo as-is. In Netlify: **Add new site → Import an existing project → GitHub → trainlikethem**. Leave the build command empty and set the publish directory to the repo root. Every push to `main` redeploys.

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The whole site — all pages, all data, all photos inlined. 1.2 MB, self-contained. |
| `netlify.toml` | Deploy config. Publishes the repo root, no build step. |

`index.html` is generated, not hand-edited. It is compiled from the design source (`TrainLikeThem.dc.html` + `programs.js`), with the five profile photos downscaled to 1400px JPEG and embedded as data URLs.

## Before launch

- **Photo credits are unfilled.** Every profile hero currently displays "Photo credit pending — not cleared for publication". Fill the `credit` field per program in the source data, or replace the photos with licensed ones.
- **The newsletter form collects nothing.** It renders but has no provider behind it. Netlify Forms is the shortest path: add the `netlify` attribute to the `<form>` and submissions appear in the Netlify dashboard.
- **Routing is hash-based** (`#/p/chris-hemsworth-thor-mass-block`), so profiles are not separately indexable. Given the traffic model is search, this is the biggest SEO gap.

## Content status

35 programs listed. Five written out in full with a complete training week, macros, supplement stack, progression rules, and four-day / three-day / dumbbell-only adaptations:

- Chris Hemsworth — Thor mass block
- Hugh Jackman — Wolverine strength
- Arnold Schwarzenegger — golden era
- Dwayne Johnson — off-season week
- David Goggins — volume base

The remaining 30 are sourced and summarised, and show a "full week not written up yet" state on their profile page.
