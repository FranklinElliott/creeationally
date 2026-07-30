# A–Z Games Marathon Overlay

Public Twitch/OBS overlay for alphabetical game marathons. Each game has its own themed look (Black Ops green, Apex red, Valorant crimson, Minecraft pixels, etc.).

## Live site (GitHub Pages)

After Pages is enabled:

- **Control panel (streamers use this):** https://franklinelliott.github.io/creeationally/
- **OBS overlay for letter B:** https://franklinelliott.github.io/creeationally/?letter=B&mode=overlay

## Enable GitHub Pages

1. Repo **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)`
4. Save and wait ~1 minute

## OBS setup

1. Add a **Browser Source**
2. URL example: `https://franklinelliott.github.io/creeationally/?letter=B&mode=overlay`
3. Width ~900 · Height ~280
4. Enable transparent background
5. To advance: change `letter=B` → `letter=C` (or use the control page and copy a new URL)

## Control without GitHub login

Streamers only need the control page link. They pick a letter and copy the OBS URL — no repo access required.

## Share with other streamers

Send them:

1. Control: `https://franklinelliott.github.io/creeationally/`
2. Or a direct overlay URL with their starting letter

## Files

- `index.html` — control panel + themed overlay (static, no build)
- `.nojekyll` — disables Jekyll on Pages
