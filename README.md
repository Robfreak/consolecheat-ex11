# Audio-Kanal-Test

Stereo-Kanaltest links, rechts, beide, mit Web Audio im Browser. Teil der inoffiziellen consolecheat-Werkzeuge rund um [consolecheat.com](https://consolecheat.com). German is the primary language, English is the other. Light and dark theme, self-hosted fonts, footer, Impressum, and Datenschutz are included. There is no Webmail link.

No account, no tracking, nothing uploaded. Fonts (Outfit, Source Sans 3) are self-hosted from `@fontsource`, so the page makes no request to Google or any other third party. The Impressum fields are placeholders until the operator fills them in. No name or address was invented.

Site: <https://robfreak.github.io/consolecheat-ex11/>

Inoffiziell. Nicht von Sony.

## What it does

A local stereo channel check. Open it at `/consolecheat-ex11/`. German is the default. English is the other language. Light and dark follow `consolecheat-theme`.

**Links**, **Rechts**, and **Beide** (center: the same full-scale signal on the left and the right). The sound is a sine tone, pink noise, or a short beep, generated with the Web Audio API (`OscillatorNode` and `BufferSource`). No audio file is fetched. Nothing is uploaded. There is no microphone and no recording. You have to click, or press `1` (left), `2` (right), or `3` (both), before any sound starts. `Esc` stops it. If `AudioContext` stays suspended, the page says the browser is holding the sound until the next click. Volume stays in the page and is not stored.

Headphones or speakers. If Left is heard on the right, the cable or the plug is swapped. The browser mixer, the operating-system mixer, and a TV passthrough can remap channels, so the test applies to this output.

Language and appearance reuse `consolecheat-lang` and `consolecheat-theme`. Links on the page point at the screen test and the HDR helper, the other picture checks.

## Storage

- `consolecheat-lang` and `consolecheat-theme` (localStorage, shared with the other consolecheat tools on robfreak.github.io)

The Datenschutz page has a button that removes this page's keys. Nothing else is stored.

## Run and test

```bash
npm install
npm test        # node --experimental-strip-types --test src/audio/*.test.ts
npm run dev     # http://127.0.0.1:5173/consolecheat-ex11/
npm run build   # typecheck, Vite build (base /consolecheat-ex11/), offline check of dist/
npm run preview # http://127.0.0.1:4173/consolecheat-ex11/
```

Node `>=22.6` (`package.json` `engines`).

## Files

- `index.html` — the HTML entry (Vite input)
- `src/audio/` — React + TypeScript source, styles, and tests
- `src/audio/tools.ts` + `src/audio/tool-links.tsx` — the footer list **Weitere Werkzeuge** (keep it identical across the consolecheat repos)
- `public/` — `favicon.svg`, `FONT-OFL.txt`, `.nojekyll`
- `scripts/check-dist.mjs` — offline check of `dist/` (no third-party hosts, no `.woff` fallback, woff2 fonts present)
- `.github/workflows/pages.yml` — test, build, and deploy to `gh-pages`

## Other tools

The footer group **Weitere Werkzeuge** (English: **Other tools**) links to the other consolecheat tools: Title-ID-Finder (ex1), PS-Plus-Archiv (ex2), Controller-Tester (ex3), Save-Info-Leser (ex4), Fehlercode-Nachschlager (ex5), the [Spiele-Merkliste](https://robfreak.github.io/consolecheat-ex6/), and [Bildschirm-Test](https://robfreak.github.io/consolecheat-ex7/), [Download-Zeit-Rechner](https://robfreak.github.io/consolecheat-ex8/), [Tastenbelegung](https://robfreak.github.io/consolecheat-ex9/), [HDR/Helligkeit](https://robfreak.github.io/consolecheat-ex10/), [USB-Stick-Checkliste](https://robfreak.github.io/consolecheat-ex12/), [Combo-Trainer](https://robfreak.github.io/consolecheat-ex13/), [Sprite-Animator](https://robfreak.github.io/consolecheat-ex14/). These are ordinary links. The page does not request those sites.

This tool was moved here from [Robfreak/consolecheat-ex6](https://github.com/Robfreak/consolecheat-ex6).

## GitHub Pages

`.github/workflows/pages.yml` runs install, test, and build on pull requests and on every push. A push to `main` also pushes `dist/` to the orphan branch `gh-pages` (`peaceiris/actions-gh-pages`, Jekyll off). Vite `base` is `/consolecheat-ex11/`, which matches the project site <https://robfreak.github.io/consolecheat-ex11/>.

Enable once in the repository settings:

1. **Settings → Actions → General → Workflow permissions → Read and write permissions.** Save.
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch.** Branch: **`gh-pages`**, folder: **`/ (root)`.** Save.

After that, every push to `main` updates the site.

## Credits

Outfit and Source Sans 3 are bundled from `@fontsource` under the SIL Open Font License; see `public/FONT-OFL.txt` and `THIRD_PARTY_NOTICES.md`.

Replace the Impressum placeholders with the operator’s real details before treating that page as a legal notice.
