# Modèle Φ — Stabilisateur automatique ciblé sur la demande solvable

🇬🇧 [English version here](README.md)

Code de réplication pour le working paper :
**The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK-Based Simulation for France**
Sébastien Delestre (Chercheur indépendant)
SSRN Working Paper No. 7597138 | [DOI: 10.2139/ssrn.7597138](https://doi.org/10.2139/ssrn.7597138)

## À propos de ce dépôt

Ce dépôt contient le code utilisé pour produire les résultats du papier, ainsi que les extensions exploratoires développées dans le cadre du projet (notamment le modèle à deux actifs).

**Distinction importante :** Seul le code identifié comme « validé » ci-dessous est documenté et reproduit les résultats du papier publié. Les extensions exploratoires sont incluses par transparence, mais ne doivent pas être citées comme des résultats du papier sans vérification préalable.

## Contenu du dépôt

### Dans le papier (validé)
| Section du papier | Fichier | Contenu |
| :--- | :--- | :--- |
| Section 4 : Modèle | `V18_phi.ipynb` (Blocs 0-1) | Modèle HANK one-asset, 10 états (KMP) |
| Section 4.2 : Calibration | `V18_phi.ipynb` (Bloc 2) | Continuation US → France |
| Section 4.4 : Diagnostics | `V18_phi.ipynb` (Bloc 2) | β*, λ_HtM, MPC |
| Section 5 : Résultats | `V18_phi.ipynb` (Bloc 3) | Multiplicateur, emploi, bilan budgétaire |
| Section 6 : Φ comme stabilisateur | `V18_phi.ipynb` (Bloc 3) | ε_Φ, α_Φ, Proposition 1 |
| Figures 1–4 | `V18_phi.ipynb` (Bloc 7) | Les figures du papier |

### Exploratoire (hors papier, v18)
Ces sections explorent la robustesse et les extensions du modèle. Elles sont documentées et reproductibles, mais ne font pas partie du papier SSRN.
| Extension | Emplacement | Statut |
| :--- | :--- | :--- |
| Modèle Two-Asset (SJ) | `V18_phi.ipynb` (Blocs 4-5) | Testé (5 modes GE, courbe en cloche du kink) |
| Simulation historique 2000–2025 | `V18_phi.ipynb` (Bloc 7) | Exploratoire (backtest) |
| Fonds Souverain & Investissement | `V18_phi.ipynb` (Bloc 7) | Design institutionnel |
| ARE (Autorité de Régulation) | `V18_phi.ipynb` (Blocs 1 & 4) | Design institutionnel |

## Le modèle v18

Le notebook `V18_phi.ipynb` unifie l'ensemble du projet. Il est structuré en 8 blocs (0 à 7) et intègre un système de **6 Checkpoints** (CP-1 à CP-6) qui vérifient 146 indicateurs par rapport à un dictionnaire `EXPECTED` de référence.

- **Blocs 0–3** : HANK one-asset, calibration, multiplicateurs, bilan budgétaire (résultats du papier).
- **Blocs 4–5** : Modèle Two-Asset avec contrainte de liquidité et kink (extension).
- **Blocs 6–7** : Sauvegardes, audits et simulation historique 2000–2025 (extensions).

## Résultats clés (HANK One-Asset)

| Indicateur | Valeur |
| :--- | :--- |
| β* (France) | 0.9862 (réf. CepreHANK : 0.9870) |
| λ_HtM | 26.9 % |
| Multiplicateur μ (8T) | +0.775 |
| Φ versé | 35.49 Md€/an |
| Emplois créés (central) | ~183 k ETP |
| Solde net État (central) | +9.75 Md€/an |
| Δπ induit par Φ | +0.20 % (<< seuil ARE 2 %) |

## Reproductibilité

Le notebook est conçu pour être exécuté de bout en bout (`Runtime → Restart and Run All`).
Durée estimée : ~1h15.
À la fin de l'exécution, les 6 Checkpoints doivent afficher **OK (0 KO)**, et les dossiers `figures/` et `results/` doivent contenir les 13 PNG et les fichiers de sauvegarde (pickles, audits, RECAP).

## Structure du dépôt


phi-hank-france/
├── README.md (Version anglaise)
├── README.fr.md (Version française)
├── ECONOMIC_ARCHITECTURE_NOTE.md
├── Economic_Architecture_Note.pdf
├── V18_phi.ipynb (Notebook principal v18)
├── requirements.txt
├── figures/ (13 PNG générées)
├── results/ (Pickles, JSON, CSV)
└── LICENSE (MIT)

Installation
git clone https://github.com/votre-nom/phi-hank-france.git
cd phi-hank-france
pip install -r requirements.txt
jupyter notebook V18_phi.ipynb

Déclaration d'usage de l'IA
L'auteur a utilisé des assistants IA (notamment pour la génération de code Python et l'aide à la rédaction) dans la préparation de ce travail. Tous les résultats numériques ont été vérifiés, recalculés et validés par l'auteur. L'auteur assume l'entière responsabilité du contenu et des erreurs restantes.

Licence
Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, de le modifier et de le distribuer, à condition de conserver la mention de copyright originale.
