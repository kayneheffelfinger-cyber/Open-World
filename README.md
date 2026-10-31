# Open World

A single-player, in-browser tycoon game set on the real Earth. Current version: **v2.25** ("The Long Walk").

Search for any real city and the game builds it from OpenStreetMap data: real streets, buildings, greens and plots, all standing on dry land. Then build your business empire there. Every city is reachable on foot.

## Play

- Dev build (GitHub Pages): https://gamble-limited-ltd.github.io/GLL-Open-World/ — always the newest features
- Hosted version: https://open-world.taps-holdings.org/ — serves `main`, which currently runs an older build than the dev branch
- The project moved to the Gamble-Limited-Ltd org: old bookmarks to `kayneheffelfinger-cyber.github.io/Open-World` no longer resolve
- Locally: serve the repo folder with any static web server and open `index.html`, then press PLAY NOW. It needs an internet connection.

Since v2.24 the game checks `version.json` on every boot: if the site is running a newer build than your browser is, it shows a one-tap **UPDATE NOW** banner that reloads through a cache-busting link — no more silently playing a stale copy while fixes ship around you.

## How the game works

The loop, as described by the in-game starter guide:

1. Buy a green **$** plot.
2. Park a food cart on it.
3. Serve the queue yourself, or hire star vendors.
4. Lease offices in the towers.
5. Trade on the exchange (limit and market orders).
6. Grow your net worth.

## Controls

| Action | How |
|---|---|
| Move your tycoon | Tap or click anywhere (the only way the tycoon walks) |
| Look around | Drag, or WASD / arrow keys / on-screen joystick |
| Rotate / tilt | Right-drag (or middle-drag / Ctrl+drag) |
| Zoom | Mouse wheel or pinch |
| Snap back to your tycoon | `C` or the crosshair button |
| Serve customers | `E` while standing at your cart |
| World map | `M` or click the minimap |
| Walk to the nearest city | The gold pill above the bottom bar (routes around water, uses bridges) — the distance shown is always your tycoon's, and it flags when the view is panned far away from them |
| Help and starter guide | In-game Help — the starter guide can be replayed anytime |

## Under the hood

- Static HTML and JavaScript. The whole game is `openworld.html` (about 8,000 lines), with `index.html` as the landing page.
- 3D with three.js 0.160, loaded from unpkg.
- Live calls to OpenStreetMap Overpass (map data) and Nominatim (city search); if Overpass is unreachable, a built-in generator lays out the city instead. Map data is (c) OpenStreetMap contributors (ODbL).
- On boot the game reads same-origin `version.json` and offers the one-tap self-update described above.
- No accounts. Your world is saved in your browser's localStorage under the key `openworld-v2`, so it stays on that browser and device.

## Planned (not built yet)

- Teleport to plots you own.
- More sidewalk plots to buy.
- Sign in with a GLL account.
- Server-side saves.

## Contributing

Read `AGENTS.md` for the contributor rules. `CHANGES.md` is a short log of what changed and why.

## License

PolyForm Noncommercial 1.0.0. See the `LICENSE` file.
