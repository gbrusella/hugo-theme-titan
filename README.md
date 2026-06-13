# TITAN — Hugo theme

A dark, gold-on-black theme with an animated procedural tessellation background
and a persisted site-wide on/off toggle.

## Install

Add as a git submodule (recommended):

```bash
git submodule add https://github.com/gbrusella/hugo-theme-titan themes/titan
```

Or clone manually into your site's `themes/` directory, then set
`theme = "titan"` in your `hugo.toml`.

## Configure

```toml
[params.titan]
shape  = "overlay"   # voronoi | triangles | overlay | hexagons | squares | rhombille | hcp | fcc | bcc | cubic
motion = "sheet"     # bulge | sheet   (2D shapes only; 3D lattices always spin)
relax  = 2           # Lloyd relaxation passes — 0 = raw Poisson, 2-3 = even "blue-noise"
cell   = 66          # plate / lattice spacing in px (smaller = more, finer cells)

[params.hero]
kicker  = "Augmentation Online"
title   = "TITAN"
tagline = "Adaptive nanoceramic shield — reactive plating engaged"
```

These map to `data-*` attributes on the `<canvas id="titan">` and are read by
`assets/js/titan-bg.js`.

## Background toggle

Any element with `data-titan-toggle` becomes an on/off switch (the header
includes one styled as a pill). State is saved in `localStorage` and the
default respects `prefers-reduced-motion`.

## Editing the engine

`assets/js/titan-bg.js` and `assets/css/titan.css` are generated from the
[source playground](https://github.com/gbrusella/titan-bg). Do not edit them
directly — edit the playground and re-run `node scripts/extract-engine.js`.
