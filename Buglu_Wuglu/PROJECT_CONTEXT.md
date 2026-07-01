# 30 Days of Us — Project Context

Keep this open (or paste into Cursor/Copilot) every time you start a new day's build,
so every mini-project shares the same visual identity instead of looking like 30 random files.

## Design tokens (reuse everywhere)

**Palette**
- `--cream: #FBF3EC` — page background
- `--plum: #3D1F2B` — primary text / dark accents
- `--rose: #C87A88` — primary accent (buttons, links, highlights)
- `--gold: #D9A94E` — secondary accent (used sparingly — seals, dividers)
- `--blush: #F3DCE1` — soft fill / card backgrounds

**Type**
- Display / headings: `Fraunces` (serif, warm, a little irregular — feels handwritten-adjacent)
- Body: `Inter` or `Work Sans` (clean, doesn't compete)
- Accent / signature moments only: `Caveat` (handwriting font — use for ONE element per page max, e.g. a signature or a single line, never body text)

Google Fonts import:
```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,600&family=Work+Sans:wght@400;500&family=Caveat:wght@600&display=swap" rel="stylesheet">
```

**Signature element:** a small circular "wax seal" badge in the corner of every page — `Day N` in Caveat script inside a gold-bordered circle. This is the thread that ties all 30 builds together visually. Reuse the exact same CSS for it every time (see `seal.css` snippet below).

```css
.seal {
  position: fixed; top: 24px; right: 24px;
  width: 64px; height: 64px; border-radius: 50%;
  background: var(--gold); color: var(--cream);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Caveat', cursive; font-size: 1.4rem;
  box-shadow: 0 4px 12px rgba(61,31,43,0.25);
  transform: rotate(-6deg);
}
```

**Motion rule:** one deliberate entrance animation per page (fade+rise on load), nothing else moving constantly. No confetti-cannon-on-every-click. Save bigger motion for the finale (Day 30).

## Tech stack per week
- Week 1 (Days 1-7): vanilla HTML/CSS/JS, single file each
- Week 2 (Days 8-14): vanilla JS, slightly more interactive (canvas/drag-drop/audio)
- Week 3 (Days 15-20): Anthropic API via fetch — see note below
- Week 4 (Days 21-25): MERN mini-apps, small Express + MongoDB backend
- Final stretch (Days 26-30): ties everything together, Day 30 = finale recap

## Anthropic API note (Week 3)
Don't expose your API key client-side in anything you'll actually send her / host publicly.
Route calls through a tiny Express backend (even a single `server.js` with one `/api/ask` route) that holds the key server-side. Keep it simple — one endpoint, one prompt template per idea.

## File structure (flat — matches what's actually on disk)
```
30 days/
  index.html          <- homepage grid, links to day1.html...day30.html
  PROJECT_CONTEXT.md  <- this file
  shared/
    tokens.css        <- palette + seal + base styles (optional reference/import)
  day1.html
  day2.html
  day3.html
  ...
  day30.html          <- days 4-30 are placeholders, ready for you to fill in
```

To unlock a day on the homepage: open `index.html`, find `const unlockedDays = [1, 2, 3];` and add the day number to that array.

## Ground rules (so this doesn't collapse by day 10)
1. Timebox each day to ~1-2 hrs. If it's not done, ship a simpler version — don't skip.
2. Reuse the palette/seal styling every time. Don't restyle from scratch.
3. Keep the ship log below updated (helps you write the Day 30 recap).

## Ship log
- [x] Day 1 — Reasons I Love You generator
- [x] Day 2 — Scratch card reveal (canvas)
- [x] Day 3 — Countdown timer to Aug 2
