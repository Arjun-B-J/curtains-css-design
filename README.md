# curtains-css-design

An interactive WebGL "curtain" effect demo. A grid of vertical strands hangs under simulated gravity and reacts to mouse/touch movement, rendered as a textured curtain over a centered name/title block ("ARJUN B J / NITC / CSE").

Originally a CodePen pen ([source](https://codepen.io/arjun_b_j/pen/LYVyZKK)) extracted into a standalone static page.

## Tech stack

- Plain HTML / CSS / JavaScript (no build step)
- [Three.js](https://threejs.org/) (r110) for WebGL rendering with a custom GLSL shader
- [Verlet.js](https://github.com/subprotocol/verlet-js) for the cloth-like physics simulation
- [chroma.js](https://gka.github.io/chroma.js/) for the color gradient across strands
- Polyline geometry adapted from [oframe/ogl](https://github.com/oframe/ogl)

All libraries are loaded from CDNs at runtime; nothing needs installing.

## Run it

Just open `index.html` in a browser. A curtain texture is fetched from a remote URL, so an internet connection is required.

For a local server (recommended to avoid any CORS quirks):

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Files

- `index.html` — markup, CDN script tags, the centered text overlay
- `style.css` — page background and typography for the overlay
- `script.js` — the full demo: Three.js scene, custom shader, Verlet physics, mouse interaction, `Polyline` helper class
