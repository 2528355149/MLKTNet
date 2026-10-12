# MLKTNet

A modality-aware knowledge transfer network for brain tumor segmentation with missing modalities.

[![Code](https://img.shields.io/badge/Code-Coming%20Soon-lightgrey)](#release-plan)
[![Weights](https://img.shields.io/badge/Pretrained%20Weights-Coming%20Soon-lightgrey)](#release-plan)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> ## 📌 Status: Work in Progress
>
> The source code **and pretrained weights are coming soon**.
>
> For now this repository provides only the **high-level method overview**, the
> **dataset / evaluation protocols**, and the **release roadmap**, while the implementation
> and trained parameters are kept private until the code release.

---

## Overview

Multi-modal MRI (FLAIR, T1, T1ce, T2) is essential for brain tumor segmentation, but in clinical
practice modalities are frequently missing, which severely degrades full-modality models. MLKTNet
transfers knowledge from a **full-modality teacher** to a **lightweight student** so that the
student stays robust under **randomly missing modalities**, following a multi-level
(channel / semantic / structural / output) knowledge-transfer design.

The student takes a fixed 4-channel input (missing modalities zero-filled) together with a
4-dimensional modality-availability vector, so a **single set of weights covers all 15 non-empty
modality combinations** — no modality synthesis and no per-combination branches.

> The individual modules, their objectives, and the exact implementation will be released
> together with the code.

## Repository Contents

| Path | Description | Available |
|---|---|---|
| `docs/architecture.md` | High-level method overview (text only) | ✅ now |
| `docs/dataset.md` | Datasets & exact preprocessing pipeline | ✅ now |
| `docs/evaluation.md` | Evaluation metrics & 15-combination protocol | ✅ now |
| `docs/roadmap.md` | Release timeline | ✅ now |
| `requirements.txt` | Python dependencies (tentative) | ✅ now |
| `src/` | Source code (model & training) | ⏳ coming soon |
| `weights/` | Pretrained student weights | ⏳ coming soon |
| `data/` | Preprocessing & feature-extraction scripts | ⏳ coming soon |

## Release Plan

See [`docs/roadmap.md`](docs/roadmap.md). In short:

- [ ] Release inference code
- [ ] Release training code (teacher–student distillation)
- [ ] Release pretrained weights
- [ ] Release preprocessing / feature-extraction scripts

We are committed to **open-sourcing the full implementation and pretrained weights** to support
reproducibility and follow-up research.

## Contact

For questions regarding the upcoming release, please open an issue in this repository.

## License

Released under the [MIT License](LICENSE).
