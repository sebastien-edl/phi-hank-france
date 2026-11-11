# 📝 Résumé Exécutif : Le Dispositif Φ
# Executive Summary: The Φ Device

**Un stabilisateur automatique ciblé sur la demande solvable**
**A Targeted Automatic Stabilizer for Solvable Demand**

Sébastien Delestre — Chercheur indépendant / Independent Researcher
ORCID: 0009-0005-4654-5107
Octobre 2026 / October 2026

🇫🇷 [Lire en Français](#-version-française) | 🇬🇧 [Read in English](#-english-version)

---

## 🇫🇷 Version Française

### 1. Le Problème : L'angle mort institutionnel
L'architecture macroéconomique moderne dispose d'institutions dédiées à la stabilité monétaire (banques centrales), à la stabilité financière (ACPR), et à la concurrence. **Aucune institution, cependant, n'a explicitement pour mandat de réguler la *demande solvable*** — le pouvoir d'achat effectivement disponible pour convertir des besoins en transactions marchandes.

Le débat public reste binaire : l'offre ou la demande. Aucun des deux camps ne propose d'institution permanente et fondée sur des règles pour réguler ce moteur. C'est cet angle mort que le dispositif Φ propose de combler.

### 2. La Solution : Φ, un stabilisateur ciblé
Φ est un stabilisateur automatique qui verse une prime horaire aux travailleurs modestes (13 millions de bénéficiaires, ciblés sur les six premiers déciles).

*   **Pourquoi eux ?** Parce que leur propension marginale à consommer (PMC) est de **78,17 %**. Chaque euro transféré génère une forte réponse de consommation.
*   **Comment est-il financé ?** Par la redirection de **32 milliards d'euros** de niches fiscales existantes. **Ce n'est pas un nouvel impôt**, ni de la dette supplémentaire. C'est une réallocation de ressources vers des agents à forte PMC.
*   **Est-il inflationniste ?** Non. Le dispositif est contracyclique : la prime baisse automatiquement quand l'inflation monte.

### 3. Les Chiffres Clés (Modèle HANK calibré France)

Testé dans un modèle HANK (*Heterogeneous Agent New Keynesian*) à 10 états, validé par **146 indicateurs** et **6 Checkpoints**, Φ produit les résultats suivants :

| Indicateur | Valeur | Interprétation |
| :--- | :--- | :--- |
| **Multiplicateur budgétaire (8T)** | **0,775** | Dans la fourchette empirique [0,5 ; 1,5] (Auerbach & Gorodnichenko 2012 ; Ramey & Zubairy 2018). |
| **Emplois créés — canal Φ** | 75,1k ETP | Transfert direct. |
| **Emplois créés — canal bc** | 293,6k ETP | Baisse de charges. |
| **Emplois créés — total** | **369k ETP** | Estimation centrale (fourchette : 108k à 741k selon `elasticite_bc` ∈ [0,05 ; 0,50]). |
| **Solde net de l'État** | **+9,75 Md€/an** | Le dispositif s'autofinance grâce aux retours fiscaux. |
| **Inflation induite** | **+0,197 %** | Bien en dessous du seuil de surchauffe (2 %). |
| **Chômage structurel (steady-state)** | **6,98 % → 6,73 %** | Réduction de 0,25 point (comparaison de steady states). |

> **Note :** La fourchette 108k–741k correspond aux valeurs de robustesse de `elasticite_bc` (0,05 et 0,50). La valeur centrale (0,15) est **369k**.

### 4. L'Extension Two-Asset (Résultats Complémentaires)

Le modèle Two-Asset (Kaplan-Moll-Violante, 2018) introduit une friction de vente (le « kink ») sur l'actif illiquide. Il produit un multiplicateur structurellement plus bas (**0,199** avec financement par niches), mais révèle **trois résultats inédits** :

1. **Le kink est neutre pour les niches** : μ = 0,199 avec kink vs 0,194 sans (Δ = 0,0055).
2. **Le kink est crucial pour le lump-sum** : μ = +0,044 avec kink vs −0,078 sans. Sans friction, les ménages ricardiens sur-réagissent.
3. **Courbe en cloche** : le multiplicateur atteint un optimum économique à χ₀,sell ≈ 0,10.

### 5. Les Limites (Transparence)

Ce travail est un *draft préliminaire*. Il ne prétend pas détenir la vérité. Les limites sont documentées explicitement :

*   **Modèle à un actif** : Le modèle HANK sous-estime la part de ménages *hand-to-mouth* (26,94 % contre 30-35 % selon l'INSEE). Les résultats sont donc des bornes inférieures conservatrices.
*   **Coefficients calibrés** : L'élasticité d'embauche (**4,0**) et l'élasticité de la baisse de charges (**0,15**) sont des choix méthodologiques, non des estimations économétriques. Le taux de retour fiscal agrégé (30 %) et le taux du scénario central (29,75 %) sont également des choix.
*   **Inflation post-traitée** : L'inflation est calculée en post-traitement (π = κŷ), pas simulée de manière endogène.
*   **Chômage en steady-state uniquement** : Les chiffres de chômage sont des comparaisons de steady states (pré-Φ vs post-Φ), pas des trajectoires de transition. La trajectoire complète *u_t* est renvoyée à une version ultérieure.

### 6. Un Appel à la Communauté Scientifique

Je ne suis pas un économiste de formation. J'ai codé cette vision avec mes moyens, en apprenant Python et le *Sequence-Space Jacobian*. Mon code est probablement imparfait, mes hypothèses sont discutables, et j'assume ces limites.

Mon but n'est pas de vous convaincre que j'ai trouvé la vérité. Mon but est de mettre ces briques entre vos mains. **Le code est ouvert sur GitHub** : testez-le, cassez-le, améliorez-le. Si l'idée est fausse, prouvez-le. Si elle est bonne, poussez-la au plus profond de la modélisation.

---

## 🇬🇧 English Version

### 1. The Problem: The Institutional Blind Spot
Modern macroeconomic architecture has institutions dedicated to monetary stability (central banks), financial stability (regulators), and competition. **No institution, however, has an explicit mandate to regulate *solvable demand*** — the purchasing power effectively available to convert needs into market transactions.

The public debate remains binary: supply or demand. Neither camp proposes a permanent, rules-based institution to regulate this engine. It is this blind spot that the Φ device proposes to fill.

### 2. The Solution: Φ, a Targeted Stabilizer
Φ is an automatic stabilizer that pays an hourly subsidy to modest workers (13 million beneficiaries, targeted at the first six deciles).

*   **Why them?** Because their marginal propensity to consume (MPC) is **78.17%**. Every euro transferred generates a strong consumption response.
*   **How is it funded?** By redirecting **€32 billion** of existing tax expenditures. **This is not a new tax**, nor additional debt. It is a reallocation of resources toward agents with a high MPC.
*   **Is it inflationary?** No. The device is countercyclical: the subsidy automatically decreases when inflation rises.

### 3. The Key Figures (Calibrated HANK Model for France)

Tested in a 10-state HANK (Heterogeneous Agent New Keynesian) model, validated by **146 indicators** and **6 Checkpoints**, Φ produces the following results:

| Indicator | Value | Interpretation |
| :--- | :--- | :--- |
| **Fiscal Multiplier (8Q)** | **0.775** | Within the empirical range [0.5; 1.5] (Auerbach & Gorodnichenko 2012; Ramey & Zubairy 2018). |
| **Jobs created — Φ channel** | 75.1k FTE | Direct transfer. |
| **Jobs created — bc channel** | 293.6k FTE | Payroll tax cut. |
| **Jobs created — total** | **369k FTE** | Central estimate (range: 108k to 741k depending on `elasticite_bc` ∈ [0.05; 0.50]). |
| **Net government balance** | **+€9.75 bn/year** | The device self-finances through tax returns. |
| **Induced inflation** | **+0.197%** | Well below the overheating threshold (2%). |
| **Structural unemployment (steady-state)** | **6.98% → 6.73%** | A reduction of 0.25 percentage points (steady-state comparison). |

> **Note:** The range 108k–741k corresponds to robustness values of `elasticite_bc` (0.05 and 0.50). The central value (0.15) is **369k**.

### 4. The Two-Asset Extension (Complementary Results)

The Two-Asset model (Kaplan-Moll-Violante, 2018) introduces a selling friction (the "kink") on the illiquid asset. It produces a structurally lower multiplier (**0.199** with tax expenditure financing), but reveals **three novel observations**:

1. **The kink is neutral for niches**: μ = 0.199 with kink vs 0.194 without (Δ = 0.0055).
2. **The kink is crucial for lump-sum**: μ = +0.044 with kink vs −0.078 without. Without friction, Ricardian households overreact.
3. **Bell curve**: the multiplier peaks at an economic optimum at χ₀,sell ≈ 0.10.

### 5. Limitations (Transparency)

This work is a *preliminary draft*. It does not claim to hold the truth. Limitations are explicitly documented:

*   **One-asset model**: The model underestimates the share of hand-to-mouth households (26.94% vs. 30-35% according to INSEE). Results are therefore conservative lower bounds.
*   **Calibrated coefficients**: The hiring elasticity (**4.0**) and the payroll tax cut elasticity (**0.15**) are methodological choices, not econometric estimates. The aggregate fiscal return rate (30%) and the central scenario rate (29.75%) are also choices.
*   **Post-processed inflation**: Inflation is calculated in post-processing (π = κŷ), not simulated endogenously.
*   **Steady-state unemployment only**: Unemployment figures are steady-state comparisons (pre-Φ vs post-Φ), not transitional paths. The full *u_t* trajectory is left to a subsequent version.

### 6. A Call to the Scientific Community

I am not a formally trained economist. I coded this vision with the means at my disposal, learning Python and the Sequence-Space Jacobian. My code is likely imperfect, my assumptions are debatable, and I acknowledge these limitations.

My goal is not to convince you that I have found the truth. My goal is to put these building blocks in your hands. **The code is open on GitHub**: test it, break it, improve it. If the idea is wrong, prove it. If it is good, push it to the deepest levels of modeling.

---

[Back to top / Retour en haut](#-résumé-exécutif--le-dispositif-φ)
