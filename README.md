# m0ss.io

The personal site of Eva Moss, independent researcher, systems architect and entrepreneur:
mathematics, theoretical physics, software development and AI.

Live at **[m0ss.io](https://m0ss.io)**.

## What is here

| File | Purpose |
|---|---|
| `index.html` | The whole site: markup, styles and script in one file, no build step, no dependencies |
| `favicon.svg`, `favicon.ico`, `apple-touch-icon.png` | Icons, the dodecahedron projected from the same vertex coordinates |
| `og.jpg` | 1200×630 preview card for link sharing |
| `robots.txt`, `sitemap.xml` | Crawling rules and the single-page sitemap |
| `CNAME` | Ties the site to the `m0ss.io` domain. Do not delete it |

There are no web fonts, analytics, form services or other third-party requests.

## Design

The site is a mobile-first research page: the author's Greek signature and dodecahedron, a
short About, three Selected work entries, correspondence, then the complete
publication archive. The section navigation uses ordinary anchors. The archive uses native
`<details>` elements grouped by year. Every publication remains in the HTML and can be opened
without JavaScript; supporting browsers animate the disclosure with CSS.

## The dodecahedron

The regular dodecahedron is computed from exact vertex coordinates. A static first frame is
inline in the HTML, so the symbol is visible without JavaScript and does not wait for scene
construction. The script only updates 12 face polygons and one path containing all 30 edges.

- **Motion.** A calm quaternion-based turn, with inertial dragging and arrow-key control.
- **Frame rate.** 30 fps at rest, up to 60 fps during interaction when rendering is cheap;
  measured frame cost can reduce this to 30 or 20 fps.
- **Lifecycle.** Rendering stops when the symbol leaves the viewport, the tab is hidden, or
  reduced motion is requested and the body has settled. Changing the system preference works
  without reloading.
- **Reduced motion.** With `prefers-reduced-motion` the solid stays still until touched.

If the vertex or face data changes, regenerate the inline SVG first frame as well as the
JavaScript arrays.

### Tuning

The settings are constants near the top of the script in `index.html`:

| Constant | What it sets |
|---|---|
| `PERIOD` | Length of one calm turn, in ms |
| `K_YAW`, `K_PITCH` | Rotation per dragged pixel |
| `HAND_CAP` | Maximum hand-driven angular speed |
| `KEY_PUSH` | Angular speed added by an arrow key |
| `CAM`, `FOC` | Camera distance and focal scale |
| `TILT`, `ROLL` | Resting orientation |

## Updating the list of works

The archive sits in the two year-grouped `<details>` elements, each containing an
`<ol class="works">`. Every link is a Zenodo **concept DOI**, which always resolves to the
latest version of a record, so a new version on Zenodo needs no change here. Update the year
counts when adding a record. When the Theory of Temporal Spheres is finished, change its
`in progress` label in the archive.

## Contact

The form composes a message locally through the visitor's mail client; nothing is sent to a
form backend. Without JavaScript, the native `mailto:` form and the direct email link remain.

[eva@m0ss.io](mailto:eva@m0ss.io) · ORCID [0009-0002-9793-9139](https://orcid.org/0009-0002-9793-9139)
