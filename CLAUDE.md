# Isiah Builds — isiahbuilds.com

Static site served by GitHub Pages from the repo root. Custom domain in `CNAME`.
**No build step, no dependencies, no package.json.** Editing an `.html` file and pushing
to `main` is the whole deploy.

## Run it

```bash
python3 -m http.server 8950
```

Serve from the repo root and open <http://localhost:8950>. (README says
`--directory portfolio` — that is stale, there is no `portfolio/` directory.)

## Layout

| Path | What it is |
|---|---|
| `index.html` | The business page. This is the piece sent to a prospect. |
| `hill-country-exterior/` | Concept — pressure washing |
| `lumen-aesthetics/` | Concept — med spa |
| `ironhide-roofing/` | Concept — storm restoration |
| `hearth-and-hollow/` | Concept — steakhouse |
| `vance-and-rowe/` | Concept — injury law |
| `cutline-lawn-turf/` | Concept — lawn & turf |
| `send/` | Private phone send sheet for outreach. `noindex,nofollow` + disallowed in robots.txt. |
| `posts/` | Social card images. Disallowed in robots.txt. |
| `assets/og.jpg` | Open Graph card for the root page |

## The one rule that shapes everything

**Every page is a single self-contained `index.html` with its own inline `<style>` block.**
No shared stylesheet, no shared section order, no component library. Each concept has a
different palette, a different type pairing, and a different structural device — that
divergence *is* the portfolio. Do not factor out common CSS "to DRY it up"; that destroys
the point of the set.

Type pairing per page (all loaded from a `<link>` in that page's `<head>`):

| Page | Display | Body | Host |
|---|---|---|---|
| `index.html` | Instrument Serif | Inter Tight | Google Fonts |
| `hill-country-exterior` | Clash Display | Archivo | Fontshare |
| `lumen-aesthetics` | Gambetta | Switzer | Fontshare |
| `ironhide-roofing` | Tanker | Ranade | Fontshare |
| `hearth-and-hollow` | Zodiak | General Sans | Fontshare |
| `vance-and-rowe` | Sentient | Supreme | Fontshare |
| `cutline-lawn-turf` | Bricolage Grotesque | Instrument Sans | Google Fonts |

Within a page, colors and spacing come from CSS custom properties on `:root`
(`--bg`, `--fg`, `--accent`, and a `--s2`…`--s10` spacing scale). Follow the page you are
editing — variable *names* differ between pages on purpose (`--ink`, `--bone-3`, `--zinc`,
`--porcelain`…). Match the file, not the other files.

## Honesty guardrails — do not edit these away

These are not stylistic preferences. The whole offer is built on having no fabricated proof.

- **The `.flag` concept banner stays on every concept page**, along with the concept line
  in the footer. They mark these as spec work for fictional businesses.
- **No testimonials, reviews, star ratings, or client results anywhere** — including the
  root page. There are none yet; inventing them poisons the one asset this strategy exists
  to build.
- **No invented settlement figures or case results** on `vance-and-rowe`. Attorney
  advertising is bar-regulated; the page carries a "no legal advice / no attorney–client
  relationship" disclosure and uses a timeline as its signature element instead.
- **Keep the scope-of-practice and price-advertising disclosures** on `lumen-aesthetics`,
  and the "deadlines are set by your policy, not a generic number" note on
  `ironhide-roofing`.
- Placeholder pricing, menus, and timelines must stay labelled inline as placeholders.

## Before pushing

Check every page you touched at **1280px and 375px**:

- No horizontal overflow at either width
- No tap target under 44px on mobile
- The page's webfont pair actually loads (display ≠ body)
- `prefers-reduced-motion` respected — only `transform` and `opacity` animate
- Visible `:focus-visible` on every interactive element

## Known loose ends

- `sitemap.xml` lists the five original concepts but **not** `cutline-lawn-turf/`. Add it
  if that page is meant to be indexed.
- `send/` and `posts/` are intentionally out of the sitemap and blocked in `robots.txt`.
  Keep them that way.
