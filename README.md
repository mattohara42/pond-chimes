# Pond Chimes

An ambient, self-playing pond that sings when you tap the fish. A screensaver with a voice.

Single HTML file, no build step — Tone.js + Canvas. Open `index.html` in a browser (or serve the folder statically) and tap the pond to wake it.

## How it plays

Everything is locked to D major pentatonic, so any combination of taps sounds intentional.

- **Fish** — drift on lazy paths; tap one and it darts, a ripple expands, and a kalimba-style pluck plays. Pitch comes from the fish's Y position at tap time (higher on screen = higher note).
- **Lily flowers** — tap to open or close. Each toggle plays a soft chord swell, and every open flower holds its chord tone in a low drone under the pond.
- **Bare water** — still ripples, with a very quiet note so every touch answers.
- **Idle mode** — left alone, fish surface now and then and sing softly. The pond self-plays as gentle ambient background.

Audio starts on the first tap (browser autoplay rules); until then the pond is silent but alive.

## Status

**M1** — fish + lily pads (melody + harmonic bed), per the approved mockup and concept doc.

Planned next:
- **M2:** frogs (bass bloops) + dragonflies (high shimmer)
- **M3:** hummingbirds + idle-behavior polish

Deferred: day/night cycle, seasons, feeding mechanic, creature unlocks, settings UI.

## Notes

- `vendor/Tone.js` is the Tone.js v15.1.22 UMD build, vendored so the toy works with no CDN dependency (kiosk-friendly).
- Sibling projects: The Grid Sings, Chord Garden.
