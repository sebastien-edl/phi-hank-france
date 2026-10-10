# Modèle Φ — Stabilisateur automatique ciblé sur la demande solvable

Modèle HANK (Heterogeneous Agent New Keynesian) one-asset avec :
- Grille KMP 10 états (Kaplan-Moll-Violante 2018)
- ARE à paliers (surprime anti-inflation à seuils)
- Comparaison Two-Agent
- Extension non-linéaire (courbure Phillips)
- Fonds Souverain (bouclier inversé en récession)

## Résultats clés

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

## Structure

- `V16_4.ipynb` — notebook principal (sections 1 à 39)
- `requirements.txt` — dépendances Python
- `LICENSE` — MIT

## Hypothèses structurelles

1. One-asset (pas de two-asset)
2. Marge extensive absente (offre de travail fixe)
3. Inflation observée (INSEE), pas simulée
4. Coefficients ad hoc chiffrés par scénarios
5. Non-linéarité : SJ conçu pour le linéaire

## Références

- Krusell & Smith (1998), JPE 106(5)
- Kaplan, Moll & Violante (2018), AER 108(3)
- Auclert et al. (2021), Econometrica 89(5)
- Auerbach & Gorodnichenko (2012), JEL
- Ramey & Zubairy (2018), JPE
- INSEE (2024), Comptes nationaux trimestriels
- CepreHANK (i-MIP-Cepremap), COR

## Auteur

Sébastien Delestre — 2026

## Licence

MIT