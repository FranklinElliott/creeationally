# A–Z Games Marathon Overlay

Public **Twitch / OBS** browser-source overlay for alphabetical game marathons (A→Z).  
Each letter has a themed card (colors, cover art, accents). Streamers control it from a simple web panel — **no GitHub login** required for day-to-day use.

## Live links

| What | URL |
|------|-----|
| **Streamer control panel** | [https://franklinelliott.github.io/creeationally/](https://franklinelliott.github.io/creeationally/) |
| **Example OBS overlay (letter B)** | [https://franklinelliott.github.io/creeationally/?letter=B&mode=overlay](https://franklinelliott.github.io/creeationally/?letter=B&mode=overlay) |

If the preview looks frozen on some PCs (OS “reduce motion”), hard-refresh or open with `?v=motion` once, then use the normal control page.

## Features

- **A–Z letters** with per-game themes and cover art (`covers/`)
- **Multi-option letters** (e.g. **E** = Expedition 33 or EA Sports FC) — pick in the control panel
- **Optional custom challenge** line under the title (e.g. “Hit a trickshot”)
- **Two timers** (both stored in the OBS URL so each streamer is independent):
  - **Current game** — time on this letter (auto-restarts when you change letter)
  - **Total** — whole marathon run
- Set time already in (days / hours / mins / secs) if the run started earlier
- **5+ hours on current game** → ➜ + 😭 flag on the overlay
- Themed motion FX (canvas + DOM); fixed overlay size for OBS
- Pure static site — no build step, works on GitHub Pages

## OBS setup

1. Open the [control panel](https://franklinelliott.github.io/creeationally/)
2. Pick letter / game, start timers, optional challenge
3. Click **Copy full OBS URL**
4. In OBS → **Browser Source** → paste that full URL
5. Size (exact — overlay is fixed):
   - **Width: 860**
   - **Height: 188**
6. Enable **transparent background**
7. Turn **OFF** “Shutdown source when not visible” (helps keep animation/timer smooth)

When you change letter, challenge, or timers on the control page → **Copy full OBS URL** again → paste into OBS → Refresh the Browser Source.

### URL parameters (advanced)

| Param | Purpose |
|-------|---------|
| `letter` | `A`–`Z` |
| `game` | Game id (e.g. `bo2`, `overwatch2`) |
| `pick` | Option index when a letter has multiple games |
| `mode` | `overlay` for OBS; omit/control for the panel |
| `runStart` | Unix seconds — whole-run clock start |
| `gameStart` | Unix seconds — current-game clock start |
| `challenge` | Optional challenge text (URL-encoded) |
| `motion=0` | Disable motion FX |

Example:

```text
https://franklinelliott.github.io/creeationally/?letter=B&game=bo2&mode=overlay&runStart=...&gameStart=...&challenge=Hit+a+trickshot
```

## Control panel tips

- **Current game** timer resets when you switch letters (total keeps going)
- **Set game time in** / **Set total time in** if already mid-run
- Challenge is optional — blank = no challenge line
- Each streamer’s timers live only in **their** OBS URL — others don’t affect them
- **Motion check**: if the live preview is moving, copy the OBS URL from that page

## Share with other streamers

Send them the control link:

**https://franklinelliott.github.io/creeationally/**

They pick their letter, set timers, and copy their own OBS URL. No repo access needed.

## Enable GitHub Pages (repo owners)

1. Repo **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)`
4. Save and wait ~1 minute

## Files

| Path | Role |
|------|------|
| `index.html` | Control panel + themed overlay (single file app) |
| `covers/` | Local cover art for each game |
| `.nojekyll` | Disables Jekyll on GitHub Pages |
| `README.md` | This file |

## Privacy / safety notes

- No accounts, no backend — everything is client-side + URL params
- Don’t commit secrets (API tokens, etc.) into this repo
- If a personal access token was ever pasted into chat, **revoke it** in GitHub settings

## License

Use freely for streams and marathons. Credit appreciated but not required.
