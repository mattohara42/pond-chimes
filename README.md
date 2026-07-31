# Pond Chimes

An ambient, self-playing pond that sings when you tap the fish. A screensaver with a voice.

Single HTML file, no build step — Tone.js + Canvas. Open `index.html` in a browser (or serve the folder statically) and tap the pond to wake it.

## How it plays

Everything is locked to D major pentatonic, so any combination of taps sounds intentional.

- **Fish** — drift on lazy paths; tap one and it darts, a ripple expands, and a kalimba-style pluck plays. Pitch comes from the fish's Y position at tap time (higher on screen = higher note).
- **Lily flowers** — tap to open or close. Each toggle plays a soft chord swell, and every open flower holds its chord tone in a low drone under the pond.
- **Frogs** — sit on lily pads; tap one and it hops to a free pad, landing with a splash and a low, round bass bloop (pitch from the landing pad's height). Left alone they croak softly now and then.
- **Dragonflies** — skim across the surface; tap one and it dashes away with a quick high shimmer arp. They occasionally dip to the water with a tiny ripple and a single sparkle note.
- **Hummingbird** — a rare visitor. Every minute or so it flies in from the edge to hover at a lily flower with a soft tremolo trill (the pond's highest register). Tap it and it startles away with a brighter trill.
- **Bare water** — still ripples, with a very quiet note so every touch answers.
- **Idle mode** — left alone, fish surface and sing, frogs croak and occasionally wander to a new pad, dragonflies dip, and the hummingbird drops by. The pond self-plays as gentle ambient background.
- **Day/night** — the water colour follows the real local clock. It keeps its moonlit identity: deep teal-black at night with faint star reflections, brightening only to a soft overcast teal by day, with a warm low-sun rake across the surface at dawn and dusk. No network needed — it reads the device clock, so it works offline.
- **Weather** — if a location is available, the pond quietly pulls current conditions and lets the real sky bleed in: cloud cover greys the water and hides the sun and stars, rain stipples the surface with dimples, wind roughens it and stirs the fish, and snow drifts down. It's a soft overlay on the day/night sky, not a mode switch. Silent by design — weather only touches the visuals.

Audio starts on the first tap (browser autoplay rules); until then the pond is silent but alive.

## Weather setup (optional)

Weather is off until it knows where the pond is. It looks, in order:

1. **URL** — `index.html?lat=42.36&lon=-71.06` (easiest for a kiosk / wall panel).
2. **Baked in** — set `FIXED_LOCATION = { lat: …, lon: … }` near the top of the weather block in `index.html`.
3. **Browser geolocation** — prompts once; needs `https` (or `localhost`).

If none resolve — or there's no network — the pond simply runs on the day/night cycle alone. Conditions come from [Open-Meteo](https://open-meteo.com/) (free, no API key), refreshed every 10 minutes.

## Status

**M3** — the full pond ensemble: fish (melody) + lily pads (harmony) + frogs (bass) + dragonflies (sparkle) + hummingbird (rare treat), with self-playing idle behavior for each, per the approved mockup and concept doc.

**M4** — a day/night cycle driven by the real local clock, in the moonlit palette range.

**M5** — live outdoor weather (cloud cover, rain, wind, snow) via Open-Meteo (no API key), overlaid on the day/night sky and degrading gracefully to time-of-day only when there's no location or network.

Deferred: seasons, feeding mechanic, creature unlocks, settings UI.

## Notes

- `vendor/Tone.js` is the Tone.js v15.1.22 UMD build, vendored so the toy works with no CDN dependency (kiosk-friendly).
- Sibling projects: The Grid Sings, Chord Garden.
