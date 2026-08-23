# trainlikethem

Documented training splits and diets from actors, athletes, bodybuilders and everyday lifters. Static site — no build step, no dependencies.

## Deploying

Netlify serves this repo as-is: no build command, publish directory `.`. Every push to `main` redeploys.

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The app shell and every page's markup. Real paths, real `<head>` metadata. |
| `programs.js` | All program data: the 35 listings, five full write-ups, progression rules, meals. |
| `support.js` | Rendering runtime. Generated — do not edit. |
| `*.webp` | Profile photos, 1400px WebP, at the repo root. |
| `netlify.toml` | Deploy config: cache headers, catch-all fallback. |
| `<slug>/index.html` | **Generated.** One prerendered page per program and per route — unique title, description, canonical, JSON-LD, and the full write-up as crawlable HTML. Do not hand-edit; regenerate. |
| `sitemap.xml`, `robots.txt` | **Generated.** |
| `.gen/` | Prerender inputs: `shell.html` (clean app shell) and `lib.js` (page builder). |

Edit content in `programs.js`. Edit layout and copy in `index.html`.

## Regenerating the prerendered pages

`index.html`, `programs.js` and `.gen/lib.js` are the sources of truth. Any change to them means the 44 generated pages are stale — ask Claude to re-run the prerender, which rewrites `.gen/shell.html`, every `<slug>/index.html`, `sitemap.xml` and `robots.txt` from them. Adding a program to `programs.js` without regenerating means it works on the site but has no indexable page of its own.

## Canonical host

Every generated canonical, `og:url` and JSON-LD url points at `https://trainlikethem.netlify.app` (the host that is actually serving). When `trainlikethem.com` is attached and resolving, change `ORIGIN` in `.gen/lib.js` and regenerate — canonicals pointing at a host that does not resolve suppress indexing.

## Before launch

- **Photo credits are unfilled.** Every profile hero displays "Photo credit pending — not cleared for publication". Fill the `credit` field per program in `programs.js`, or replace the photos with licensed ones.
- **The newsletter form collects nothing.** It renders but has no provider behind it. Netlify Forms is the shortest path: add the `netlify` attribute to the `<form>` and submissions appear in the Netlify dashboard.
- **Photo hosting.** Hero images are preloaded per page. If profiles get replaced with licensed sets, keep them WebP and keep the total under ~500 KB.

## Content status

35 programs listed. Five written out in full — complete training week, macros, supplement stack, progression rules, and four-day / three-day / dumbbell-only adaptations:

- Chris Hemsworth — Thor mass block
- Hugh Jackman — Wolverine strength
- Arnold Schwarzenegger — golden era
- Dwayne Johnson — off-season week
- David Goggins — volume base

The remaining 30 are sourced and summarised, and show a "full week not written up yet" state on their profile page.
