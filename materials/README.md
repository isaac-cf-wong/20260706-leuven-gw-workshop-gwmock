# Workshop materials — gwmock hands-on (Leuven GW Workshop)

Hands-on notebooks for the session — one per part. Six short, self-contained
notebooks; everything runs on a laptop **or** in Google Colab in a few minutes,
and the example runs are deliberately small (seconds each).

| #   | Notebook                                                               | Section                                    |
| --- | ---------------------------------------------------------------------- | ------------------------------------------ |
| 0   | [`00-installation-setup.ipynb`](notebooks/00-installation-setup.ipynb) | Installation & setup, ecosystem + CLI tour |
| 1   | [`01-quickstart-mdc.ipynb`](notebooks/01-quickstart-mdc.ipynb)         | Quickstart — your first MDC                |
| 2   | [`02-populations.ipynb`](notebooks/02-populations.ipynb)               | Populations — `gwmock-pop`                 |
| 3   | [`03-signals.ipynb`](notebooks/03-signals.ipynb)                       | Signals — `gwmock-signal`                  |
| 4   | [`04-noise.ipynb`](notebooks/04-noise.ipynb)                           | Noise — `gwmock-noise`                     |
| 5   | [`05-end-to-end.ipynb`](notebooks/05-end-to-end.ipynb)                 | End-to-end MDC, provenance, SGWB           |

## Run on Google Colab

Each notebook's **first code cell** installs gwmock
(`%pip install "gwmock[sgwb]"`), and all data/configs are written inline with
`%%writefile` — so the notebooks are fully self-contained and need no repo
checkout on Colab. Open a notebook via its **"Open in Colab" badge**, which
points at
`colab.research.google.com/github/isaac-cf-wong/20260706-leuven-gw-workshop-gwmock/blob/main/materials/notebooks/<notebook>.ipynb`.

> The badges work once this repo is **public** on GitHub (Colab needs to read
> the notebook from GitHub). A bare repo link does not open Colab — use the
> badge, or paste the repo URL into Colab's **File → Open notebook → GitHub**
> tab to browse all notebooks.

## Run locally

Requires Python **3.12–3.14**. With [`uv`](https://docs.astral.sh/uv/):

```bash
uv venv --python 3.13
source .venv/bin/activate
uv pip install "gwmock[sgwb]" jupyterlab matplotlib
jupyter lab        # then open materials/notebooks/
```

(`matplotlib` is used for the plots; `jupyterlab` to run the notebooks. The
`[sgwb]` extra is required for the stochastic-background examples.)

## Verified

All six notebooks were executed end-to-end against the released `gwmock 0.9.0`
(`gwmock-signal 0.9.3`, `gwmock-noise 0.6.1`, `gwmock-pop 0.10.3`). Key checks
that pass:

- `merge` → `data == signal + noise` exactly
- merged strain ASD tracks the input `ET_10_full_cryo_psd` curve
- `compare_psd` confirms coloured noise matches the requested preset
- SGWB strain PSD vs. theory → median ratio ≈ 1 over 8–200 Hz
- SGWB cross-channel Pearson correlation ≈ 0.98
- reproduce-from-metadata (SGWB HDF5) → **bit-identical** arrays

Upstream issues found during prep were fixed and released before the workshop
(gwmock 0.9.0 / gwmock-pop 0.10.3 / gwmock-noise 0.6.1) — the full record is in
[`../MAINTAINER-NOTES.md`](../MAINTAINER-NOTES.md).
