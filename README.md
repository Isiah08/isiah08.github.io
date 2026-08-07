# Portfolio — five concepts

Spec work for **fictional** businesses, built to show range across price point and visual
register. Nothing here pitches a real company, so there is no permission or
misrepresentation problem in posting any of it.

Every page carries a banner saying it is a concept. Placeholder pricing, menus and
timelines are labelled inline.

## Run it

```bash
python3 -m http.server 8950 --directory portfolio
```

`portfolio/index.html` is the piece you actually send a prospect. The five case pages hang
off it.

## The five

| Folder | Trade | Signature idea | Palette / type |
|---|---|---|---|
| `hill-country-exterior` | Pressure washing | Headline sits inside a "cleaned stripe" cut through grimy concrete. Publishes per-sq-ft rates instead of "call for quote" | Slate + safety orange, light page · Archivo Black + Public Sans |
| `lumen-aesthetics` | Med spa | Treatments set as a printed book index — leader dots, ranged-right prices. No cards anywhere | Sage + porcelain · Fraunces + Karla |
| `ironhide-roofing` | Storm restoration | The insurance claim clock as the spine of the page: date of loss → evidence → file → policy deadline | Bitumen + hazard yellow · Saira Condensed + IBM Plex Sans |
| `hearth-and-hollow` | Steakhouse | The menu *is* the hero, typeset as a letterpress card. Food photo demoted below the fold | Charred oak + ember · Bodoni Moda + Jost |
| `vance-and-rowe` | Injury law | A first-48-hours timeline — the part a frightened client needs — instead of a giant settlement figure | Parchment + oxblood · Newsreader + Source Sans 3 |

Each has its own palette, its own type pairing, and its own structural device. No shared
stylesheet, no shared section order — that is the whole point of the set.

## Why no case results on the law page

Attorney advertising is regulated by state bar rules, and invented settlement figures on a
spec build would be dishonest even labelled as a concept. So the firm page carries a
"nothing here is legal advice / no attorney–client relationship" disclosure and the
signature element is a timeline instead. Same reasoning drives the disclosures on the med
spa (scope-of-practice, price advertising) and the roofing page (filing deadlines are set
by the individual policy, not by a generic number).

Worth knowing before you sell into those verticals — it is also a good thing to raise on a
call, because most designers pitching them have not thought about it.

## Verified

All six pages, at 1280px and 375px:

- No horizontal overflow at either width
- No tap target under 44px on mobile
- Real webfont pairs load (display ≠ body on every page)
- `prefers-reduced-motion` respected; only `transform` and `opacity` animate
- Visible `:focus-visible` on every interactive element

Seen with my own eyes: the index, Hill Country, Hearth & Hollow, Ironhide. Lumen and
Vance & Rowe passed the same automated audit but were not screenshotted — worth a look
before you publish them.

## Reusing these for a real client

1. Copy the folder, rename it.
2. Delete the `.flag` banner and the concept line in the footer.
3. Replace the AI photography — it is the fastest tell.
4. Real pricing, or cut the pricing section.
5. Deploy to Netlify Drop or Vercel.
