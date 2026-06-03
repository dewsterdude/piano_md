# 🎹 Piano MD

A fully interactive **88-key web piano** — installable as a Progressive Web App and playable offline. Built as a single static page with no build step.

**▶ Play it:** https://dewsterdude.github.io/piano-md/

## Features

- **Full 88-key keyboard** (A0–C8) with horizontal scroll and an octave shifter.
- **Two voices:**
  - **GRAND** — a real sampled grand piano (Salamander Grand Piano), played via [Tone.js](https://tonejs.github.io/). Default voice.
  - **SYNTH** — a built-in additive Web Audio piano synth (inharmonicity, hammer noise, convolution reverb), used instantly while the GRAND samples load.
- **Volume control** and touch + mouse input.
- **Progressive Web App** — installable to your home screen and works fully offline (app shell, Tone.js, and all samples are cached by a service worker).

## Running locally

It's just static files, so serve the folder over HTTP (a service worker won't run from `file://`):

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Project layout

```
index.html               The app (markup, styles, audio engine)
manifest.webmanifest      PWA manifest
sw.js                     Service worker (offline caching)
vendor/tone.js            Tone.js 14.8.49 (vendored)
samples/salamander/       30 Salamander piano samples (minor-third intervals, A0–C8)
icons/                    PWA / favicon / Apple touch icons (+ source SVG)
```

## Credits & license

The **GRAND** voice uses the **Salamander Grand Piano** by **Alexander Holm**, licensed under [Creative Commons Attribution 3.0 (CC-BY 3.0)](https://creativecommons.org/licenses/by/3.0/). The sample set used here is the reduced version distributed with the [Tone.js](https://github.com/Tonejs/Tone.js) project.

Audio synthesis and the rest of the app are powered by [Tone.js](https://tonejs.github.io/) (MIT).
