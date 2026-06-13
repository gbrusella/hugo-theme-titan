# Contributing to TITAN (Hugo theme)

Thanks for your interest! Contributions of all kinds are welcome — bug reports,
layout improvements, documentation fixes, and new features.

---

## Project structure

```text
hugo-theme-titan/
├── assets/
│   ├── css/
│   │   ├── titan.css        # readable stylesheet  (generated — do not edit)
│   │   └── titan.min.css    # minified             (generated — do not edit)
│   └── js/
│       ├── titan-bg.js      # animation engine     (generated — do not edit)
│       └── titan-bg.min.js  # minified             (generated — do not edit)
├── exampleSite/             # demo site built by CI
├── images/                  # Hugo themes gallery screenshots
├── layouts/                 # Hugo templates
├── static/                  # static assets (favicon, etc.)
├── theme.toml
└── hugo.toml
```

---

## What lives where

### Templates and layouts

`layouts/` is the right place for Hugo-specific changes — partials, base layout,
shortcodes, etc. Edit freely and open a PR.

### The animation engine and stylesheet

`assets/js/titan-bg.js` and `assets/css/titan.css` are **generated from a separate
source repository** — the [titan-bg playground](https://github.com/gbrusella/titan-bg).
Do **not** edit them directly here; your changes will be overwritten the next time
the files are regenerated.

If you want to change the animation logic or the shared stylesheet, open an issue or
PR there instead. Once merged, the maintainer regenerates the files and updates this repo.

---

## Running the demo locally

```bash
# from the repo root
mkdir -p exampleSite/themes
ln -sf "$(pwd)" exampleSite/themes/titan   # symlink the theme in
hugo server -s exampleSite
```

Open <http://localhost:1313>.

---

## Submitting a pull request

1. Fork the repo and create a branch from `main`.
2. Make your changes. Keep commits focused — one logical change per commit.
3. If you changed any layout files, test the demo site locally (see above).
4. Open a PR with a clear description of what changed and why.

Please do not commit the generated `assets/js/titan-bg*.js` or
`assets/css/titan*.css` files unless you are the maintainer regenerating them
from the source playground.

---

## Reporting issues

Open a GitHub issue with:

- What you expected vs. what happened
- Hugo version (`hugo version`)
- Browser and OS (for visual bugs)
- A minimal reproduction if possible
