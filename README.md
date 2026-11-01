# Datacenter Camp Français - Lesquin / Lezennes / Ronchin

Étude d'impact et moyens d'opposition au projet de datacenter sur l'ancien complexe moto (22 ha), secteur de 130 ha à l'interface de Lesquin, Lezennes et Ronchin.

Le dépôt est organisé par catégorie :

- `national/` : cadre national (RTE, RECOUPEMENT, analyses énergétiques, sources nationales)
- `international/` : comparaisons internationales (EU, US, Chine, TFLOPS)
- `datacenter/` : documents généralistes réutilisables, par thème (`conso-electrique/`, `eau/`, `bruit/`, `sources/`)
- `projets/` : un sous-dossier par projet ; ici `projets/MEL-Lezenne-camps-francais/` (documents de travail, sources locales, outils, proposition alternative)

## Documents

| Document | Description |
|----------|-------------|
| [rapport-etude-impact.md](projets/MEL-Lezenne-camps-francais/rapport-etude-impact.md) | Analyse personnelle du projet : contexte, impacts environnementaux, économie, marché bureaux, recommandations |
| [rapport-moyens-opposition.md](projets/MEL-Lezenne-camps-francais/rapport-moyens-opposition.md) | Stratégie d'opposition : argumentaire, leviers réglementaires, contrôle pièces promoteur, actions concrètes |
| [etudes-nappe-craie.md](projets/MEL-Lezenne-camps-francais/etudes-nappe-craie.md) | Études comparatives Grand Stade + Leroy Merlin : preuves hydrologiques, nappe de la Craie, carrières, conformité SDAGE |
| [infrastructure-ia-gpu-souverainete.md](projets/MEL-Lezenne-camps-francais/infrastructure-ia-gpu-souverainete.md) | GPU/RAM/Storage : pénurie, NVIDIA vs Huawei, Cloud Act, souveraineté, puissance calcul/m², cas d'étude infrastructure, scénarios et estimation de capacité |
| [souverainete-numerique.md](projets/MEL-Lezenne-camps-francais/souverainete-numerique.md) | Souveraineté numérique appliquée au projet : cadre juridique (CLOUD Act, FISA, SecNumCloud 3.2, CADA), niveaux d'hébergement 1→4, tests, exigences contractuelles |
| [contentieux-administratif-datacenter.md](projets/MEL-Lezenne-camps-francais/contentieux-administratif-datacenter.md) | Fiches contentieuses : autorisation environnementale, espèces, ICPE, servitude 225 kV, voies de recours, délais |
| [bilan-carbone-productiviste-1.3GW.md](projets/MEL-Lezenne-camps-francais/bilan-carbone-productiviste-1.3GW.md) | Bilan carbone productiviste d'un scénario 1,3 GW IT : électrification, facteurs de charge, réseau, hypothèses |
| [proposition/data-commun-datacenter-ethique-souverain.md](projets/MEL-Lezenne-camps-francais/proposition/data-commun-datacenter-ethique-souverain.md) | Alternative de construction « Data-Commun » : prérequis juridiques, de gouvernance, d'énergie, de site, de matériel et d'exploitation ; points d'incohérence à trancher, jalons go/no-go, checklist |

## Documents généralistes — `datacenter/`

Transposable à d'autres territoires ou projets ; les chiffres du dossier local sont signalés comme tels.

| Fichier | Contenu |
|----------|---------|
| [datacenter/souverainete-numerique-generalites.md](datacenter/souverainete-numerique-generalites.md) | Guide généraliste : 5 couches de souveraineté, niveaux 1→4, 10 tests, cadre juridique (CLOUD Act, SecNumCloud, CADA, RGPD, Data Act, NIS2), panorama des lois nationales |
| [datacenter/conso-electrique/electricite-france-nucleaire.md](datacenter/conso-electrique/electricite-france-nucleaire.md) | Mix électrique français, facteurs de charge, canicule, compensation carbonée |
| [datacenter/eau/projections-canucle-2050-2100.md](datacenter/eau/projections-canucle-2050-2100.md) | Projections de canicules 2050-2100 (contrainte de refroidissement) |
| [datacenter/conso-electrique/optimisation-datacenter-parametres.md](datacenter/conso-electrique/optimisation-datacenter-parametres.md) | Paramètres de dimensionnement et d'optimisation (PUE, WUE, densité) |
| [datacenter/eau/refroidissement.md](datacenter/eau/refroidissement.md) | Alternatives de refroidissement du marché |
| [datacenter/eau/refroidissement-generalisation-300MW.md](datacenter/eau/refroidissement-generalisation-300MW.md) | Généralisation du schéma de refroidissement à un site de base 300 MW |
| [datacenter/conso-electrique/dimensionnement-datacenter-entrainement-frontiere.md](datacenter/conso-electrique/dimensionnement-datacenter-entrainement-frontiere.md) | Dimensionnement pour l'entraînement de modèles de frontière |
| [datacenter/ecarts-annonces-realisite-datacenters.md](datacenter/ecarts-annonces-realisite-datacenters.md) | Écarts entre annonces et réalité : eau, électricité, emplois, bruit |
| [datacenter/nuisances-datacenter-11-axes.md](datacenter/nuisances-datacenter-11-axes.md) | Les 11 nuisances d'un datacenter (axes d'opposition) |
| [datacenter/bruit/NuisancesSonores.md](datacenter/bruit/NuisancesSonores.md) | Base documentaire nuisances sonores |
| [datacenter/DATACENTER.md](datacenter/DATACENTER.md) | Exemple de référence : Google Saint-Ghislain (EUW1) |
| [national/sources_backbones_datacenters.md](national/sources_backbones_datacenters.md) | Répertoire des sources et cartographies pour le déploiement de datacenters en France |
| [projets/MEL-Lezenne-camps-francais/rapport-etude-impact-LIEN_CORRIGE.md](projets/MEL-Lezenne-camps-francais/rapport-etude-impact-LIEN_CORRIGE.md) | Version antérieure du rapport d'impact (lien corrigé) — conservée pour l'historique |

### Comparaisons internationales — `international/`

| Fichier | Contenu |
|----------|---------|
| [national/RECENSEMENT.md](national/RECENSEMENT.md) | Recensement des projets de data centers en France (2026) |
| [international/EU_DC_recensement.md](international/EU_DC_recensement.md) | Data centers en Europe — recensement existant (+ `EU_datacenters_existant.csv`) |
| [international/US_DC_recensement.md](international/US_DC_recensement.md) | Data centers aux États-Unis (+ `US_datacenters_existant.csv`) |
| [international/China_DC_recensement.md](international/China_DC_recensement.md) | Data centers en Chine (+ `China_datacenters_existant.csv`) |
| [international/TFLOPS_REFERENCE.md](international/TFLOPS_REFERENCE.md) | Référence de conversion MW → TFLOPS/GFLOPS |
| [international/TFLOPS_SYNTHESIS.md](international/TFLOPS_SYNTHESIS.md) | Synthèse TFLOPS → GFLOPS, datacenters mondiaux |
| [international/GLOSSAIRE_IA.md](international/GLOSSAIRE_IA.md) | Glossaire IA / data centers / HPC |

### Cadre national — `national/`

| Fichier | Contenu |
|----------|---------|
| [national/RECOUPEMENT.md](national/RECOUPEMENT.md) | Tableau de recoupement des projets data center en France (+ `projets_dc_france.csv` / `.json`) |
| [national/ANALYSE_ENERGETIQUE.md](national/ANALYSE_ENERGETIQUE.md) | Analyse énergétique : data center vs électrification vs production française |
| [national/INVESTISSEMENTS_2023_2026.md](national/INVESTISSEMENTS_2023_2026.md) | Chronologie des investissements data center en France (2023-2026) |
| [national/GLOSSAIRE_VIEILLISSEMENT_CUVE.md](national/GLOSSAIRE_VIEILLISSEMENT_CUVE.md) | Glossaire technique : vieillissement des cuves de réacteurs nucléaires |
| [national/sources/README.md](national/sources/README.md) | Index des sources nationales (RTE, Enedis, SDES, CRE, LBNL, IAEA, ASNR) — 91 Mo |

## Santé — `datacenter/bruit/`

| Fichier | Contenu |
|----------|---------|
| [datacenter/bruit/infrasons-sante.md](datacenter/bruit/infrasons-sante.md) | Infrasons et santé : synthèse sourcée |
| [datacenter/bruit/nuisances-sonores-sante.md](datacenter/bruit/nuisances-sonores-sante.md) | Nuisances sonores et santé : synthèse sourcée |

## Outils

| Fichier | Contenu |
|----------|---------|
| [outils/calculettes.html](projets/MEL-Lezenne-camps-francais/outils/calculettes.html) | Calculettes interactives : atténuation du bruit et outils d'étude du site |

## Sources

### Sources locales — `projets/MEL-Lezenne-camps-francais/sources/` (90 Mo)

Copies de travail des pièces citées (HTML brut + version Markdown retravaillée) et PDF.

| Type | Fichiers |
|------|----------|
| Textes (`.md` retravaillés + `.html` bruts) | [communique-press-mel-concertation](projets/MEL-Lezenne-camps-francais/sources/textes/communique-press-mel-concertation.md) · [mel-communique-concertation-2025](projets/MEL-Lezenne-camps-francais/sources/textes/mel-communique-concertation-2025.md) · [registre-numerique-complexe-moto](projets/MEL-Lezenne-camps-francais/sources/textes/registre-numerique-complexe-moto.md) · [ronchin-concertation-camp-francais](projets/MEL-Lezenne-camps-francais/sources/textes/ronchin-concertation-camp-francais.md) · [ronchin-carrieres-souterraines](projets/MEL-Lezenne-camps-francais/sources/textes/ronchin-carrieres-souterraines.md) · [hellemmes-proteger-chiropteres](projets/MEL-Lezenne-camps-francais/sources/textes/hellemmes-proteger-chiropteres.md) · [murin-daubenton-lille-nature](projets/MEL-Lezenne-camps-francais/sources/textes/murin-daubenton-lille-nature.md) · [picardie-nature-chiropteres-catiches-mel](projets/MEL-Lezenne-camps-francais/sources/textes/picardie-nature-chiropteres-catiches-mel.md) · [piezometrie-bss000bfvm-lille](projets/MEL-Lezenne-camps-francais/sources/textes/piezometrie-bss000bfvm-lille.md) |
| PDF | `avis-cnpn-bruges-equinix`, `avis-mrae-pennes-mirabeau-datacenter`, `barometre-ey-france-datacenter-2025`, `bilan-plan-relance-chiros-cmnf`, `brgm-nappe-avril-2026`, `brgm-rp60217-modele-nappe-craie`, `brgm-rp71378-hydro-craie-sud-lille`, `guide-chiropteres-batiments-gepma`, `LaRecherche-Jui-Sep-2026-Le Son-Bruit environnemental`, `livret-chauves-souris-commune-fne`, `mel-deliberation-golf-interet-metropolitain`, `observatoire-emploi-infra-numeriques-2030`, `plan-chiroptere-mel`, `univ-lille-remontees-nappe-craie-bassin-minier` |
| Images | `foret-datacenter.png`, `murin-daubenton.jpg`, `satellite-moto.png`, `satellite-moto_IR.png` |

> `datacenter/sources/` est un **miroir partiel et périmé** (22 Mo, PDF + images + HTML) : utiliser `projets/MEL-Lezenne-camps-francais/sources/` et `national/sources/`.


### Textes officiels

| Document | Lien |
|----------|------|
| Communiqué de presse MEL - Concertation | [lillemetropole.fr](https://www.lillemetropole.fr/communique-de-presse/camp-francais-centre-equestre-golf-complexe-moto-la-metropole-engage-une) |
| Registre numérique - Secteur complexe moto | [registre-numerique.fr](https://www.registre-numerique.fr/secteur-complexe-moto) |
| Fiche Murin de Daubenton - Ville de Lille | [lille.fr](https://www.lille.fr/Nature-a-Lille/Le-patrimoine-naturel/Le-patrimoine-lillois-et-ses-especes-locales/Le-murin-de-daubenton) |
| Protéger les chiroptères - Hellemmes | [hellemmes.fr](https://www.hellemmes.fr/Vivre-a-Hellemmes/Cadre-de-vie/Nature-en-ville/Les-animaux-en-ville/Les-animaux-sauvages-en-ville/Proteger-les-chiropteres) |
| Chiroptères catiches MEL - Picardie Nature | [picardie-nature.org](http://www.picardie-nature.org/protection-de-la-faune-sauvage/protection-et-cohabitation-avec/le-plan-regional-d-actions-en/les-actualites-du-plan-regional-d/article/preservation-des-chiropteres-dans) |

### PDF

| Document | Lien |
|----------|------|
| Baromètre EY / France Datacenter 2025 | [cner-france.com](https://www.francedatacenter.com/wp-content/uploads/ressources/pfwgk7ynxi/Etude_EY_France_Datacenter_2025_VF.pdf) |
| Avis MRAe - Datacenter Pennes-Mirabeau | [bouches-du-rhone.gouv.fr](https://www.bouches-du-rhone.gouv.fr/contenu/telechargement/61688/434897/file/AvisMRAe_PennesMirabeau13_P_ICPE_Datacenter.pdf) |
| Avis CNPN - Datacenter Equinix Bruges | [nouvelle-aquitaine.gouv.fr](https://www.nouvelle-aquitaine.developpement-durable.gouv.fr/IMG/pdf/urbanisation_datacenter__equinix_bruges.pdf) |
| Guide chiroptères bâtiments - GEPMA | [gepma.org](https://gepma.org/wp-content/uploads/2024/12/guidechiropteresbatiments2023.pdf) |
| Chauves-souris et communes - FNE | [parcduverdon.fr](https://www.parcduverdon.fr/wp-content/uploads/2025/11/2023_Livret_proteger-chiros-dans-sa-commune_FNE-GCP.pdf) |
| Observatoire emploi infra numériques 2030 | [observatoires.afdas.com](https://observatoires.afdas.com/sites/default/files/document-ressource/EDEC_Infrastructures_numeriques_Emploi_Competences_Infographie_0.pdf) |
| Présentation chiroptère rue verte | [lillemetropole.fr](https://participation.lillemetropole.fr/fi/hHODTjaSGs6/4SaAyL3D9GgGd/13a42459e8087e77736d7a9cd428780c.pdf) |
| Plan relance chiroptères - CMNF | [cmnf.fr](https://www.cmnf.fr/fichiers/docs/bilan-plan-relance-chiros.pdf) |

### Marché bureaux

| Source | Lien |
|--------|------|
| JLL - Marché locatif bureaux Lille T2 2026 | [jll.com](https://www.jll.com/fr-fr/insights/market-dynamics/lille-office-leasing) |
| CBRE - France Bureaux Lille T4 2025 | [cbre.fr](https://www.cbre.fr/insights/figures/france-bureaux-lille-figures-t4-2025) |
| Le Journal des Entreprises - Vacance Lille | [lejournaldesentreprises.com](https://www.lejournaldesentreprises.com/article/lille-le-marche-de-limmobilier-dentreprise-sur-une-pente-inquietante-selon-cbre-2142826) |
| 20 Minutes - Datacenters et emplois | [20minutes.fr](https://www.20minutes.fr/economie/4227404-20260609-data-centers-france-dizaines-milliards-investissements-combien-emplois) |

### Réglementation

| Texte | Lien |
|-------|------|
| Art. L.411-1 - Protection stricte espèces | [Légifrance](https://www.legifrance.gouv.fr/codes/article_lc/LEGIARTI000033035411) |
| Art. L.411-2 - Dérogation espèces protégées | [Légifrance](https://www.legifrance.gouv.fr/codes/id/LEGIARTI000054715973/2026-09-06?isSuggest=true) |
| Art. L.103-2 - Concertation préalable | [Légifrance](https://www.legifrance.gouv.fr/codes/id/LEGIARTI000052866507/2026-09-06?isSuggest=true) |
| Art. R.122-2 - Évaluation environnementale | [Légifrance](https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006074220/LEGISCTA000006176674/) |
| Directive Habitats 92/43/CEE | [EUR-Lex](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000000339498) |

### Études hydrologiques (nappe de la Craie)

| Document | Lien |
|----------|------|
| Fiche Infosols BRGM - Grand Stade | [fiches-risques.brgm.fr](https://fiches-risques.brgm.fr/georisques/infosols/classification/SSP00034450101) |
| Étude d'impact Borne de l'Espoir (KALIÈS) | [docslib.org](https://docslib.org/doc/408207/etude-dimpact-borne-de-lespoir) |
| BRGM - Impact urbanisation champs captants | [infoterre.brgm.fr](http://infoterre.brgm.fr/rapports/RP-65412-FR.pdf) |
| BRGM - Pollution nappe craie sud Lille | [infoterre.brgm.fr](http://infoterre.brgm.fr/rapports/RP-52215-FR.pdf) |
| INERIS - Guide remblayage carrières souterraines | [ineris.fr](https://www.ineris.fr/sites/default/files/contribution/Documents/Ineris-206842-2735434-Guide%20remblayage%20carri%C3%A8res%20sout.%20en%20exploitation%20v2.pdf) |
| Recours Nord Écologie - Stade Lille | [batiweb.com](https://www.batiweb.com/actualites/collectivites-territoriales/stade-pierre-mauroy-a-lille-nouveau-recours-en-justice-d-une-association-ecologiste-24195) |
| Mediapart - Arrangements Eiffage | [mediapart.fr](https://www.mediapart.fr/journal/france/020414/stade-de-lille-les-arrangements-d-eiffage-avec-l-environnement) |
| Avis services État - Grand Stade | [nongrandstade.free.fr](http://nonaugrandstade.free.fr/lettrepref.php) |
| La Gazette - Chantier Borne de l'Espoir | [lagazettefrance.fr](https://www.lagazettefrance.fr/article/hope-26-000-m2-pour-redynamiser-la-borne-de-l-espoir) |

### Souveraineté / GPU / Infrastructure IA

| Document | Lien |
|----------|------|
| NVIDIA GPU Shortage 2026 | [neuralwired.com](https://neuralwired.com/2026/05/30/nvidia-gpu-shortage-2026-ai-compute/) |
| GPU Supply Chain 2026 (CoWoS, HBM) | [sourcebyspec.com](https://www.sourcebyspec.com/news/gpu-supply-chain-2026-cowos-hbm-and-wafer-bottlenecks-reshape-sourcing.html) |
| Kimi K3 - GitHub officiel | [github.com/MoonshotAI/Kimi-K3](https://github.com/MoonshotAI/Kimi-K3) |
| Kimi K3 GPU Requirements | [packet.ai](https://packet.ai/blog/moonshot-kimi-k3-gpu-requirements) |
| Kimi K3 - Lambda Labs | [lambda.ai](https://lambda.ai/inference-models/moonshotai/kimi-k3) |
| Huawei Ascend 910C vs NVIDIA | [cfr.org](https://www.cfr.org/articles/chinas-ai-chip-deficit-why-huawei-cant-catch-nvidia-and-us-export-controls-should-remain) |
| Ascend 910C benchmarks | [awesomeagents.ai](https://awesomeagents.ai/hardware/huawei-ascend-910c/) |
| CLOUD Act et souveraineté | [bontrain.fr](https://bontrain.fr/ressources/cloud-act-donnees-europeennes) |
| 4 niveaux souveraineté cloud | [fromeuropewithlove.eu](https://www.fromeuropewithlove.eu/fr/blog/quatre-niveaux-souverainete-cloud-guide-ctos-europeens) |
| CADA - Cloud & AI Development Act | [genee.tech](https://www.genee.tech/blog/cloud-ai-development-act-cada-ue-data-centers-souverainete-aout-2026) |
| Scaleway GPU instances | [scaleway.com](https://www.scaleway.com/en/gpu-instances/) |
| OVHcloud - Cloud souverain | [corporate.ovhcloud.com](https://corporate.ovhcloud.com/en/newsroom/news/ovhcloud-deep-clever-cloud-consortium/) |
| Cloud Act vs FISA | [parlons.cloud](https://www.parlons.cloud/cloud-act-fisa-et-lillusion-du-datacenter-en-france/) |

### État des liens

Vérifié le 21/10/2026 : **41 des 44 liens externes** répondent en HTTP 200, les **45 liens internes** du dépôt sont valides.

Trois liens ne répondent pas au contrôle automatisé (pages probablement accessibles dans un navigateur) :

| Lien (tableau d'origine) | Réponse | Cause probable |
|------|---------|----------------|
| [cbre.fr — France Bureaux Lille T4 2025](https://www.cbre.fr/insights/figures/france-bureaux-lille-figures-t4-2025) | 403 | protection anti-robot |
| [lille.fr — murin de Daubenton](https://www.lille.fr/Nature-a-Lille/Le-patrimoine-naturel/Le-patrimoine-lillois-et-ses-especes-locales/Le-murin-de-daubenton) | 503 | erreur serveur temporaire |
| [hellemmes.fr — protéger les chiroptères](https://www.hellemmes.fr/Vivre-a-Hellemmes/Cadre-de-vie/Nature-en-ville/Les-animaux-en-ville/Les-animaux-sauvages-en-ville/Proteger-les-chiropteres) | 503 | erreur serveur temporaire |

Les deux pages lilloises sont archivées localement dans `projets/MEL-Lezenne-camps-francais/sources/textes/` ; le reste du dossier est utilisable hors ligne.
