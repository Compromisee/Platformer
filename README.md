# 🏔️ SUMMIT — Rise

A single-file browser platformer where you climb as high as you can. Built with vanilla HTML5 Canvas, zero dependencies.

---

## Play

Open `summit3.html` in any modern browser. No server, no install, no build step.

---

## How to Play

| Input | Action |
|---|---|
| `←` / `A` | Move left |
| `→` / `D` | Move right |
| `Space` / `↑` / `W` | Jump |
| Jump again (mid-air) | Double jump |
| Land on enemy from above | Stomp (bounce off, +5 score) |

**Goal:** Jump onto platforms and climb as high as possible. Your altitude score increases as you rise. Don't fall off the bottom of the screen — and watch out for enemies.

---

## Platform Types

| Platform | Colour | Behaviour |
|---|---|---|
| Normal | Green | Standard landing, resets double jump |
| Bounce | Orange | Launches you upward automatically — higher than a regular jump |
| Crumble | Red | Starts breaking the moment you land. Jump fast |

---

## Enemies

Spiky red blobs patrol back and forth on platforms. Two ways to deal with them:

- **Stomp** — fall onto one from above. You bounce off and score +5.
- **Avoid** — getting hit from the side costs 1 HP and gives you brief invincibility frames.

You start with **3 HP**. The bar at the bottom of the screen tracks your health. Reach zero and it's game over.

---

## Day / Night Cycle

In light mode the world runs through a full day cycle — dawn, midday, dusk, and night — with a sun that arcs across the sky and sets behind the mountain silhouettes. Stars appear at night, and a crescent moon rises.

In dark mode the world is locked to permanent night: deep navy sky, full star field, moon only. No sun, no dawn, no transitions.

---

## Theme Toggle

The vertical slider on the left side of the game switches between **Light** and **Dark** mode.

- ☀️ at the top = Light mode — full day/night cycle
- 🌙 at the bottom = Dark mode — permanent night

The entire UI responds: HUD pills, screen overlays, platform colours, and the sky all adapt.

---

## Scoring

- Altitude climbed is your primary score, calculated from how high your character has risen above the starting platform.
- Each enemy stomped adds **+5** to your score.
- Your best score is tracked for the session and shown in the top-right HUD.

---

## Technical Notes

- **Single file** — all HTML, CSS, and JS in one `summit3.html`. No frameworks, no bundler.
- **Single canvas** — sky background, celestial bodies, mountains, platforms, enemies, player, and particles all render to one `<canvas>` in the correct draw order.
- **Procedural generation** — platforms are randomly generated with randomised widths, positions, and types. The world extends infinitely upward as you climb.
- **Parallax mountains** — three silhouette layers built from sine-wave paths, drawn after the sun/moon so the sun visually sets behind the peaks.
- **Day/night palette** — interpolated across keyframe colour stops using lerped RGB values. Dark mode bypasses the cycle entirely and returns a static night palette.
- **Font** — JetBrains Mono (loaded from Google Fonts). Requires an internet connection for the typeface; gameplay works offline with a fallback monospace font.

---

## Browser Support

Works in any browser with Canvas 2D support — Chrome, Firefox, Safari, Edge. No WebGL required.
