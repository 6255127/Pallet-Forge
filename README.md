# PaletteForge
 
drop a photo in, get a real color system out. not just hex codes — which color's the background, does the text pass accessibility, what does a button look like with it.
 
built this because i kept doing the same annoying thing every project: opening a color picker site, eyeballing 5 hex codes, realizing none of them had good contrast, starting over.
 
---
 
## what it does
 
**pulls colors from an image** — k-means clustering finds the 6 colors that actually dominate the photo, not random samples. merges near-duplicates.
 
**figures out what each color is for** — decides background, text, primary, accent based on how light/dark and saturated each color is.
 
**checks if your text will be readable** — full WCAG contrast matrix, every color against every other. tells you what passes and what fails.
 
**shows real components, not mockups** — actual buttons, cards, inputs styled live with your palette. the feature i wanted most and couldn't find anywhere else.
 
**tints and shades** — 10-step scale per color, same idea as tailwind's color scale.
 
**gradients** — linear, radial, conic, mesh. click one, css gets copied.
 
**dark and light mode CSS** — generates both, with a live preview.
 
**exports** — Figma Tokens, W3C Tokens, Style Dictionary, Tailwind config.
 
**colorblind check** — simulates 6 types of color vision deficiency. ~8% of men have some form of this.
 
**font pairings** — 6 pairs, picked to match the palette's mood.
 
**share via link** — palette gets encoded into the URL.
 
---
 
## how to use it
 
open the html file in a browser. that's it.
 
drop in an image (or type a hex code). it pulls a palette automatically. click through the tabs — design system, components, tints, gradients, dark/light, tokens, colorblind, fonts, analytics, exports. copy what you need.
 
works offline except for the google fonts used in font previews.
 
---
 
## why it looks the way it does
 
first version was dark mode, blue accent, sidebar, perfectly even grid — worked fine, looked like every other hackathon project.
 
rebuilt it lighter: warm cream background instead of black, an accent color that isn't blue or violet, a grid where cards aren't all the same size. looked at some layouts on 21st.dev to get a feel for irregular bento grids, then built it by hand in css.
 
---
 
## the build
 
vanilla js, no react, no build step. one html file, open it from downloads or host it anywhere.
 
wanted something genuinely frictionless — no setup, no account, works the second you open it. images never leave your browser since there's no backend.
 
devlog.md has the messier version of how this got built, bugs included.
 
---
 
## being upfront
 
- k-means starts from random points, so the same image can give slightly different colors each run. close every time, not identical.
- works best on photos with distinct color areas. a plain sky photo gives a less interesting palette.
- colorblind simulation is a standard matrix approximation, good for catching obvious problems, not a replacement for real testing.
---
