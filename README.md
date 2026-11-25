# Daisycutter Goes to Siberia — Web Edition

An original NES stealth game by **IntELiSoft**, published by Claude, running in the browser.
Not officially licensed by Nintendo.

**Play:** https://spokswinski.github.io/Daisycutter_goes_to_siberia/

November 1986. A Soviet nuclear physicist wants out, and Daisycutter is going in to get him.
Each area hides one weapon inside a searchable object or on a guard, and that weapon is the
only thing that can kill the area's boss. Interrogate guards for intel, find the weapon,
take down the boss, and stop KGB agent Viktor Drozd.

---

## Install it on your screen

The game is a web app. It installs like a regular app, launches full screen straight into
the game, and works offline after the first visit.

| Device | Steps |
|---|---|
| **iPhone / iPad** | Open the link in **Safari** → tap **Share** → **Add to Home Screen** → **Add**. |
| **Android** | Open the link in **Chrome** → tap **⋮** → **Install app** (or **Add to Home screen**). |
| **Windows / Mac / Chromebook** | Open the link in **Chrome** or **Edge** → click the **install icon** at the right end of the address bar (or **⋮ → Cast, save and share → Install page as app**). |

Sound starts on your first tap or key press (browsers require this).

## Controls

| NES | Touch | Keyboard | Gamepad |
|---|---|---|---|
| D-pad (8-way) | Left pad (slide your thumb for diagonals) | Arrow keys or WASD | D-pad / left stick |
| **B** — fire | Left red button | **X** (or K) | Xbox A / PlayStation ✕ |
| **A** — search / talk | Right red button | **Z** (or J) | Xbox B / PlayStation ○ |
| Start — pause / map | Start | **Enter** | Menu / Options |
| Select — switch weapon | Select | **Shift** | View / Share |

In-game, **Start** drops the pause screen with your weapons, the area map and any intel
you've collected. Turkey legs refill health.

The top bar has mute 🔊 and full-screen ⛶ buttons. The game pauses itself when you switch
away; tap the screen or press a key to resume.

---

## Repository configuration (one-time, for the repo owner)

The site is plain static files, so GitHub Pages serves it directly with no build step.

1. On GitHub, open **spokswinski/Daisycutter_goes_to_siberia → Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Set **Branch** to **`main`** and the folder to **`/ (root)`**, then click **Save**.
4. Wait a minute or two. The page shows *"Your site is live at
   https://spokswinski.github.io/Daisycutter_goes_to_siberia/"*. Share that link.

Notes:
- The repository must be **public** for Pages on a free GitHub account (private-repo Pages
  needs GitHub Pro, Team or Enterprise).
- The path is **case-sensitive** and matches the repo name exactly:
  `/Daisycutter_goes_to_siberia/`.
- **Enforce HTTPS** (same Settings → Pages screen) should stay on; installing as an app
  requires HTTPS.
- Optional: in **Settings → General**, add the Pages URL as the repository **Website** so it
  shows on the repo's front page.

### Shipping an update

1. Replace `rom/daisycutter.nes` (and/or edit other files).
2. In `sw.js`, bump `VERSION` (e.g. `daisycutter-v1.3-web1`) so installed copies refresh
   their offline cache.
3. Commit and push to `main`. Pages redeploys automatically; installed apps pick up the
   new version the next time they're opened online.

### Run it locally

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```
(Opening `index.html` directly from disk won't work; browsers block loading the ROM from `file://`.)

## Files

| Path | What it is |
|---|---|
| `index.html` | The player: screen, touch controls, keyboard and gamepad input, audio |
| `rom/daisycutter.nes` | The game (v1.2, MMC1, 128 KB PRG + 128 KB CHR). Also runs on an NES Classic via hakchi2 CE or any NES emulator |
| `vendor/jsnes.min.js` | JSNES 3.0.0 emulator core (Apache-2.0) |
| `manifest.webmanifest`, `sw.js` | App install metadata and offline cache |
| `icons/` | Home-screen icons |
| `.nojekyll` | Tells Pages to serve the files as-is |

See [NOTICE.md](NOTICE.md) for credits and licenses.
