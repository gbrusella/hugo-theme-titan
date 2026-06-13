---
title: "Hello, Titan"
date: 2026-06-13
---

Welcome to the first post on the TITAN theme. The animated background keeps
running behind this panel, while the frosted-glass surface keeps the text
crisp and legible.

## Switching tessellation models

Change `shape` in `hugo.toml`:

```toml
[params.titan]
shape = "rhombille"
motion = "sheet"
```

Try `hcp`, `fcc`, `bcc`, or `cubic` for the rotating 3D crystal lattices —
those have their own spin animation and ignore `motion`.

> The whole engine is a single dependency-free script shared with the Jekyll
> build, generated from the original `index.html` playground.
