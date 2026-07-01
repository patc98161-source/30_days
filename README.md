# 30 Days of Us

A daily mini-project, one for each day leading up to her birthday (Aug 2).

## Folder structure
- `index.html` — homepage grid, links to each unlocked day
- `day1.html` through `day30.html` — one file per day (days 4-30 are placeholders right now)
- `shared/tokens.css` — the shared color/type palette, for reference
- `PROJECT_CONTEXT.md` — design system + ship log, paste into Cursor/Copilot when building a new day

**Note:** this folder is named `30 days` (with a space). That's fine for a local folder, but when you create the GitHub repo, give the *repo* a space-free name like `30-days-of-us` — the folder contents just get pushed into it.

## How to publish this on GitHub Pages

**1. Create the repo**
- Go to github.com → New repository
- Name it `30-days-of-us` (public)
- Don't initialize with a README (you already have one)

**2. Push your local folder**
Open a terminal inside the `30 days` folder:
```bash
git init
git add .
git commit -m "Days 1-3: reasons, scratch card, countdown"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/30-days-of-us.git
git push -u origin main
```

**3. Turn on GitHub Pages**
- Repo → Settings → Pages
- Source: **Deploy from a branch** → Branch: `main`, folder: `/ (root)` → Save
- Wait ~1 minute, your live URL will be:
  `https://YOUR_USERNAME.github.io/30-days-of-us/`

## Daily workflow (repeat for days 4-30)

1. Open `dayX.html` (e.g. `day4.html`) — replace the placeholder content with that day's build. Keep the palette (cream `#FBF3EC` / plum `#3D1F2B` / rose `#C87A88` / gold `#D9A94E` / blush `#F3DCE1`) and the "Day X" seal badge so it stays visually consistent — see `PROJECT_CONTEXT.md`.
2. In `index.html`, find `const unlockedDays = [1, 2, 3];` and add the new day number, e.g. `[1, 2, 3, 4]`.
3. Commit and push:
```bash
git add .
git commit -m "Day 4: <what you built>"
git push
```
4. Site auto-updates within ~1 minute — no extra steps.

## Tip
Don't push all remaining days at once even if you build ahead — commit one day at a time so the site unfolds day by day when she checks it, and your commit history tells the story.
