# Φ Model — Targeted Automatic Stabilizer for Solvable Demand

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23862920.svg)](https://doi.org/10.5281/zenodo.23862920)

🇫🇷 [Version française ici](README.fr.md)

Replication code for the working paper:
**The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK and Two-Asset Evaluation for France**
Sébastien Delestre (Independent Researcher)
Archived on Zenodo: [DOI: 10.5281/zenodo.23862920](https://doi.org/10.5281/zenodo.23862920) | SSRN Working Paper No. 7597138

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
| Section 6: Two-Asset | `V18_phi.ipynb` (Blocks 4-5) | 5 GE modes, kink bell curve |
| Figures 1–4 | `V18_phi.ipynb` (Blocks 7.2, 7.3) | Paper figures |

### Exploratory (outside the paper, v18)
These sections explore the robustness and extensions of the model. They are documented and reproducible, but are not part of the SSRN paper.
| Extension | Location | Status |
| :--- | :--- | :--- |
| Historical Simulation 2000–2025 | `V18_phi.ipynb` (Block 7.1) | Exploratory (backtest) |
| Sovereign Fund & Investment | `V18_phi.ipynb` (Block 7.2) | Institutional design |
| ARE (Economic Regulation Authority) | `V18_phi.ipynb` (Blocks 1 & 4) | Institutional design |

## The v18 Model

The `V18_phi.ipynb` notebook unifies the entire project. It is structured into 8 blocks (0 to 7) and integrates a **6 Checkpoint** system (CP-1 to CP-6) that verifies 146 indicators against a reference `EXPECTED` dictionary.

- **Blocks 0–3**: HANK one-asset, calibration, multipliers, fiscal balance (paper results).
- **Blocks 4–5**: Two-Asset model with liquidity constraint and kink (paper results, Section 6).
- **Blocks 6–7**: Save/Audit, historical simulation 2000–2025 (extensions).

## Key Results — HANK (One-Asset)

| Indicator | Value |
| :--- | :--- |
| β* (France) | 0.9862 (CepreHANK ref: 0.9870) |
| λ_HtM (absolute) | 26.94 % |
| MPC of Φ beneficiaries | 0.7817 |
| Multiplier μ (8Q) | +0.775 |
| Φ disbursed | €35.49 bn/year (€31.94 bn net) |
| Jobs created — Φ channel | 75.1k FTE |
| Jobs created — bc channel | 293.6k FTE |
| **Jobs created — total** | **369k FTE** (75.1k + 293.6k) |
| Net government balance (central) | +€9.75 bn/year |
| Steady-state unemployment | 6.98 % → **6.73 %** |
| Δπ induced by Φ | +0.197 % (<< 2 % ARE threshold) |

*Sensitivity to the hiring elasticity `elasticite_bc` (0.05–0.50) spans 108k–741k jobs; the central value (elasticite_bc = 0.15) is 369k.*

## Key Results — Two-Asset (Extension)

| Indicator | Value |
| :--- | :--- |
| β (Two-Asset SS) | 0.9924 |
| χ₁ (friction parameter) | 14.9993 |
| λ_HtM | 26.09 % |
| n_htm_ss | 32.38 % |
| Steady-state unemployment | 7.48 % (u_court 5.63 % + u_long 1.85 %) |
| Multiplier μ (8Q) — niches + kink | +0.199 |
| Multiplier μ (8Q) — broad + kink | +0.237 |
| Multiplier μ (8Q) — lump-sum + kink | +0.044 |
| Multiplier μ (8Q) — lump-sum, no kink | −0.078 |

## Three Novel Observations on the Selling Friction (Kink)

The Two-Asset model (Kaplan-Moll-Violante, 2018) reveals three mechanisms that, to our knowledge, have not been explicitly documented in the fiscal multiplier literature:

1. **The kink is neutral for niches.** μ = 0.199 with kink vs 0.194 without (Δ = 0.0055). The selling friction does not explain the multiplier decline; the recalibration does.
2. **The kink is crucial for lump-sum.** μ = +0.044 with kink vs −0.078 without. Without friction, Ricardian households overreact and the multiplier becomes negative. The friction acts as a calming mechanism.
3. **Bell curve of the friction.** The lump-sum multiplier as a function of χ₀,sell peaks at an economic optimum (χ₀,sell ≈ 0.10). Below: overreaction. Above: transaction blocking.

## Reproducibility

The notebook is designed to run from start to finish (`Runtime → Restart and Run All`).
Estimated runtime: ~1h30 to 1h45 (calibration, continuation, Two-Asset steady state, and 5 GE modes are the most time-consuming blocks).
Upon completion, all 6 Checkpoints must display **OK (0 KO)**, and the `figures V18/` and `results V18/` folders must contain the generated PNGs and backup files (pickles, audits, RECAP).

**Note on figures:** 10 PNGs are generated by default (Blocks 7.2 and 7.3). The optional Block 7.3bis (`fig_recap_chiffres_cles.png`) requires adding the corresponding keys to `HANK_V17['critical']` in Block 6.3 before running.

## Repository Structure

```text
phi-hank-france/
├── README.md (English version)
├── README.fr.md (French version)
├── RESUME_EXECUTIF.md
├── ECONOMIC_ARCHITECTURE_NOTE.md
├── Economic_Architecture_Note.pdf
├── paper.pdf
├── V18_phi.ipynb (Main v18 notebook)
├── requirements.txt
├── figures V18/ (10 generated PNGs by default)
├── results V18/ (Pickles, JSON, CSV)
└── LICENSE (MIT)
Installation
bash
git clone https://github.com/sebastien-edl/phi-hank-france.git
cd phi-hank-france
pip install -r requirements.txt
jupyter notebook V18_phi.ipynb
AI Disclosure
The author used AI assistants (notably for Python code generation and writing assistance) in the preparation of this work. All numerical results were verified, recalculated, and validated by the author. The author assumes full responsibility for the content and any remaining errors.

License
This project is licensed under the MIT License. You are free to use, modify, and distribute it, provided the original copyright notice is retained.



