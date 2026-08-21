# gramlingo-landing

GramLingo landing page — static HTML, trilingual (EN / 中文 / Español), no CDN, no build step.

Live at **https://gramlingo.online** (GitHub Pages + CNAME).

App lives at https://app.gramlingo.online (separate repo: `gramlingo`).

## Structure

```
index.html      — full landing page (inline CSS + JS, single file)
privacy.html    — privacy policy
404.html        — branded 404
favicon.svg     — SVG favicon
fonts/          — self-hosted Baloo 2 + DM Sans (woff2)
*.jpg/.webp     — world covers, mascots, OG poster
robots.txt      — allows all, points to sitemap
sitemap.xml     — 2 URLs (home, privacy)
CNAME           — gramlingo.online
.nojekyll       — disables GitHub Pages Jekyll processing
```

## i18n

All visible strings use `data-i18n` keys backed by the inline `L10N` dictionary (EN / zh / es) at the bottom of `index.html`. Language switcher updates `document.documentElement.lang` and all `data-i18n` elements in place. No page reload.

## Layout variants

The body carries variant classes (`hero-a/b/c`, `order-a/b/c`, `world-a/b/c`, `word-a/b/c`, `card-clay/soft/sticker`) — unused variants are `display:none` and exist for A/B testing. Current live config: `hero-b order-a world-b word-a card-clay`.

## Adding content

1. Edit `index.html` directly — no build step.
2. New strings: add key to `L10N` (all 3 languages) + `data-i18n="key"` on the element.
3. New images: drop file in root, reference with relative path, set `width`/`height` attributes + `loading="lazy"`.
4. Commit to `main` — GitHub Pages auto-deploys.
