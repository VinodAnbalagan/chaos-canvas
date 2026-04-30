# 🎨 chaos-canvas

> *Learning math through generative art — one iteration at a time.*

A personal lab for exploring **mathematical art** with [marimo](https://marimo.io) reactive notebooks.
Inspired by the work of [Simone Conradi](https://twitter.com/profConradi) and the educational style of [3Blue1Brown](https://www.3blue1brown.com/), this project pairs **interactive visualizations** with **math explanations** so each piece of art is a lesson.

## 🌌 What's inside

- **Iterated Function Systems (IFS)** — Sierpinski, Barnsley fern, fractal flames
- **Strange attractors** — Clifford, de Jong, the orbit map
- **Fractals** — Mandelbrot, Julia sets, Koch, dragon curve
- **Symmetry & kaleidoscopes** — dihedral groups in action
- **Animations** — interpolating fractals through parameter space
- **3D explorations** — IFS in three dimensions

Each tutorial is a self-contained marimo notebook that **explains the math, lets you play with sliders, and renders the art live**.

## 🚀 Quick start

### Prerequisites

- [uv](https://docs.astral.sh/uv/) — extremely fast Python package manager (10–100× faster than pip)
- Python 3.12+ (uv will install it for you)

### Install

```bash
# Clone
git clone https://github.com/VinodAnbalagan/chaos-canvas.git
cd chaos-canvas

# Install everything (uv reads pyproject.toml + uv.lock automatically)
uv sync
```

That's it. uv created an isolated `.venv/`, installed Python 3.12 (if you didn't have it), and installed all dependencies — reproducibly.

### Run a notebook

```bash
uv run marimo edit notebooks/07_ifs_basics.py
```

Your browser will open at `http://localhost:2718` with an interactive notebook.

### Run as a read-only web app (share with friends!)

```bash
uv run marimo run notebooks/07_ifs_basics.py
```

## 📚 Tutorial path

Tutorials are designed to build on each other. Each one teaches a math concept *through* the art.

| # | Notebook | Math concept | Art outcome |
|---|----------|--------------|-------------|
| 01 | `01_lissajous.py` | Parametric curves, sin/cos | Lissajous figures |
| 02 | `02_mandelbrot.py` | Complex iteration | The Mandelbrot set |
| 03 | `03_julia_sets.py` | Parameter space | Julia set zoo |
| 04 | `04_kaleidoscope.py` | Dihedral symmetry groups | Kaleidoscopic patterns |
| 05 | `05_attractors.py` | Discrete dynamical systems | Orbit attractors |
| 06 | `06_random_walks.py` | Probability, CLT | Random walks, Rayleigh dist. |
| 07 | `07_ifs_basics.py` | Contraction mappings, chaos game | Sierpinski, Barnsley fern, fractal flames |
| 08 | `08_ifs_animations.py` | Interpolation in transform space | Morphing fractals |
| 09 | `09_ifs_3d.py` | 3D affine transforms, projection | 3D IFS attractors |
| 10 | `10_dashboard.py` | Layout, app deployment | Combined gallery |

## 🧱 Project structure

```
chaos-canvas/
├── src/chaos_canvas/      # Reusable library (chaos_game, transforms, render…)
├── notebooks/             # marimo tutorials (start here!)
├── gallery/               # Saved renders (PNGs, MP4s)
├── docs/                  # Math notes & references
├── scripts/               # Headless renderers
└── tests/                 # Library tests
```

## 🧠 Math philosophy

Every tutorial answers three questions:

1. **What's the rule?** (the equation)
2. **Why does it produce *this* shape?** (the intuition)
3. **What can we change, and what happens?** (interactive sliders)

If a tutorial only does #1, it's not done.

## 🛠️ Development

```bash
# Run tests
uv run pytest

# Format & lint
uv run ruff format .
uv run ruff check .

# Type-check
uv run mypy src/
```

## 📦 Adding a new dependency

```bash
uv add some-package           # adds to pyproject.toml + installs
uv remove some-package        # removes
uv sync                       # re-syncs from lockfile
```

You can also install packages from the marimo UI — they'll be added to `pyproject.toml` automatically.

## 🎁 Inspiration & credits

- **[Simone Conradi](https://twitter.com/profConradi)** — *"I draw using mathematics and Python."* The artistic inspiration.
- **[3Blue1Brown](https://www.3blue1brown.com/)** — the gold standard for mathematical exposition.
- **[marimo](https://marimo.io)** — the reactive notebook that makes this interactive magic possible.
- **Michael Barnsley**, *Fractals Everywhere* — the foundational IFS reference.
- **Scott Draves**, *The Fractal Flame Algorithm* — the technique behind density rendering.

## 📖 References

See [`docs/references.md`](docs/references.md) for papers, books, and links.

## 📄 License

MIT 
