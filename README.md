# LAA-SFCI AF Stratifier

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20899949.svg)](https://doi.org/10.5281/zenodo.20899949)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

A TEE-based Left Atrial Appendage **Structure–Function Coupling** calculator: an offline,
single-page (single-file HTML) tool that computes candidate LAA structure–function coupling
indices (LAA-SFCIs) from transesophageal echocardiography (TEE)-derived parameters and displays
an auxiliary AF disease-stage **profile** based on the study-derived parameter pattern.

This software accompanies the article (under review):

> *A Transesophageal Echocardiography–Derived Left Atrial Appendage Structure–Function Coupling
> Index Across the Atrial Fibrillation Disease Continuum.* (Authors and full citation to be
> updated on acceptance.)

---

## ⚠️ Intended use and disclaimer

- **For research demonstration and educational use only.** It is **not** a medical device and has
  **not** been validated for clinical diagnosis or treatment decisions.
- The displayed stage values are **parameter-profile similarity scores** computed from the
  parameter distributions of a single-center, cross-sectional study. **They are not individual
  diagnostic probabilities** and must not be interpreted as such.
- All outputs should be interpreted together with clinical history, ECG/Holter findings, rhythm
  during TEE, CHA₂DS₂-VASc score, and TEE thrombus-related findings (SEC, LAA thrombus).
- **Do not enter any personally identifiable information.** The tool runs entirely in your
  browser; no data are transmitted or stored.

---

## How to use

1. Open `index.html` in any modern web browser (no installation, no internet connection required), **or**
   use the hosted version via GitHub Pages (see below).
2. Enter **LAA-VI** (required) and one or more LAA functional parameters
   (LAA-GLS and LAAPSE are recommended as priority inputs).
3. Click **Calculate and Stratify** to view the calculated candidate LAA-SFCIs, the principal-index
   cutoff interpretation, and the multi-index stage profile.
4. Use **Print / Save PDF** to export the result.

### Inputs and units
| Parameter | Unit expected by the tool | Note |
|---|---|---|
| LAA-VI | mL/m² | Required (LAA-EDV indexed to BSA) |
| LAA-GLS | % (absolute value) | Enter 10.03, not −10.03 |
| LAAPSE | mm | LAA longitudinal displacement |
| LAA-PEV / LAA-PFV / LAA-s′ | m/s | If recorded in cm/s, divide by 100 |
| LAA-FAC | decimal or % | 0.30 or 30 both accepted |

> **Note on units:** velocity-based ratios are computed with velocities in m/s; the manuscript
> tables report some velocities in cm/s. The ratios are mathematically equivalent — only the unit
> convention differs. Please follow the in-app field hints when entering values.

The principal LAA-SFCI is **LAA-VI/LAA-GLS**. Stage reference values and ROC-derived cutoffs
embedded in the tool correspond to the final analysis reported in the article
(e.g., the Stage 1–2 vs Stage 3a–3b transition: AUC 0.904, cutoff 0.460).

---

## Hosting on GitHub Pages (optional)

Because the tool is a single self-contained `index.html`, you can serve it for free:

1. Push this repository to GitHub.
2. Go to **Settings → Pages → Build and deployment**.
3. Set **Source = Deploy from a branch**, **Branch = `main` / root**, then **Save**.
4. After a minute the tool will be live at `https://zzzzz11zz776.github.io/LAA-SFCI-tool/`.

---

## Citation

If you use this tool, please cite both the article and this software archive. See
[`CITATION.cff`](./CITATION.cff). The archived version has a permanent DOI:
**10.5281/zenodo.20899949**.

---

## License

Code is released under the [MIT License](./LICENSE). You are free to use, modify, and redistribute
it with attribution. (If you prefer a content/data license such as CC BY 4.0 for the embedded
reference values, state that explicitly when you deposit on Zenodo.)
