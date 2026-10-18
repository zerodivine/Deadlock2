# Deadlock II Launcher

Plays your own copy of *Deadlock II: Shrine Wars* (1998) in a web browser, on an iPad or anywhere else, using the Boxedwine Windows emulator.

This site contains no game files. You load your own `Deadlock2-iPad.zip` package from your device.

## What's here
- `index.html`: the launcher page
- `boxedwine.js`, `boxedwine.wasm`: Boxedwine 26R1 multi-core web build (GPL-2.0, https://github.com/danoon2/Boxedwine)
- `st/`: Boxedwine 26R1 single-core web build, used when the browser can't run the multi-core one
- `coi-serviceworker.min.js`: turns on cross-origin isolation so the multi-core build can run on GitHub Pages (MIT, https://github.com/gzuidhof/coi-serviceworker)
- `jszip.min.js`: save backups (MIT/GPLv3, https://stuk.github.io/jszip/)
- `fonts/`: Chakra Petch, Barlow, Share Tech Mono (SIL Open Font License)

The page also embeds a patched copy of Wine 6's `ddraw.dll.so` (LGPL-2.1, https://www.winehq.org). One check in `ddraw_surface_update_frontbuffer` is changed so that locking the primary surface reads the game window first. Without it, Deadlock II's menus go black when the cursor moves.
