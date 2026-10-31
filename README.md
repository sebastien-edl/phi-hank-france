# Φ Model — Targeted Automatic Stabilizer for Solvable Demand

🇫🇷 [Version française ici](README.fr.md)

Replication code for the working paper:
**The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK-Based Simulation for France**
Sébastien Delestre (Independent Researcher)
SSRN Working Paper No. 7597138 | [DOI: 10.2139/ssrn.7597138](https://doi.org/10.2139/ssrn.7597138)

## About this repository

This repository contains the code used to produce the results of the paper, as well as the exploratory extensions developed within the project (notably the two-asset model).

**Important distinction:** Only the code listed under "In the paper (validated)" below is documented and reproduces the published results. Exploratory extensions are included for transparency but should not be cited as paper results without prior verification.

## Repository Content

### In the paper (validated)
| Paper Section | File | Content |
| :--- | :--- | :--- |
| Section 4: Model | `V18_phi.ipynb` (Blocks 0-1) | HANK one-asset model, 10 states (KMP) |
| Section 4.2: Calibration | `V18_phi.ipynb` (Block 2) | US → France continuation |
| Section 4.4: Diagnostics | `V18_phi.ipynb` (Block 2) | β*, λ_HtM, MPC |
| Section 5: Results | `V18_phi.ipynb` (Block 3) | Multiplier, employment, fiscal balance |
| Section 6: Φ as stabilizer | `V18_phi.ipynb` (Block 3) | ε_Φ, α_Φ, Proposition 1 |
| Figures 1–4 | `V18_phi.ipynb` (Block 7) | Paper figures |

### Exploratory (outside the paper, v18)
These sections explore the robustness and extensions of the model. They are documented and reproducible, but are not part of the SSRN paper.
| Extension | Location | Status |
| :--- | :--- | :--- |
| Two-Asset Model (SJ) | `V18_phi.ipynb` (Blocks 4-5) | Tested (5 GE modes, kink bell curve) |
| Historical Simulation 2000–2025 | `V18_phi.ipynb` (Block 7) | Exploratory (backtest) |
| Sovereign Fund & Investment | `V18_phi.ipynb` (Block 7) | Institutional design |
| ARE (Economic Regulation Authority) | `V18_phi.ipynb` (Blocks 1 & 4) | Institutional design |

## The v18 Model

The `V18_phi.ipynb` notebook unifies the entire project. It is structured into 8 blocks (0 to 7) and integrates a **6 Checkpoint** system (CP-1 to CP-6) that verifies 146 indicators against a reference `EXPECTED` dictionary.

- **Blocks 0–3**: HANK one-asset, calibration, multipliers, fiscal balance (paper results).
- **Blocks 4–5**: Two-Asset model with liquidity constraint and kink (extension).
- **Blocks 6–7**: Save/Audit, historical simulation 2000–2025 (extensions).

## Key Results (HANK One-Asset)

| Indicator | Value |
| :--- | :--- |
| β* (France) | 0.9862 (CepreHANK ref: 0.9870) |
| λ_HtM | 26.9 % |
| Multiplier μ (8Q) | +0.775 |
| Φ disbursed | €35.49 bn/year |
| Jobs created (central) | ~183k FTE |
| Net government balance (central) | +€9.75 bn/year |
| Δπ induced by Φ | +0.20 % (<< 2% ARE threshold) |

## Reproducibility

The notebook is designed to run from start to finish (`Runtime → Restart and Run All`).
Estimated runtime: ~1h15.
Upon completion, all 6 Checkpoints must display **OK (0 KO)**, and the `figures V18/` and `results V18/` folders must contain the 13 PNGs and backup files (pickles, audits, RECAP).

## Repository Structure

```text
phi-hank-france/
├── README.md (English version)
├── README.fr.md (French version)
├── ECONOMIC_ARCHITECTURE_NOTE.md
├── Economic_Architecture_Note.pdf
├── V18_phi.ipynb (Main v18 notebook)
├── requirements.txt
├── figures V18/ (13 generated PNGs)
├── results V18/ (Pickles, JSON, CSV)
└── LICENSE (MIT)

Installation
git clone https://github.com/your-name/phi-hank-france.git
cd phi-hank-france
pip install -r requirements.txt
jupyter notebook V18_phi.ipynb

AI Disclosure
The author used AI assistants (notably for Python code generation and writing assistance) in the preparation of this work. All numerical results were verified, recalculated, and validated by the author. The author assumes full responsibility for the content and any remaining errors.

License
This project is licensed under the MIT License. You are free to use, modify, and distribute it, provided the original copyright notice is retained.
