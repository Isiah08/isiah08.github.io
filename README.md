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

| Folder | Trade | Skeleton (each one is different on purpose) | Type (Fontshare) |
|---|---|---|---|
| `hill-country-exterior` | Pressure washing | Split-screen hero with the quote form IN it, full-height photo proof, sticky mobile call bar | Clash Display + Archivo |
| `lumen-aesthetics` | Med spa | Arch-cropped hero, marquee ticker, treatments on a horizontal scroll-snap shelf | Gambetta + Switzer |
| `ironhide-roofing` | Storm restoration | Proof strip above the fold, claim clock as a draggable filmstrip, sticky emergency bar | Tanker + Ranade |
| `hearth-and-hollow` | Steakhouse | Full-viewport photographic opening, then one centered editorial column — no sticky header, no cards | Zodiak + General Sans |
| `vance-and-rowe` | Injury law | Fixed left sidebar rail beside a scrolling column — no hero image anywhere | Sentient + Supreme |

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

After the second-generation rebuild, screenshotted: index, Hill Country, Lumen, Vance & Rowe.
Hearth & Hollow and Ironhide passed the same automated audit (no overflow, no sub-44px
targets, fonts confirmed loading) but the new versions were not eyeballed — glance at them
before publishing.

## Reusing these for a real client

1. Copy the folder, rename it.
2. Delete the `.flag` banner and the concept line in the footer.
3. Replace the AI photography — it is the fastest tell.
4. Real pricing, or cut the pricing section.
5. Deploy to Netlify Drop or Vercel.
