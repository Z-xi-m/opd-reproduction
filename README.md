# OPD Reproduction

This repository tracks my reproduction work on recent open-source
on-policy distillation (OPD) projects for large language models.

## Goals

- Reproduce representative OPD methods published or actively updated around
  2026.
- Record environment setup, data preparation, training commands, evaluation
  commands, failures, fixes, and final results.
- Compare practical differences across modern OPD variants rather than only
  collecting paper summaries.

## Reproduction Order

| Order | Project | Local source | My fork | Status |
| --- | --- | --- | --- | --- |
| 1 | THUNLP OPD | `../01_thunlp_OPD` | https://github.com/Z-xi-m/OPD | Not started |
| 2 | G-OPD | `../02_G-OPD` | https://github.com/Z-xi-m/G-OPD | Not started |
| 3 | OPSD | `../03_OPSD` | https://github.com/Z-xi-m/OPSD | Not started |
| 4 | Revisiting OPD | `../04_revisiting_opd` | https://github.com/Z-xi-m/revisiting_opd | Not started |
| 5 | CaOPD | `../05_CaOPD` | https://github.com/Z-xi-m/CaOPD | Not started |

## Repository Layout

- `projects/`: per-project reproduction notes.
- `env/`: environment setup notes and dependency records.
- `results/`: experiment tables, logs, plots, and evaluation summaries.

## Method Notes

The initial focus is code-level reproducibility:

- identify the intended entry scripts,
- pin model and dataset dependencies,
- run a minimal sanity check,
- run the closest feasible reproduction experiment,
- document deviations from the original setup.

## Hardware

To be filled in before the first run.

| Item | Value |
| --- | --- |
| GPU | TBD |
| CUDA | TBD |
| Driver | TBD |
| Python | TBD |
| Main framework | TBD |

## Progress

| Date | Project | Update |
| --- | --- | --- |
| 2026-05-11 | Workspace | Downloaded source repositories and prepared GitHub binding plan. |
