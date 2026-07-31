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
- **Lily pads** are grouped together in the right third of the pond — the still water, away from the waterfall and rocks. (Tap a flower to open/close it.)
- **Rocks** — big, smooth boulders with a scatter of pebbles form a heavy rocky border down the whole left edge, like the real pond's bank. They cast shade on the water, and on a hot day (from the live temperature) the fish drift over to loiter in the cool. Rocks are permanent — they poke up through the winter ice.
- **Water plants** — tall, wide-leaf clumps (think pickerelweed / canna) rise up among the rocks to break up the frame with some height. They sway with the wind, take on the season's colour, and die back with the lily pads in deep winter.
- **Water flow** — a gentle current runs the way the real pond does: a waterfall spills in at the top-left (with a little foam where it lands) and the surface drifts down toward the pump intake at the bottom-right. The caustic light and any drifting petals or leaves ride the current. Kept subtle, so the pond still feels calm.
- **Bare water** — still ripples, with a very quiet note so every touch answers.
- **Idle mode** — left alone, fish surface and sing, frogs croak and occasionally wander to a new pad, dragonflies dip, and the hummingbird drops by. The pond self-plays as gentle ambient background.
- **Day/night** — the water colour follows the real local clock. It keeps its moonlit identity: deep teal-black at night with faint star reflections, brightening only to a soft overcast teal by day, with a warm low-sun rake across the surface at dawn and dusk. No network needed — it reads the device clock, so it works offline.
- **Weather** — if a location is available, the pond quietly pulls current conditions and lets the real sky bleed in: cloud cover greys the water and hides the sun and stars, rain stipples the surface with dimples, wind roughens it and stirs the fish, and snow drifts down. It's a soft overlay on the day/night sky, not a mode switch. Silent by design — weather only touches the visuals.
- **Seasons** — the pond also drifts through the year on the real calendar date. A gentle tint warms or cools the water, the lily pads take on the season's colour (fresh green in spring, lush in summer, olive-brown in autumn, dull in winter), blossom petals fall in spring and leaves in autumn, and the cold quiets the dragonflies and frogs. In spring a little school of **baby fish** appears among the adults (tap near them and they scatter). As winter closes in the pond winds down for the season: the lily pads die back, the frogs settle in to hibernate, and the dragonflies vanish — until only the fish are left, drifting slow and dim beneath a translucent **sheet of ice** that freezes over the surface. Everything eases back to life as it warms. Hemisphere-aware and always gradual, so the pond's identity holds year-round.

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

**M6** — seasons on the real calendar date (hemisphere-aware): seasonal water tint, lily-pad colour, drifting spring petals / autumn leaves, cold-quieted dragonflies and frogs, a spring school of baby fish, and a winter ice sheet with the fish drifting slow beneath it. Completes the "pond mirrors the world outside" trio with day/night and weather.

**M7** — pond layout & flow: lily pads grouped in the right third; a heavy border of big smooth boulders + pebbles down the left edge casting shade (fish loiter there on a hot day, driven by live temperature); tall wide-leaf water plants rising among the rocks; and a gentle top-left-waterfall → bottom-right-pump current that the caustics and drifting foliage ride. Adds real pond-edge character.

Deferred: feeding mechanic, creature unlocks, settings UI, optional weather/season sound.

## Notes

- `vendor/Tone.js` is the Tone.js v15.1.22 UMD build, vendored so the toy works with no CDN dependency (kiosk-friendly).
- Sibling projects: The Grid Sings, Chord Garden.
