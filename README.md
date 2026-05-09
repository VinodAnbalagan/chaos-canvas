# 🎨 chaos-canvas

> _Learning math through generative art — one iteration at a time._

A personal lab for exploring **mathematical art** with [marimo](https://marimo.io) reactive notebooks.
Inspired by the work of [Simone Conradi](https://profconradi.com/) and the educational style of [3Blue1Brown](https://www.3blue1brown.com/), this project pairs **interactive visualizations** with **math explanations** so each piece of art is a lesson — and a stepping stone toward the math that underlies modern AI.

## 🌌 What's inside

- **Random walks & probability** — the math behind diffusion and stochastic processes
- **Strange attractors** — discrete dynamical systems, the same family that powers RNNs and SSMs
- **Fractals** — Mandelbrot, Julia sets, Koch, dragon curve
- **Iterated Function Systems (IFS)** — Sierpinski, Barnsley fern, fractal flames
- **Symmetry & kaleidoscopes** — dihedral groups in action (an on-ramp to equivariant networks)
- **Animations** — interpolating fractals through parameter space
- **Live dashboard** — combine everything into a shareable web app

Each tutorial is a self-contained marimo notebook that **explains the math, lets you play with sliders, and renders the art live**.

## 🚀 Quick start

### Prerequisites

- [uv](https://docs.astral.sh/uv/) — fast Python package manager
- Python 3.12+ (uv will install it for you)

### Install

```bash
git clone https://github.com/VinodAnbalagan/chaos-canvas.git
cd chaos-canvas
uv sync --extra dev
```

That's it. uv reads `pyproject.toml`, sets up an isolated `.venv/`, and installs everything reproducibly.

### Run a notebook

```bash
uv run marimo edit notebooks/01_lissajous.py
```

Your browser will open at `http://localhost:2718` with an interactive notebook.

### Run as a read-only web app

```bash
uv run marimo run notebooks/01_lissajous.py
```

## 🌐 Share notebooks on the web (no install required)

The killer feature of marimo — export any notebook to a static WASM bundle that runs entirely in the browser:

```bash
uv run marimo export html-wasm notebooks/06_ifs_basics.py -o gallery_web/ifs/
```

Push `gallery_web/` to GitHub Pages and anyone with a browser can run the interactive notebook — no Python, no install. This is what turns the repo from "code I wrote" into "interactive demos people can actually open."

## 📚 Tutorial path

Tutorials build on each other. The order is chosen so each piece teaches a math concept that **transfers directly to AI/ML research** — random processes for diffusion, dynamical systems for sequence models, group symmetries for equivariant networks.

| #   | Notebook               | Math concept                             | Connects to (in AI/ML)                           |
| --- | ---------------------- | ---------------------------------------- | ------------------------------------------------ |
| 01  | `01_lissajous.py`      | Parametric curves, sin/cos               | Marimo warm-up                                   |
| 02  | `02_random_walks.py`   | Probability, CLT, heavy tails            | Diffusion models, gradient noise, RL exploration |
| 03  | `03_attractors.py`     | Discrete dynamical systems, chaos        | RNN / Mamba hidden-state dynamics                |
| 04  | `04_mandelbrot.py`     | Complex iteration, escape dynamics       | Iterative refinement intuition                   |
| 05  | `05_julia_sets.py`     | Parameter-space view of iteration        | Phase / parameter space thinking                 |
| 06  | `06_ifs_basics.py`     | Contraction mappings, chaos game         | Probabilistic state machines                     |
| 07  | `07_kaleidoscope.py`   | Dihedral symmetry groups (D_n)           | Equivariant networks (E(2), `escnn`)             |
| 08  | `08_ifs_animations.py` | Interpolation in transform space         | Latent-space interpolation                       |
| 09  | `09_fractal_flames.py` | Non-linear variations, density rendering | Tone mapping, gamma, perceptual scaling          |
| 10  | `10_dashboard.py`      | Layout, web app deployment               | Shipping ML demos                                |

---

## 🧱 Project structurechaos-canvas/
```
├── src/chaos_canvas/ # Reusable library (chaos game, transforms, render, kaleidoscope)
├── notebooks/ # marimo tutorials (start here!)
├── gallery/ # Saved renders (PNGs, MP4s)
├── gallery_web/ # WASM exports for GitHub Pages
├── docs/ # Math notes & references
└── tests/ # Library tests
```
---

## 🧠 Math philosophy

Every tutorial answers three questions:

1. **What's the rule?** (the equation)
2. **Why does it produce _this_ shape?** (the intuition)
3. **What can we change, and what happens?** (interactive sliders)

If a tutorial only does #1, it's not done.

## 🛠️ Development

```bash
uv run pytest                    # run tests
uv run ruff format .             # format
uv run ruff check .              # lint
uv run mypy src/                 # type-check
```

---

## 🎁 Inspiration & credits

- **[Simone Conradi](https://profconradi.com/)** ([@S_Conradi](https://x.com/S_Conradi)) — _"I draw using mathematics and Python."_ The artistic inspiration.
- **[3Blue1Brown](https://www.3blue1brown.com/)** — the gold standard for mathematical exposition.
- **[marimo](https://marimo.io)** — the reactive notebook that makes interactive math possible.
- **Michael Barnsley**, _Fractals Everywhere_ — the foundational IFS reference.
- **Scott Draves**, _The Fractal Flame Algorithm_ — the technique behind density rendering.

## 📖 References

See [`docs/references.md`](docs/references.md) for papers, books, and links.

## 📄 License

MIT — see [`LICENSE`](LICENSE).

---
