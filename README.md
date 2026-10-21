# m0ss.io

The personal site of Eva Moss, independent researcher: the Theory of Temporal Spheres and
dodecahedral structure across cosmology, physics, number theory and biology.

Live at **[m0ss.io](https://m0ss.io)**.

## What is here

| File | Purpose |
|---|---|
| `index.html` | The whole site: markup, styles and script in one file, no build step, no dependencies |
| `sky.webp`, `sky.jpg` | Background, the galactic centre in near-infrared (NASA/JPL-Caltech/ESA/CXC/STScI, PIA12348); WebP first, JPEG as a fallback |
| `CNAME` | Ties the site to the `m0ss.io` domain. Do not delete it |

## The dodecahedron

Nothing in the hero is drawn by hand. The regular dodecahedron is computed from its exact
vertex coordinates and rendered in SVG every frame.

- **Look.** Translucent gold faces with a narrow gold rim along every edge, lit by two
  lights that sit out of frame; sun glints slide across a face whenever it turns to catch one.
- **Motion.** A rigid body integrated from Euler's equations. Its mass is spread unevenly
  (a weight below the centre and three unequal moments of inertia), so when it is spun about
  its middle axis it flips over and over on its own, the tennis-racket effect. Each spin-up
  starts from a small random nudge, so no two are alike.
- **Spin cycle.** Calm turning, a slow spin-up, a stretch at full speed where the solid smears
  into a breathing globe with racing glints, then braking, and again. Motion blur is drawn with
  trailing copies of the solid.
- **Touch.** Dragging it works through friction, with slip: it is heavy, takes a while to
  follow the hand, and coasts after release. Arrow keys push it.
- **Sound.** Off until the visitor turns it on (bottom right of the hero). A muffled
  20–30 Hz drone climbs with the spin; at full speed a low rumble joins, the whole sound
  breathes on a 5 s cycle, and the globe shudders in time with the sound's flutter at the
  turn rate. Everything is synthesized in the browser with the Web Audio API.
- **Reduced motion.** With `prefers-reduced-motion` the solid stays still until touched.

### Tuning

The main settings are constants near the top of the script in `index.html`:

| Constant | What it sets |
|---|---|
| `CALM`, `RISE`, `HOLD`, `FALL` | Length of each phase of the spin cycle, in ms |
| `INERTIA` | Moments of inertia; the more unequal, the sooner and more often it flips |
| `SWAY` | Strength of the weight that rights it once it slows |
| `DRAG` | Air drag on its turning |
| `KICK` | Size of the random nudge at each spin-up |
| `GRIP` | How hard it is to drag by hand |
| `RIM`, `WALL` | Width of the gold rim and density of the faces |
| `BREATH`, `TREMOR_SIZE` | The globe's breathing period and shudder |
| `SOUND_LEVEL` | Overall volume |

## Updating the list of works

The list sits in `<ol class="works">` in `index.html`. Every link is a Zenodo **concept
DOI**, which always resolves to the latest version of a record, so a new version on Zenodo
needs no change here. When the Theory of Temporal Spheres is finished, change its
`in progress` label.

## Contact

[eva@m0ss.io](mailto:eva@m0ss.io) · ORCID [0009-0002-9793-9139](https://orcid.org/0009-0002-9793-9139)
