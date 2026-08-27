# BENDEFORM — one pager

Static site. No build step, no framework, no npm.

```
index.html                      single file: markup + CSS + ~60 lines JS
assets/organism-open.webp       hero / "open state"
assets/organism-closed.webp     "closed state" + contact backdrop
assets/organism-hero.webp       social preview image (og:image)
assets/bendeform-portrait.webp  artist portrait
assets/logo.webp                logo mark, background keyed to transparent
assets/logo-512.png             favicon / apple-touch-icon (PNG with alpha)
assets/logo-192.png             favicon
```

The logo appears in the header, above the hero wordmark, in the contact block and
in the footer; it is also the favicon. Sizes are set in CSS (`.brand .mark`,
`.hero-mark`, `.contact .mark-lg`, `footer .mark`).

Total ~1.1 MB. Opens by double-clicking `index.html`.

## Hosting

Drop the whole folder on any static host:

- Netlify Drop — drag the folder onto https://app.netlify.com/drop
- Cloudflare Pages / Vercel — connect or upload, no build command
- GitHub Pages — push, enable Pages on the branch root
- Classic webspace (All-Inkl etc.) — upload the folder contents to the web root by FTP

`bendeform.de` currently does not serve a valid certificate (parked on kasserver),
so the domain needs to be pointed at the host before it will load over HTTPS.

## External dependencies

- Google Fonts (Archivo + JetBrains Mono) — one `<link>`, with system fallbacks
- YouTube thumbnails on the reel cards; the video only loads after a click
  (`youtube-nocookie.com`), so nothing from YouTube runs until then

To go fully self-contained, download the two font families into `assets/` and
replace the `<link>` with `@font-face` rules.

## Editing

Everything is in `index.html`:

- Colours — the `:root` block (VOID / VIOLET / LILAC / MAGENTA / CYAN / ACID)
- Reel videos — the `var videos = [...]` array at the bottom: `["<youtube-id>", "Title", "Sub-label"]`
- Workshop date, venue, registration — the `#workshop` section
- Festivals and artist credits — the `#work` section

## Content sources

Copy and imagery are taken from the `ENTER THE ORGANISM` LPM 2026 deck and the
Projection Mapping Workshop presskit. Links, video IDs and the credits list were
verified against youtube.com/@bendeform, instagram.com/bendeform_vj,
facebook.com/bendeform and nanocaos.framer.website.
