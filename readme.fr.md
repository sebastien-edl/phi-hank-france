# Modèle Φ — Stabilisateur automatique ciblé sur la demande solvable

🇬🇧 **[English version here](README.md)**

Code de réplication pour le working paper :

> **The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK-Based Simulation for France**
> Sébastien Delestre (Chercheur indépendant)
> SSRN Working Paper No. 7597138
> DOI: [10.2139/ssrn.7597138](https://doi.org/10.2139/ssrn.7597138)
> [Papier sur SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7597138)

---

## Ce que contient ce dépôt

Ce dépôt contient le code utilisé pour produire les résultats du papier **et** des extensions exploratoires qui **ne sont pas** dans le papier publié.

Cette distinction est importante : seul le code listé sous « Dans le papier » est validé et documenté. Le reste est exploratoire, peut être incomplet, et ne doit pas être cité comme un résultat du papier.

### Dans le papier (validé)

| Section du papier | Fichier | Ce que fait le code |
|---|---|---|
| Section 4 : Modèle | `V16_4.ipynb` (cellules 1–11) | Modèle HANK one-asset, 10 états |
| Section 4.2 : Calibration | `V16_4.ipynb` (cellule 10) | Continuation US → France |
| Section 4.4 : Diagnostics | `V16_4.ipynb` (cellule 11) | β*, λ_HtM, MPC |
| Section 5 : Résultats | `V16_4.ipynb` (cellules 12–21) | Multiplicateur, emploi, bilan |
| Section 6 : Φ comme stabilisateur | `V16_4.ipynb` (cellule 6.3) | ε_Φ, α_Φ, Proposition 1 |
| Figures 1–4 | `V16_4.ipynb` (cellule 40) | Les 4 figures du papier |

### Exploratoire (pas dans le papier)

| Extension | Cellules du notebook | Statut |
|---|---|---|
| ARE (Autorité de Régulation Économique) | Cellules 28–32 | Design institutionnel, non testé |
| Fonds Souverain | Cellules 33–36 | Design institutionnel, non testé |
| Investissement stratégique | Cellule 39 | Design institutionnel, non testé |
| Φ différencié | Cellule 39 bis | Simulation historique 2000–2025 |
| Simulation historique | Cellule 39 | Backtest 2000–2025 |

Ces extensions sont incluses par transparence, pas comme résultats validés. Elles reflètent la vision plus large du projet (régulation institutionnelle de la demande solvable), mais elles ne font pas partie du papier SSRN et ne doivent pas être traitées comme telles.

---

## Le modèle

Modèle HANK (Heterogeneous Agent New Keynesian) one-asset avec :

- Grille KMP 10 états (Kaplan-Moll-Violante 2018)
- ARE à paliers (surprime anti-inflation à seuils)
- Comparaison Two-Agent
- Extension non-linéaire (courbure Phillips)
- Fonds Souverain (bouclier inversé en récession)

### Résultats clés

| Indicateur | Valeur |
|---|---|
| β* (France) | 0.9862 (réf. CepreHANK : 0.9870) |
| λ_HtM | 26.9 % |
| Multiplicateur μ (8T) | +0.775 |
| Φ versé | 35.49 Md€/an |
| Emplois créés (central) | ~183 k ETP |
| Solde net État (central) | +9.75 Md€/an |
| Marge de manœuvre | +4.73 Md€/an |
| Δπ induit par Φ | +0.20 % (<< seuil ARE 2 %) |
| Contribution à la stabilisation (Section 6) | ~1 % |

---

## Structure du dépôt

```text
phi-hank-france/
├── README.md             # English version
├── README.fr.md          # Version française (ce fichier)
├── V16_4.ipynb           # Notebook principal (sections 1 à 40)
├── requirements.txt      # Dépendances Python
└── LICENSE               # MIT
