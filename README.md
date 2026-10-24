# Model Φ — Targeted Automatic Stabilizer for Solvable Demand

🇫🇷 **[Version française ici](README.fr.md)**

Replication code for the working paper:

> **The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK-Based Simulation for France**
> Sébastien Delestre (Independent Researcher)
> SSRN Working Paper No. 7597138
> DOI: [10.2139/ssrn.7597138](https://doi.org/10.2139/ssrn.7597138)
> [Paper on SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7597138)

---

## What this repository contains

This repository contains the code used to produce the results in the paper **and** some exploratory extensions that are **not** part of the published paper.

This distinction matters: only the code listed under "In the paper" is validated and documented. The rest is exploratory, may be incomplete, and should not be cited as a result of the paper.

### In the paper (validated)

| Paper Section | File | What the code does |
|---|---|---|
| Section 4: Model | `V16_4.ipynb` (cells 1–11) | One-asset HANK model, 10 states |
| Section 4.2: Calibration | `V16_4.ipynb` (cell 10) | US → France continuation |
| Section 4.4: Diagnostics | `V16_4.ipynb` (cell 11) | β*, λ_HtM, MPC |
| Section 5: Results | `V16_4.ipynb` (cells 12–21) | Multiplier, employment, balance |
| Section 6: Φ as stabilizer | `V16_4.ipynb` (cell 6.3) | ε_Φ, α_Φ, Proposition 1 |
| Figures 1–4 | `V16_4.ipynb` (cell 40) | The 4 figures of the paper |

### Exploratory (not in the paper)

| Extension | Notebook cells | Status |
|---|---|---|
| ARE (Economic Regulation Authority) | Cells 28–32 | Institutional design, untested |
| Sovereign Fund | Cells 33–36 | Institutional design, untested |
| Strategic investment | Cell 39 | Institutional design, untested |
| Differentiated Φ | Cell 39 bis | Historical simulation 2000–2025 |
| Historical simulation | Cell 39 | Backtest 2000–2025 |

These extensions are included for transparency, not as validated results. They reflect the broader vision of the project (institutional regulation of solvable demand), but they are not part of the SSRN paper and should not be treated as such.

---

## The model

HANK (Heterogeneous Agent New Keynesian) one-asset model with:

- 10-state KMP grid (Kaplan-Moll-Violante 2018)
- Tiered ARE (anti-inflation surcharge with thresholds)
- Two-Agent comparison
- Nonlinear extension (Phillips curve curvature)
- Sovereign Fund (inverse shield in recession)

### Key results

| Indicator | Value |
|---|---|
| β* (France) | 0.9862 (ref. CepreHANK: 0.9870) |
| λ_HtM | 26.9% |
| Multiplier μ (8Q) | +0.775 |
| Φ disbursed | €35.49 bn/year |
| Jobs created (central) | ~183k FTE |
| Net government balance (central) | +€9.75 bn/year |
| Fiscal margin | +€4.73 bn/year |
| Δπ induced by Φ | +0.20% (<< 2% ARE threshold) |
| Stabilization contribution (Section 6) | ~1% |

---

## Repository structure

phi-hank-france/
├── README.md                      # English version (this file)
├── README.fr.md                   # French version
├── ECONOMIC_ARCHITECTURE_NOTE.md  # Economic intuition & philosophy
├── Economic_Architecture_Note.pdf # PDF version of the Note
├── V16_4.ipynb                    # Main notebook (sections 1 to 40)
├── requirements.txt               # Python dependencies
└── LICENSE                        # MIT
