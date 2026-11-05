# online-cv

My CV as a single static page: **[cv.magniff.dev](https://cv.magniff.dev)**

It's one hand-written `index.html`: no build step, no framework, no dependencies
beyond the JetBrains Mono web font (with a system monospace fallback).

- Dark, monospace, terminal-flavoured design that works on desktop and mobile
- Respects `prefers-reduced-motion`
- A dedicated print stylesheet turns the page into a dense one-page A4 CV;
  use the `↓ pdf` button or your browser's *Print → Save as PDF*

## Run locally

```sh
python3 -m http.server 8000
# → http://localhost:8000
```

Or just open `index.html` in a browser.

## Deploy

GitHub Pages serves the `gh-pages` branch at `cv.magniff.dev` (see `CNAME`;
DNS: `cv` CNAME → `magniff.github.io`). `.nojekyll` makes Pages serve the
files as they are, without running Jekyll. To publish, push the same tree to
`gh-pages`:

```sh
git push origin master:gh-pages
```

## Editing

All content lives in `index.html`. Each section is a `<section class="block">`
labelled `0x00`–`0x04`. Jobs are `<article class="job">` entries in the
`#work` timeline. Print layout tweaks are in the `@media print` block at the
end of the stylesheet.
