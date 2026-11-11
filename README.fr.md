# Φ Model — Stabilisateur Automatique Ciblé pour la Demande Solvable

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23862920.svg)](https://doi.org/10.5281/zenodo.23862920)

🇬🇧 [English version here](README.md)

Code de réplication pour le working paper :
**The Missing Institution: Solvable Demand as a Macroeconomic Function — A HANK and Two-Asset Evaluation for France**
Sébastien Delestre (Chercheur indépendant)
Archivé sur Zenodo : [DOI : 10.5281/zenodo.23862920](https://doi.org/10.5281/zenodo.23862920) | SSRN Working Paper No. 7597138

---

## 1. Le Problème : l'angle mort institutionnel

L'architecture macroéconomique moderne dispose d'institutions dédiées à la stabilité monétaire (banques centrales), à la stabilité financière (ACPR), et à la concurrence. Aucune institution, cependant, n'a explicitement pour mandat de réguler la **demande solvable** — le pouvoir d'achat effectivement disponible pour convertir des besoins en transactions marchandes.

Le débat public reste binaire : l'offre ou la demande. Aucun des deux camps ne propose d'institution permanente et fondée sur des règles pour réguler ce moteur. C'est cet angle mort que le dispositif Φ propose de combler.

---

## 2. La Solution : Φ, un stabilisateur ciblé

Φ est un stabilisateur automatique qui verse une prime horaire aux travailleurs modestes (**13 millions de bénéficiaires**, ciblés sur les six premiers déciles).

- **Pourquoi eux ?** Parce que leur propension marginale à consommer (PMC) est de **78,17 %**. Chaque euro transféré génère une forte réponse de consommation.
- **Comment est-il financé ?** Par la redirection de **32 milliards d'euros** de niches fiscales existantes. Ce n'est pas un nouvel impôt, ni de la dette supplémentaire. C'est une réallocation de ressources vers des agents à forte PMC.
- **Est-il inflationniste ?** Non. Le dispositif est contracyclique : la prime baisse automatiquement quand l'inflation monte (mécanisme ARE à 5 zones).

---

## 3. Les Chiffres Clés (Modèle HANK calibré France)

Testé dans un modèle HANK (*Heterogeneous Agent New Keynesian*) à 10 états, validé par **146 indicateurs** et **6 Checkpoints**, Φ produit les résultats suivants :

| Indicateur | Valeur | Interprétation |
| :--- | :--- | :--- |
| Multiplicateur budgétaire (8T) | **0,775** | Dans la fourchette empirique [0,5 ; 1,5]. |
| Emplois créés — canal Φ | 75,1k ETP | Transfert direct. |
| Emplois créés — canal bc | 293,6k ETP | Baisse de charges. |
| **Emplois créés — total** | **369k ETP** | Estimation centrale (fourchette : 108k à 741k selon `elasticite_bc` ∈ [0,05 ; 0,50]). |
| Solde net de l'État | **+9,75 Md€/an** | Le dispositif s'autofinance grâce aux retours fiscaux. |
| Inflation induite | **+0,197 %** | Bien en dessous du seuil de surchauffe (2 %). |
| Chômage structurel (SS) | **6,98 % → 6,73 %** | Réduction de 0,25 point (comparaison de steady states). |

> **Note :** La fourchette 108k–741k correspond aux valeurs de robustesse de `elasticite_bc` (0,05 et 0,50). La valeur centrale (0,15) est 369k.

---

## 4. Les Résultats Two-Asset (Extension)

Le modèle Two-Asset (Kaplan-Moll-Violante, 2018) introduit une friction de vente (le « kink ») sur l'actif illiquide. Il produit les résultats suivants :

| Indicateur | Valeur |
| :--- | :--- |
| β (Two-Asset SS) | 0,9924 |
| χ₁ (paramètre de friction) | 14,9993 |
| λ_HtM | 26,09 % |
| n_htm_ss | 32,38 % |
| Chômage structurel (SS) | 7,48 % (u_court 5,63 % + u_long 1,85 %) |
| Multiplicateur μ (8T) — niches + kink | **+0,199** |
| Multiplicateur μ (8T) — broad + kink | +0,237 |
| Multiplicateur μ (8T) — lump-sum + kink | +0,044 |
| Multiplicateur μ (8T) — lump-sum, sans kink | −0,078 |

---

## 5. Les 3 Découvertes sur le Kink

Le modèle Two-Asset révèle trois mécanismes qui, à notre connaissance, n'avaient pas été documentés explicitement dans la littérature sur les multiplicateurs budgétaires :

1. **Le kink est neutre pour les niches.** μ = 0,199 avec kink vs 0,194 sans (Δ = 0,0055). La friction de vente n'explique pas la baisse du multiplicateur ; c'est la recalibration qui l'explique.
2. **Le kink est crucial pour le lump-sum.** μ = +0,044 avec kink vs −0,078 sans. Sans friction, les ménages ricardiens sur-réagissent et le multiplicateur devient négatif. La friction agit comme un mécanisme de calmage.
3. **Courbe en cloche de la friction.** Le multiplicateur lump-sum en fonction de χ₀,sell atteint un optimum économique (χ₀,sell ≈ 0,10). En dessous : sur-réaction. Au-dessus : blocage des transactions.

---

## 6. Les Limites (Transparence)

Ce travail est un *draft* préliminaire. Il ne prétend pas détenir la vérité. Les limites sont documentées explicitement :

- **Modèle à un actif :** Le modèle HANK sous-estime la part de ménages *hand-to-mouth* (26,94 % contre 30-35 % selon l'INSEE). Les résultats sont donc des bornes inférieures conservatrices.
- **Coefficients calibrés :** L'élasticité d'embauche (**4,0**) et l'élasticité de la baisse de charges (**0,15**) sont des choix méthodologiques, non des estimations économétriques. Le taux de retour fiscal agrégé (30 %) et le taux du scénario central (29,75 %) sont également des choix.
- **Inflation post-traitée :** L'inflation est calculée en post-traitement (π = κŷ), pas simulée de manière endogène.
- **Chômage en steady-state uniquement :** Les chiffres de chômage sont des comparaisons de steady states (pré-Φ vs post-Φ), pas des trajectoires de transition. La trajectoire complète *u_t* est renvoyée à une version ultérieure.
- **Économie fermée (Two-Asset) :** Les fuites d'importations sont intégrées dans le HANK, mais pas dans le Two-Asset.

---

## 7. Reproductibilité

Le notebook `V18_phi.ipynb` est conçu pour tourner de bout en bout (*Runtime → Restart and Run All*).

- **Durée estimée :** ~1h30 à 1h45 (la calibration, la continuation US→France, le steady state Two-Asset et les 5 modes GE sont les blocs les plus longs).
- **À la fin :** les 6 Checkpoints doivent afficher **OK (0 KO)**, et les dossiers `figures V18/` et `results V18/` doivent contenir les PNGs générés et les fichiers de sauvegarde (pickles, audits, RECAP).
- **Note sur les figures :** 10 PNGs sont générés par défaut (Blocs 7.2 et 7.3). Le bloc optionnel 7.3bis (`fig_recap_chiffres_cles.png`) nécessite d'ajouter les clés correspondantes à `HANK_V17['critical']` dans le bloc 6.3 avant exécution.

---

## 8. Structure du Dépôt

```text
phi-hank-france/
├── README.md (English version)
├── README.fr.md (Version française)
├── RESUME_EXECUTIF.md
├── ECONOMIC_ARCHITECTURE_NOTE.md
├── Economic_Architecture_Note.pdf
├── V18_phi.ipynb (Notebook principal v18)
├── requirements.txt
├── figures V18/ (10 PNGs générés par défaut)
├── results V18/ (Pickles, JSON, CSV)
└── LICENSE (MIT)
9. Installation
bash
git clone https://github.com/sebastien-edl/phi-hank-france.git
cd phi-hank-france
pip install -r requirements.txt
jupyter notebook V18_phi.ipynb
10. Un Appel à la Communauté Scientifique
Je ne suis pas un économiste de formation. J'ai codé cette vision avec mes moyens, en apprenant Python et le Sequence-Space Jacobian. Mon code est probablement imparfait, mes hypothèses sont discutables, et j'assume ces limites.

Mon but n'est pas de vous convaincre que j'ai trouvé la vérité. Mon but est de mettre ces briques entre vos mains. Le code est ouvert sur GitHub : testez-le, cassez-le, améliorez-le. Si l'idée est fausse, prouvez-le. Si elle est bonne, poussez-la au plus profond de la modélisation.

AI Disclosure
L'auteur a utilisé des assistants IA (notamment pour la génération de code Python et l'aide à la rédaction) dans la préparation de ce travail. Tous les résultats numériques ont été vérifiés, recalculés et validés par l'auteur. L'auteur assume l'entière responsabilité du contenu et des éventuelles erreurs restantes.

Licence
Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, de le modifier et de le distribuer, à condition de conserver la mention de copyright originale.
