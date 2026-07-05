# gwmock — Leuven GW Workshop hands-on session

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Reveal.js](https://img.shields.io/badge/reveal.js-6.x-orange.svg)](https://revealjs.com/)
[![CI](https://github.com/isaac-cf-wong/20260706-leuven-gw-workshop-gwmock/actions/workflows/ci.yml/badge.svg)](https://github.com/isaac-cf-wong/20260706-leuven-gw-workshop-gwmock/actions/workflows/ci.yml)
[![Publish](https://github.com/isaac-cf-wong/20260706-leuven-gw-workshop-gwmock/actions/workflows/publish.yml/badge.svg)](https://isaac-cf-wong.github.io/20260706-leuven-gw-workshop-gwmock/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![typos](https://img.shields.io/badge/spell--check-typos-brightgreen)](https://github.com/crate-ci/typos)

Slides and hands-on notebooks for the **gwmock** session at the
[Leuven GW Workshop: From perturbation theory to future detections](https://indico.fys.kuleuven.be/event/212/overview)
(KU Leuven, 6 July 2026, 10:30–12:00).

[gwmock](https://leuven-gravity-institute.github.io/gwmock) is a Mock Data
Challenge (MDC) framework for gravitational-wave data, built for the **Einstein
Telescope**. This session is a general tour of the whole toolbox: the config/CLI
orchestration layer plus the three Python engines (`gwmock-pop`,
`gwmock-signal`, `gwmock-noise`).

## Attending? Start here

Everything hands-on lives in [`materials/notebooks/`](materials/notebooks/) —
six short, self-contained notebooks. Two ways to run them:

- **Google Colab** (nothing to install): open a notebook via its "Open in Colab"
  badge; the first cell installs gwmock.
- **Locally** (Python 3.12–3.14):

    ```bash
    uv venv --python 3.13 && source .venv/bin/activate
    uv pip install "gwmock[sgwb]" jupyterlab matplotlib
    jupyter lab    # open materials/notebooks/
    ```

Details in [`materials/README.md`](materials/README.md).

## Session outline (90 min)

0. **Installation & setup** — ecosystem + CLI tour
1. **Quickstart** — YAML config → BBH signal + ET noise → GWF → merge + validate
2. **Populations** — `gwmock-pop`: presets (GWTC-4), swappable priors,
   catalogues
3. **Signals** — `gwmock-signal`: waveforms, detector projection, custom models,
   SGWB
4. **Noise** — `gwmock-noise`: ET sensitivity curves, lines, glitches, streaming
5. **End-to-end** — population-driven MDC, provenance & bit-identical replay,
   SGWB anchored to theory

Every notebook ends with a **Try it** block.

## Repository layout

```text
slides/               # reveal.js intro deck (markdown, one file per slide)
index.html            # loads the slides
materials/
  README.md           # how to run the notebooks (local + Colab)
  notebooks/          # the six workshop notebooks
MAINTAINER-NOTES.md   # findings from prep (all fixed upstream) + verification workflow
```

## Verification

All six notebooks were executed end-to-end against the released stack
(`gwmock 0.9.0`, `gwmock-signal 0.9.3`, `gwmock-noise 0.6.1`,
`gwmock-pop 0.10.3`), and the quantitative anchor checks they contain — merge
exactness, ASD vs input PSD, SGWB PSD vs theory, bit-identical metadata replay —
all pass. Issues found during preparation were fixed and released upstream
before the workshop; the record is in
[`MAINTAINER-NOTES.md`](MAINTAINER-NOTES.md).

## Building the slides

Prerequisites: Node.js 18.x or 20.x.

```bash
npm install
npm start          # dev server with live reload at http://localhost:8000
npm run build      # production build into dist/
```

Controls: arrows/space to navigate, **S** for speaker notes, **F** fullscreen,
**ESC** overview, **?** for help. Export to PDF by appending `?print-pdf` to the
URL and printing (landscape).

## Links

- gwmock docs: <https://leuven-gravity-institute.github.io/gwmock>
- Source: <https://github.com/Leuven-Gravity-Institute/gwmock>
- Event page: <https://indico.fys.kuleuven.be/event/212/overview>

## License

MIT — see [LICENSE](LICENSE).
