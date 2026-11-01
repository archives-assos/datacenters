# Data-Commun — Proposition de datacenter éthique et souverain

## Prérequis de construction

> **Statut du document** — Document de travail (proposition). Rédigé le 21/10/2026. Il décrit les **prérequis** à remplir avant qu'un datacenter « éthique et souverain » de type *Data-Commun* puisse être décidé, financé et construit. Il ne vaut ni étude de faisabilité, ni avis juridique, ni note de calcul.
>
> **Position** — Ce document est une **alternative de construction** au scénario « datacenter unique de grande puissance » : il énonce, en amont, les conditions à réunir pour qu'un tel ouvrage soit possible, financable et défendable. Cadre de référence : `datacenter/souverainete-numerique-generalites.md` (5 couches de souveraineté, niveaux 1→4, grille d'évaluation).
>
> **Portée** — La proposition est **transposable** : principes, seuils et clauses valent pour tout territoire ; seuls le dimensionnement, les sites et les contreparties locales sont spécifiques.
>
> **Convention** — Les éléments marqués 🔴 sont des **incohérences internes de la spécification initiale** (section 9) : ils doivent être tranchés *avant* toute décision, faute de quoi le projet est intenable sur le papier.

---

## Lexique

*(placé en tête de document : les sigles et termes ci-dessous sont employés dans la suite sans redéfinition)*

### Sigles et acronymes

| Sigle | Signification | Précision utile | Vois § |
|---|---|---|---|
| ADEME | Agence de la transition écologique | Financement et appui méthodologique (électronique, chaleur, circularité) | §8 |
| AI Act | Règlement européen (UE) 2024/1689 sur l'intelligence artificielle | Obligations GPAI depuis le 02/08/2025 ; dispositions high-risk depuis le 02/08/2026 | §3.4 |
| ANSSI | Agence nationale de la sécurité des systèmes d'information | Auditeur et éditeur du référentiel SecNumCloud | §3.3 |
| ASI | Alimentation sans interruption | Onduleurs + batteries de secours ; conditionne la rubrique ICPE 2925 | §4.4, §4.5 |
| BE | Bureau d'études | Responsable de la note d'opposabilité et de l'étude de sols | §4.5, §12 |
| CAPEX / OPEX | Investissements / charges d'exploitation | Deux postes dominants : le raccordement (CAPEX) et l'astreinte (OPEX) | §8.2 |
| CADA | Cloud and AI Development Act (UE) | En vigueur 04/08/2026 ; guichet unique et permis accéléré, sans dispense d'étude d'impact | §3.4 |
| CLOUD Act | *Clarifying Lawful Overseas Use of Data Act* (US, 2018) | Impose aux sociétés US de remettre les données sur mandat US, où qu'elles soient stockées | §3.3, §6.1 |
| CO₂e | Équivalent dioxyde de carbone | Unité de comptabilité carbone (CO₂, CH₄, N₂O ramenés au CO₂) | §5.1 |
| COP | Coefficient de performance | Rapport chaleur produite / électricité consommée par une pompe à chaleur | §5.2 |
| CPU / GPU | Processeur / processeur graphique | Le CPU exécute, le GPU parallélise ; l'IA exige des GPU | §6.2, §6.3 |
| CUE | Carbon Usage Effectiveness | Kilogrammes de CO₂e par kWh IT : le PUE sans angle carbone | §5.1 |
| DARE | *Digital Autonomy with RISC-V in Europe* | Programme européen de souveraineté sur RISC-V | §6.3 |
| DEAL | Direction de l'environnement, de l'aménagement et du logement | Instruction de l'autorisation environnementale | §4.5 |
| DPO | Délégué à la protection des données | Responsable RGPD de la SCIC | §7, §11 |
| EPI | European Processor Initiative | Consortium ayant produit la puce SiPearl Rhea1 | §6.3 |
| ERP | Établissement recevant du public | Piscine, mairie, salle de sport : statut des sites Edge | §4.5 |
| ESRIS | État des risques industriels (document d'étude de sols) | À produire avant toute cession de terrain pollue | §9-E |
| FISA 702 | Section 702 du *Foreign Intelligence Surveillance Act* (US) | Surveillance sans notification de personnes hors US | §3.3 |
| FRR / FRRouting | Suite logicielle de routage open source | Alternative européenne au routage propriétaire | §6.1, §6.5 |
| GPAI | *General Purpose AI* / IA à usage général | Catégorie de l'AI Act Triggerant des obligations de documentation et de transparence | §3.4 |
| HBM | *High Bandwidth Memory* | Mémoire haute bande passante des GPU d'IA ; approvisionnement tendu, non européenne | §6.3 |
| HDS | Hébergeur de données de santé | Certification française, distincte de SecNumCloud | §3.4 |
| IaaS / PaaS | Infrastructure / plateforme as a service | Couches exploitées par le cloudeur au-dessus de l'infrastructure physique | §1.1, §3.2 |
| ICPE | Installation classée pour la protection de l'environnement (ex SEVESO) | Rubrique 3110 (groupes électrogènes > 50 MW), 2925 (accumulateurs) | §4.5 |
| ISA | *Instruction Set Architecture* | Jeu d'instructions du processeur ; openness = droit de modifier et réimplémenter | §6.3, §9-B |
| KPI | Indicateur clé de performance | Ici : PUE, WUE, CUE, taux de réemploi, taux de chaleur valorisée | §3.5, §12 |
| kW / MW / GW / MVA | Puissance (kW = MW = MVA ≈ à cos φ ≈ 1) | Distinguer la **puissance IT** de la **puissance soutirée** (PUE) | §4.4, §5.1 |
| LOI | Lettre d'intention | Engagement non contractuel d'un client d'ancrage | §8.3, §12 |
| Agglomération | Intercommunalité métropolitaine portant le projet | Territoire de référence : réseaux de chaleur publics, projet de réseau de froid | §5.2 |
| MRAe | Mission régionale d'autorité environnementale | Avis sur l'étude d'impact, l'évaluation environnementale | §4.5 |
| N+1 / redondance | Un élément de secours par composant | Exigence de disponibilité et de continuité (sûreté de fonctionnement) | §6.5, §7 |
| NIS2 / DORA | Directives UE cyber (NIS2) et résilience financière (DORA) | Obligations de notification, de gestion de risque et de tests | §3.4 |
| OCP | Open Compute Project | Référentiels ouverts : serveurs, refroidissement, circularité, CEDaCI | §6.4, §6.5 |
| ONERA | Office national d'études et de recherches aérospatiales | Référentiels français de mesure acoustique et vibratoire | §5.4 |
| PFAS | *Per- and polyfluoroalkyl substances* | Fluides d'immersion fluorés : risque réglementaire européen, exclus du projet | §5.3, §12 |
| PLU | Plan local d'urbanisme | Sertitudes d'inconstructibilité (bandes de lignes HT, zones de risque) | §4.3 |
| PTF | Proposition technique et financière (Enedis/RTE) | Engagement de raccordement : puissance, tension, délai, quote-part | §4.4 |
| PUE / WUE / CUE | Efficacité électrique / hydrique / carbone | PUE = énergie totale ÷ énergie IT ; WUE = litres ÷ kWh IT | §5.1 |
| RISC-V | Jeu d'instructions ouvert et gratuit, géré par une communauté | Ouvert mais immature pour le calcul d'IA à grande échelle | §6.3, §9-B |
| ROCm / HIP | Pile logicielle open source d'AMD (équivalent de CUDA) | Support PyTorch, vLLM, ONNX, Triton ; maturité inégale | §6.2, §9-D |
| RPO / RTO | Perte de données maximale tolérée / durée de reprise | Cibles de continuité : sauvegarde et restauration | §7 |
| RTE / Enedis | Gestionnaire de réseau de transport / de distribution | Interlocuteurs du raccordement et du PTF | §4.4 |
| SAS / SCIC / SEM | Société par actions simplifiée / coopérative d'intérêt collectif / société d'économie mixte | Formes juridiques candidates de la structure porteuse | §3.1 |
| SLA / SLO | Engagement de service contractuel / objectif interne mesuré | Le SLA est opposable ; le SLO est l'instrument de pilotage interne | §7 |
| SREN | Loi « sécuriser et réguler l'espace numérique » (21/05/2024) | Son article 31 fonde l'exigence SecNumCloud pour l'État | §3.3 |
| TWh | Térawattheure | 1 TWh = 1 million de MWh ; ordre de grandeur annuel | §8.2 |
| UALink / RoCE / InfiniBand | Protocoles d'interconnexion multi-GPU | Ethernet ouvert (UALink, RoCE) face au verrou NVLink/InfiniBand | §6.2 |
| XCCL | Bibliothèque de communications collectives multi-GPU (AMD) | Équivalent d'un NCCL pour la pile ROCm | §6.2, §7 |
| ZAC / emprise | Zone d'aménagement concerté / surface occupée | « Zéro artificialisation » = pas d'extension de la surface imperméabilisée | §4.2 |

*(dernière ligne : « zéro artificialisation » = aucune surface nouvelle imperméabilisée)*

### Termes et expressions

| Terme | Définition retenue dans ce document | Vois § |
|---|---|---|
| **Artificialisation** | Transformation d'un sol naturel ou perméable en surface bâtie ou imperméable. « Zéro artificialisation » = réutilisation exclusive de l'emprise existante. | §4.2, §9-E |
| **Catiche** | Vide karstique vertical, naturelle ou d'origine minière, dans le massif crayeux. Propage les vibrations, menace les habitations et les chiroptères. | §4.2, §5.4, §9-F |
| **Chaleur fatale** | Chaleur résiduelle rejetée par les équipements, valorisable en chauffage. Sa valorisation dépend de la **température**, de la **saisonnalité** et du **contrat**, pas du seul volume. | §5.2 |
| **Cloisonnement (des flux)** | Séparation technique et administrative des workloads sensibles et non sensibles, avec clés, accès et journaux distincts. | §3.3.1 |
| **Common numérique** | Ressource ouverte Autoproduite et@gouvernée de façon collective (Wikipédia, OpenStreetMap, jeux de données publics). Client prioritaire de la charte. | §3.5 |
| **Direct-to-chip** | Refroidissement où le fluide froid circule directement dans le processeur (plaque de refroidissement, bobine). Variante sans eau du refroidissement de salle. | §5.1, §5.3 |
| **Edge** | Point de présence de calcul décentralisé, implanté au plus près des usages (sous-sol, parking, piscine). Faible densité, forte contraintes d'intégration. | §0, §4.1 |
| **Friche industrielle** | Site industrielle désaffecté, réutilisable. Atout dificialisation nulle, mais **risque de pollution** et de passif environnemental. | §4.2, §9-E |
| **Go / no-go** | Jalon de décision : on engage l'étape suivante, ou on arrête le projet. Chaque jalon doit avoir des critères **écrits avant** le test. | §10 |
| **Gouvernance (coopérative)** | Organisation des décisions par colleges de votants, avec droit de veto et règles d'affectation des résultats. | §3.1, §3.2 |
| **Grille de souveraineté (5 couches)** | Foncier-bâti-énergie / matériel / logiciel-firmware / opérateur-données / compétences-réversibilité. Le niveau global = **le maillon le plus faible**. | §1.2, §9-A |
| **Immersion (refroidissement)** | Noyage des serveurs dans un fluide diélectrique. Variantes « eau froide » (≤ 40 °C) et « eau chaude » (60–90 °C), cette dernière seule compatible avec un réseau de chaleur à haute température. | §5.2, §5.3 |
| **Karst** | Relief calcaire creusé par l'eau, featuring cavités, catiches et pertes de nappe. Site exclu par le critère de sanctuarisation géologique. | §4.2 |
| **Lock-in (verrouillage)** | Dépendance économique et technique à un fournisseur, à coût de sortie élevé. S'oppose à l'exigence de réversibilité. | §6.1, §9-A |
| **Maillon faible** | Règle : le niveau de souveraineté d'un système est celui de sa couche la plus exposée, pas celui de sa couche la plus flatteuse. | §1.2 |
| **Nappe de la Craie** | Aquifère de la craie (nord de la France), principale nappe d'eau potable de la région : sensible aux remontées de niveau et aux pollutions de surface. | §4.2 |
| **Obsolescence programmée** | Fin de support décidée par le fournisseur (firmware, pièces, mises à jour), rendant l'équipement inutilisable avant son usure physique. | §6.1, §6.4 |
| **Pile logicielle (stack)** | Ensemble des couches logicielles d'un service : OS, hyperviseur, orchestration, stockage, réseau, supervision. | §6.1 |
| **Portabilité** | Capacité à déplacer un workload (modèle, données, code) d'une pile matérielle/logicielle à une autre sans réécriture. C'est l'enjeu ROCm. | §6.2 |
| **Réversibilité** | Capacité documentée et chiffrée de quitter un fournisseur ou une pile, avec export complet (données, images, clés, journaux) et délai d'exercice connu. | §3.2, §6.5 |
| **Réemploi / reconditionnement** | Remise en état d'équipements usagés (serveurs, châssis, alimentations, câblage) pour un second cycle de production, avec garantie, traçabilité et firmware ouvert. | §6.4, §9-G |
| **Tranchée d'atténuation** | Excavation périphérique remplie de matériaux découplants (sable, caoutchouc broyé) pour atténuer la propagation des ondes de sol. Efficace surtout au-dessus de ~10 Hz. | §5.4, §9-F |
| **Vibration de sol (structurelle)** | Transmission par le sol et les fondations des vibrations mécaniques, notamment basse fréquence, perceptibles à plusieurs dizaines de mètres. | §5.4 |
| **WUE = 0** | Cible d'absence d'eau de refroidissement en exploitation. Atteignable en circuit fermé strict ; à tempérer en « WUE_IT < 0,01 L/kWh et zéro m³ prélevé ». | §5.1, §9-D |


---

## 0. Résumé exécutif

**Data-Commun** propose de ne pas construire un giga-datacenter centralisé, mais un **dispositif de calcul réparti à trois étages**, détenu par une **SCIC** (coopérative d'intérêt collectif) et exploité avec un **cloudeur européen qualifié SecNumCloud** sous contrôle technique de la coopérative :

| Échelle | Usage | Site type | Puissance |
|---|---|---|---|
| **Edge** | Inférence courante, services de proximité, caissons *edge* | Bâtiments publics existants (parkings, sous-sols, piscines) | 20–200 kW / site |
| **Inférence régionale** | Inférence industrialisée, service public, santé | Friche industrielle hors zone karstique | 1–5 MW |
| **Entraînement** | Modèles ouverts (échelle Mistral Large) | Friche portuaire/industrielle, hors massifs calcaires | 20–100 MW |

**Les 6 préalableurs bloquants** (section 2) :

1. **Gouvernance** — statuts SCIC, 3 catégories d'associés, autogestion des décisions techniques ; le projet est ingérable sans carte des droits de veto.
2. **Droit** — chaîne de qualification **SecNumCloud 3.2** : la SCIC n'étant pas un fournisseur de cloud, il faut désigner qui est qualifié, et sous quel contrat.
3. **Cohérence matérielle** — l'interdiction « absolue des licences américaines » est **incompatible** avec AMD EPYC, avec SiPearl Rhea (Arm) et avec la quasi-totalité de la chaîne. Elle doit être remplacée par des critères auditables (§9-A).
4. **Énergie** — PUE < 1,15 **et** WUE = 0 **et** chaleur fatale 100 % valorisée ne sont pas simultanés sans arbitrage explicite sur les températures de retour et sur la saisonnalité.
5. **Territoire** — l'exclusion géologique (karst, catiches) et l'interdiction d'artificialisation réduisent le foncier disponible à un jeu restreint : il faut le **sécuriser** (bail, PTF Enedis, réseau de chaleur) avant toute étude de dimensionnement.
6. **Économie** — une SCIC ne vit pas du marché : il faut un **client d'ancrage** (public, université, santé) et un modèle de financement (subventions, contrat de capacité chaleur, tarif préférentiel).

**Conclusion de cadrage** : le projet est **réalisable** au stade Edge et Inférence régionale ; l'étage Entraînement n'est justifié qu'après un **jalon go/no-go technique** (portabilité ROCm + performance + chaleur) et un **jalon financier** (client d'ancrage + capacité d'accélérateurs réservée). Sans ces deux jalons, l'alternative se réduit à une opération de communication.

---

## 1. Objet et périmètre

### 1.1 Ce que Data-Commun est

- Une **infrastructure de calcul distribuée** (Edge + régional + entraînement) sous **gouvernance coopérative** multi-parties prenantes.
- Un **modèle d'exploitation à deux acteurs** : la SCIC possède le foncier, l'énergie, les machines et **décide de la stack** ; le cloudeur EU qualifié opère la couche PaaS/IaaS et met en œuvre les décisions techniques.
- Une **charte d'usage contraignante** : priorité à la recherche publique, la santé, l'enseignement supérieur et les communs numériques ; exclusions contractuelles (minage crypto, trading haute fréquence, surveillance de masse, optimisation fiscale).
- Un standard d'**efficacité et de circularité** opposable par le contrat : PUE, WUE, valorisation de la chaleur, taux de matériel reconditionné, réversibilité.

### 1.2 Ce que Data-Commun n'est pas

| Ce que le discours pourrait laisser croire | Ce que le projet est réellement |
|---|---|
| « Datacenter souverain matériel » | Souveraineté **d'exploitation, de gouvernance et de données**. Le silicium (AMD US, TSMC Taïwan, HBM KR, Arm UK/Japon) reste non européen : voir §9-A et `datacenter/souverainete-numerique-generalites.md` §2 (règle du maillon faible). |
| « Un datacenter » | Trois échelles, trois sites, trois régimes réglementaires, trois modèles économiques. |
| « Zéro impact » | Un impact **différent** : artificialisation nulle, eau de refroidissement nulle, chaleur valorisée, mais **pics de puissance** et **bruit de fond permanent** en zone urbaine dense (Edge). |
| « Alternative au giga-datacenter » | Alternative **partielle** : l'étage Entraînement reste une puissance concentrée, avec les mêmes contraintes de raccordement qu'un site unique : poste 225 kV dédié, **80–150 M€** et **3–5 ans** de délai. |

---

## 2. Synthèse des préalableurs bloquants

| # | Famille | Prérequis bloquant | Preuve exigée avant décision | Section |
|---|---|---|---|---|
| P1 | Gouvernance | SCIC constituée, statuts fixant les colleges de vote, l'autogestion de la société, l'interdiction de sortie du capital | Statuts + immatriculation RCS | §3.1 |
| P2 | Juridique | Chaîne SecNumCloud 3.2 (ou trajectoire datée) et plan de sortie | Contrat + plan de réversibilité | §3.3 |
| P3 | Matériel | Critères de souveraineté auditables remplaçant l'interdiction de nationalité | Grille de 6 critères + audit de chaîne | §9-A |
| P4 | Technique | Portabilité des workloads hors CUDA démontrée sur batterie de référence | Rapport de benchmarks reproductible | §6.2 |
| P5 | Énergie | Contrat de chaleur (température, saisonnalité, prix) signé avec un opérateur de réseau | Convention + étude technico-économique | §5.2 |
| P6 | Site | Bail / convention d'occupation, faisabilité foncière, PTF Enedis | Pièces foncières + PTF | §4.3–4.4 |
| P7 | Autorisations | Faisabilité ICPE / espèces / eau / urbanisme confirmée par un tiers | Note d'opposabilité + saisine DEAL | §4.5 |
| P8 | Modération | Charte d'usage opposable, arbitre, allocation transparente | Règlement + CGU | §3.5 |
| P9 | Économie | Client d'ancrage + plan de financement pluriannuel | LOI + plan de financement | §8 |
| P10 | Compétences | Équipe SRE open source interposée, non 100 % prestataire | Plan de recrutement / convention de formation | §7 |

---

## 3. Prérequis juridiques et de gouvernance

### 3.1 Structure : la SCIC comme forme de propriété (pas comme slogan)

**Ce que la SCIC apporte concrètement** : elle permet d'associer dans un même capital des **collectivités**, des **usagers**, des **scientifiques** et des **salariés**, avec une **obligation statutaire** de non-distribution des résultats (15 % en réserve légale, 50 % du solde en réserve statutaire, soit 57,5 % minimum), et une possible inscription au registre des coopératives.

**Ce qu'il faut savoir avant de choisir la SCIC** (et non un consortium classique) :

| Point | Règle | Conséquence pratique |
|---|---|---|
| Catégories d'associés | **Au moins 3** catégories obligatoires (salariés, bénéficiaires/utilisateurs, autres parties prenantes) | La gouvernance à 1 voix/associé est incompatible avec le multi-usage : prévoir des **collèges de votants** dès les statuts |
| Collectivités publiques | Peuvent être associées, dans la limite de **20 % du capital** au total | Une collectivité ne peut pas **détenir** l'infrastructure ; elle peut être **locataire**, usagère, ou cliente d'ancrage. Chiffrer ce plafond dès le schéma capitalistique |
| Agrément préfectoral | **Supprimé** par la loi n° 2012-387 du 22 mars 2012 | Le « agrément » n'est plus un préalable : ce qui reste, c'est la **justification du caractère d'utilité sociale** (décret n° 2002-241 du 21 février 2002) — nécessaire pour les dispositifs d'aide publics et territoriaux, à instruire |
| Forme | Société **commerciale** (non ESUS) | Fiscalité, commissariat aux comptes, TVA sur les services : à modéliser, l'« utilité sociale » n'est pas une exonération |
| Gouvernance | Pas de SARL de droit privé classique possible (article 1 de la loi 2002-5) | La SCIC est **une** société de droit privé commerciale à finalité d'intérêt collectif : usage à confirmer par un praticien |
| Alternative | SAS coopérative, SEM (société d'économie mixte), consortium public-privé, fondation | Comparer : la SEM autorise une détention publique majoritaire, incompatible avec l'exigence « capital UE, contrôle UE » de SecNumCloud |

> **Prérequis P1** : un avis juridique écrit sur la forme, le plafond de 20 %, la fiscalité et les leviers d'aide. Sans lui, les statuts ne peuvent pas être rédigés et rien ne peut être immatriculé.

### 3.2 Chaîne de contrôle avec le cloudeur

Le modèle « le cloudeur opère, la SCIC gouverne » n'a de valeur que si **les droits de la SCIC sont contractuellement réels**. Les clauses minimales à obtenir (à annexer au contrat de capacité) :

| Clause | Contenu minimal | Pourquoi |
|---|---|---|
| Contrôle de la stack | La SCIC **arrête** les versions OS / hyperviseur / firmware / ROCm retenues ; le cloudeur ne peut pas imposer de mise à jour unilatéralement | Sans cela, le « contrôle technologique » est nominal |
| Non-extraterritorialité | Le cloudeur ne peut être placé sous contrôle extra-UE ni accepter de clause d'audit extra-UE ; notification de tout changement de contrôle | C'est le cœur SecNumCloud et CLOUD Act |
| Support et supervision | Astreinte, supervision et support **physiquement en UE** ; interdiction de sous-traitance hors UE | Couches 4-5 de la grille de souveraineté |
| Audibilité | Audit ANSSI / AFNOR, pentest, reporting, accès de la SCIC aux journaux d'exploitation | §3.3 |
| Réversibilité | Format de données documenté, export complet (VM, images, données, clés), plan de sortie chiffré, délai d'exercice | Coût de sortie explicité et provisionné |
| Non-conformité | Sanctions financières en cas d'écart aux indicateurs (PUE, WUE, chaleur, taux de reconditionnement) | Sans pénalité, un indicateur est un vœu |
| Gouvernance de la roadmap | Comité technique conjoint (SCIC + cloudeur + 2 représentants des parties prenantes + 2 chercheurs) avec compte rendu public | Évite la dérive vers la roadmap du fournisseur |
| Sortie | Conditions de sortie anticipée sans pénalité si non-conformité grave, et transfert des machines à la SCIC | Réalisabilité : la SCIC n'a ni les compétences ni les équipes de migration au départ |

### 3.3 SecNumCloud 3.2 : qui est qualifié, et pourquoi c'est un préalable

**Rappel de l'état du droit** (état 2026) : le référentiel **SecNumCloud v3.2** est celui de l'ANSSI (8 mars 2022). Il a cessé d'être une simple recommandation : la **loi SREN du 21 mai 2024 (art. 31)**, le **décret n° 2026-272 du 14 avril 2026** et l'**arrêté du 12 août 2026** (JO du 14/08/2026, entrée en vigueur le 15/08/2026) en font le cadre **exigible** pour les administrations de l'État, leurs opérateurs et certains groupements d'intérêt public qui confient des données **particulièrement sensibles** à un cloud commercial. Une dizaine d'offres étaient qualifiées en 2026 ; la liste ANSSI fait foi.

**Conséquence pour Data-Commun** : la qualification porte sur **le service cloud et son fournisseur**, pas sur un bâtiment ni sur un exploitant de site. Trois architectures possibles :

| Option | Description | Effort | Limite |
|---|---|---|---|
| **A — qualification par le cloudeur** | Le cloudeur fournit les workloads sensibles depuis son offre qualifiée ; le site Data-Commun n'héberge que du **non sensible** | Faible | La souveraineté du projet tient alors au cloudeur, pas à la SCIC : la communication doit le dire |
| **B — qualification de la SCIC** | La SCIC devient fournisseur de cloud et se fait qualifier (audit, processus, organisation, durée d'exploitation) | **Très élevé** | Incompatible avec un calendrier court ; la qualification suppose une existence opérationnelle démontrée |
| **C — trajectoire** | Site Data-Commun en non-sensible + **bascule documentée** vers l'offre qualifiée du cloudeur pour le sensible, avec engagement de calendrier et pénalités | Moyen | Le plus réaliste ; mais impose de **séparer physiquement et logiquement** les deux flux (§3.3.1) |

**Prérequis P2** : choisir A, B ou C **par écrit**, identifier les workloads sensibles, et faire figurer dans la convention les **critères SecNumCloud opposables** (capital/contrôle UE, immunité extraterritoriale, hébergement + exploitation + support UE, audit, pentest, plan de sortie).

#### 3.3.1 Séparation des flux (une exigence technique, pas administrative)

| Flux | Localisation | Exigence |
|---|---|---|
| Données sensibles (État, santé, recherche sous embargo) | Offre qualifiée du cloudeur (option C) ou site dédié à accès contrôlé | Chiffrement, cloisonnement, clés gérées par la SCIC |
| Données ouvertes / communes / non sensibles | Site Data-Commun | Accès public, journalisation, pas de ré-exposition |
| Modèles et poids | Dépositaire EU de poids de modèles (type Hugging Face), reproductibilité des versions | Pas de dépendance à un dépôt unique |

### 3.4 Conformité sectorielle et réglementaire

| Domaine | Ce qu'il faut | Effet sur le projet |
|---|---|---|
| **RGPD** | Registre, analyse d'impact, base légale pour les données d'usage, information des personnes | Edge en zone urbaine = données de trafic/personnalisation à encadrer strictement |
| **AI Act** (règl. UE 2024/1689) | Obligations GPAI depuis le 2 août 2025 ; dispositions high-risk depuis le 2 août 2026 ; transparence, documentation technique, registre | Entraînement de modèles = fournisseur de modèle → obligations de documentation, d'alignment, de transparence |
| **NIS2 / DORA** | Si le service est qualifié d'entité essentielle ou critique | Notification, gestion de risque, plans de crise, tests de crise |
| **HDS** | Hébergeur de données de santé | Si le site héberge de la donnée de santé → certification séparée, non couverte par SecNumCloud |
| **CADA** (Cloud and AI Development Act, en vigueur 04/08/2026) | Guichet unique et permis accéléré, **sans dispense** d'étude d'impact ni de droit de l'environnement | Utile pour les calendriers ICPE, mais ne dispense d'aucune étude d'impact |
| **Marchés publics** | Clauses de souveraineté (niveau 3-4) exigées dans les CCTP | Il faut être éligible : c'est le premier client d'ancrage (§8) |
| **Propriété intellectuelle / licences open source** | Inventaire des licences (GPL/AGPL/Apache) et politique de contribution ; conformité des modèles open weights | Une SCIC qui héberge des modèles ouverts doit respecter les licences amont (Mistral AI Apache 2.0, Llama community licence, etc.) |

### 3.5 Charte de modération des usages : rendre l'éthique opposable

Une « charte » non intégrée aux statuts et aux CGU est un document de communication. **Prérequis P8** :

| Brique | Contenu |
|---|---|
| Principes dans les statuts | Priorité de la recherche publique, de la santé, de l'enseignement supérieur européen et des communs numériques (Wikipédia, OpenStreetMap) |
| Exclusions contractuelles | Minage de crypto-actifs, trading à haute fréquence, applications de surveillance de masse, optimisation fiscale et scoring de solvabilité, applications de modèles open-weight sans licence compatible |
| Mécanisme | Allocation en quotas par catégorie d'usage, priorité explicite, tarif préférentiel, publication des taux d'occupation |
| Arbitrage | Instance de médiation (membre de la coopérative + expert + élu de collectivité), délais de traitement, recours |
| Sanctions | Suspension, retrait de quota, exclusion, sans suppression rétroactive des données de l'usager |
| Transparence | Rapport annuel : consommation par catégorie, part du tarif préférentiel, incidents de modération, indicateurs environnementaux |

---

## 4. Prérequis de site et de territoire

### 4.1 Segmentation des usages (l'astuce de design n° 1)

La puissance ne se découpe pas de façon arbitraire : **on ne fait pas ce que le site peut faire**. Le triparti évite le vice classique du « datacenter unique » qui doit être dimensionné pour le pic d'entraînement alors que 95 % des heures sont passées en inférence.

| Échelle | Charge typique | Exigence de densité | Site | Puissance cible |
|---|---|---|---|---|
| Edge | Inférence 1–20 kW, services de proximité | Faible densité, forte dissimulation | Sous-sol de parking, bâtiment public, piscine, station | 20–200 kW |
| Régional | Inférence industrialisée, services numériques | Densité moyenne, pilotage souple | Friche industrielle hors zone karstique | 1–5 MW |
| Entraînement | Entraînement distribué de modèles ouverts | Forte densité, refroidissement liquide | Friche portuaire/industrielle hors zone karstique et hors habitat | 20–100 MW |

### 4.2 Critères d'exclusion du site (non négociables)

| Critère | Test | Point de vigilance |
|---|---|---|
| **Géologie karstique** | Absence de cavités/catiches dans le rayon d'emprise et sous les emprises de circulation | Les massifs crayeux karstifiés (nappe de la Craie, catiches) sont **incompatibles** avec ce critère : sur un tel site, l'implantation est exclue. Le test se fait **en amont** (prospection géologique, investigations géotechniques), pas en cours de projet |
| **Espèces protégées** | Pas d'habitat d'espèces L.411-1 dans l'emprise ; pas de corridor de chiroptères | Les chauves-souris (colonies de cave, de clochers) et les oiseaux rupestres sont les groupes les plus fréquemment concernés : l'écart de protection conduit couramment à écarter le site |
| **Zone d'habitation** | Distance minimale aux habitations, et mesure d'impact acoustique de la source | L'Edge en zone urbaine dense impose une étude acoustique par site |
| **Artificialisation** | Emprise au sol nouvelle = 0 ; réutilisation de bâti existant ou de dalle déjà imperméabilisée | Condition de la trajectoire « friches » |
| **Eau souterraine** | Pas de recharge de nappe, pas de bassin de rétention des eaux de process industrielles | Nappe de la Craie : zone de captage et risque d'inondation par remontée de nappe |
| **Réseau** | Distance au poste source compatible avec le niveau de puissance visé | 225 kV : 80–150 M€ et 3–5 ans |

### 4.3 Foncier : sécuriser avant d'étudier

**Prérequis P6** — la séquence inverse de l'habitude courante (étudier, puis chercher le foncier) est la cause première des projets retardés ou abandonnés.

| Acte | Contenu | Pourquoi c'est un préalable |
|---|---|---|
| Convention d'occupation / bail emphytéotique | Durée ≥ 15 ans, alignée sur la durée d'amortissement des équipements ; indexation plafonnée | Un bail court (< 10 ans) interdit l'amortissement de la chaleur et des machines, et décourage l'investissement en réemploi |
| Réserve de capacité électrique | Droit de raccordement obtenu avant la conception | Voir §4.4 |
| Clause de substitution de site | En cas de découverte karstique ou d'espèces en cours de travaux | Découverte de carrières souterraines en phase chantier = arrêt de travaux |
| Servitudes et servitudes d'utilité publique | Bandes inconstructibles, accès de maintenance, réseaux traversants | Les lignes HT qui traversent ou longent un site imposent des bandes inconstructibles, des accès de maintenance et des contraintes de sécurité (stockage de fioul et de batteries, gabarits de grues de chantier) |
| Obligation de continuité de service | Reprise des machines et des données en cas de défaillance de l'exploitant | Protection de l'actif coopératif |

### 4.4 Raccordement électrique : le préalable le plus long

| Poste | Contenu | Commentaire |
|---|---|---|
| PTF (proposition technique et financière) Enedis/RTE | Puissance, tension, délai, quote-part, délai de raccordement | Le délai de raccordement (3–5 ans pour un poste 225 kV) **dépasse la durée de construction du datacenter** : c'est le préalable n° 1 du calendrier |
| Tension de raccordement | ≥ 63 kV pour un site de plusieurs MW ; poste de transformation dédié | Rubrique 32 / R.122-2 : autorisation de l'état (2 mois) |
| Source | Contrat d'accès + origine de l'électricité ; à défaut, garantie d'origine | Le mix doit être documenté, sinon l'objection « datacenter sobre en carbone mais alimenté par du charbon importé » est imparable |
| Architecture de secours | Groupes électrogènes + ASI : ce sont eux qui déclenchent l'ICPE rubrique 3110 (puissance thermique > 50 MW) | Voir §4.5 : l'ICPE se joue sur le **secours**, pas sur l'IT |
| Pilotage de la charge | Possibilité de délestage pour préserver l'exploitation du réseau | Un site de 100 MW sans possibilité d'effacement est un risque pour le réseau local |

### 4.5 Autorisations : la séquence et les points de rupture

| Autorisation | Fondement | Effet du non-obtention |
|---|---|---|
| Autorisation environnementale unique (ICPE + eau + espèces) | L.181-1 et s., L.515-28, R.122-2 rubriques 1/32/39 | **Arrêt total** : pas de chantier |
| ICPE rubrique 3110 | Groupes électrogènes, seuil thermique | Déclenche l'enquête publique et l'étude d'impact |
| ICPE rubriques batteries (2925) et fluides frigorigènes | Accumulateurs de secours, circuits de refroidissement | Souvent oublié ; peut suffire à basculer en régime d autorisation |
| Dérogation espèces (L.411-2) | Destruction de sites de reproduction | Délai long, forte probabilité de refus sur site karstique |
| Autorisation de prélèvement d'eau | L.214-1 et s. | Si un jour le refroidissement consomme de l'eau (contradiction avec WUE 0), la procédure change tout |
| Permis de construire / permis d'aménager | Urbanisme | Après l'autorisation environnementale |
| Autorisation de travail en hauteur / ERP | Locaux Recevant du Public (piscine, mairie) pour l'Edge | Sujet propre aux sites Edge, à traiter site par site |
| Raccordement électrique | RTE/Enedis | Conditionne tout le reste |

**Prérequis P7** : une **note d'opposabilité** produite par un tiers (bureau d'études ICPE + avocat) qui identifie, site par site, les autorisations à obtenir et les points de rupture. Elle est un livrable de la phase 0, pas une formalité de fin de projet.

---

## 5. Prérequis thermiques et énergétiques

### 5.1 PUE < 1,15 **et** WUE ≈ 0 : vérifier la faisabilité, pas seulement l'affichage

| Cible | Ce qu'elle exige | Point de vigilance |
|---|---|---|
| **PUE < 1,15** | Refroidissement **sans** tour de refroidissement ni tour adiabatique (donc sans eau) ; à défaut, tours fermées avec appoint d'eau minimal ; salle à forte densité | Un PUE < 1,15 suppose une **charge IT élevée et stable** ; l'Edge (charge variable, faible densité) a un PUE structurellement pire. **Le PUE doit être mesuré par échelle**, pas en moyenne globale |
| **WUE = 0 L/kWh IT** | Circuits fermés stricts (refroidisseurs à eau secs, tours de refroidissement à sec ou condenseurs à air), aucune eau potable en refroidissement, aucun apport d'humidité par évaporation | « Zéro » au sens strict est inatteignable : appoints de fuite, déshumidification en ambiance, eau de chantier. Cible défendable : **WUE_IT < 0,01 L/kWh** et **eau de refroidissement = 0 m³** en exploitation, avec un indicateur d'empreinte hydrique publié (option **Water Positive**) |
| **PUE/WUE/CUE ensemble** | Suivi mensuel **public** des trois indicateurs, avec méthode et périmètre | Le PUE seul masque l'eau et le carbone : c'est l'argument le plus facile à opposer au projet |

**Point technique à trancher** : un dispositif **sans eau** (refroidissement à sec ou direct-to-chip avec condenseurs à air) rejette plus de chaleur à la température ambiante que les tours évaporatives ; il consomme donc **plus** d'électricité pour la même charge utile. Le projet doit assumer cet arbitrage explicitement (PUE 1,15 ↔ WUE 0) au lieu de promettre les deux « naturellement ».

### 5.2 Chaleur fatale 100 % : le point dur du projet

**Pourquoi c'est le point dur** : la valorisation de la chaleur est le seul bénéfice qui rend le projet désirable pour les collectivités, et c'est aussi l'exigence la plus facile à promettre et la plus difficile à tenir.

| Contrainte | Réalité | Conséquence |
|---|---|---|
| **Température** | Un réseau de chaleur urbain fonctionne à haute température (typiquement 95/75 °C côté distribution) ; la chaleur récupérée en air-cooled arrive à 30–45 °C, en immersion « eau chaude » à 35–55 °C | Pour **100 %** de valorisation dans un réseau à haute température, il faut soit de l'**immersion eau chaude** (60–90 °C, coût et contraintes de maintenance), soit une **pompe à chaleur** de relève (CAPEX + rendement dégradé) |
| **Saisonnalité** | Le besoin de chauffage est saisonnier (octobre–mars) ; le datacenter est **constant** | En été, la chaleur n'a pas de débouché : soit stockage thermique (réservoir d'eau chaude / glace), soit **réseau de froid** — que plusieurs métropoles prévoient (à Lille, un réseau de froid est évoqué : `lillemetropole.fr/les-reseaux-de-chaleur-urbains`) |
| **Continuité** | Un réseau de chaleur ne tolère pas l'arrêt ; le datacenter si | Prévoir un bypass et un échangeur de secours, ou lire les calories en base (prairie) |
| **Compte** | 100 % valorisé ≠ 100 % utilisé | Conventionner une **quantité garantie** (base) et un volume facturé (indexé) ; la chaleur produite en été doit être contractée ailleurs (froid, industrie, stockage) |
| **Contrepartie** | Sur une métropole comme Lille, 6 réseaux de chaleur publics existent, exploités notamment par ilenergy (filiale de Dalkia) | **Partenaire naturel** : la négociation porte sur des prix, des volumes et des températures, pas sur l'existence d'un interlocuteur |

**Prérequis P5** : une **convention de raccordement chaleur** (puissance, températures d'aller/retour, saisonnalité, prix, indexation, responsabilité de la continuité, valorisation des deux parties) + une étude technico-économique comparant trois scénarios : (a) immersion eau chaude avec réseau 95/75, (b) boucle 40 °C + pompe à chaleur, (c) couplage chaleur + réseau de froid + stockage. Sans ce document, la cible « 100 % » n'est pas finançable.

### 5.3 Immersion : fluides, environnement, fin de vie

| Sujet | Exigence |
|---|---|
| Nature du fluide | **Pas de fluide fluoré à haut PBP** (PFAS / type Novec) : risque réglementaire européen et image de marque incompatible avec le projet. Exiger un fluide **biodégradable certifié**, sans PFAS, avec fiche de données de sécurité et analyse de cycle de vie |
| Toxicité / sécurité incendie | Fluide non inflammable ou auto-extinguible, plan d'intervention incendie spécifique |
| Fin de vie | Contrat de reprise du fluide usagé (reconstitution), provision de démantèlement |
| Maintenance | Composants immergés / composants « froids » : la maintenance des nœuds de calcul est un métier distinct → clause de compétence et de stock de pièces |
| Compatibilité | Cuivre, aluminium, caoutchouc, colles : la liste de compatibilité est une contrainte d'architecture (cartes accélératrices, connecteurs) |

### 5.4 Bruit, vibrations de sol, infrasons

Le principe « le sol est une caisse de résonance » est juste et doit être traité **comme un prérequis de conception**, pas comme un argument de communication.

| Mesure | Efficacité | Commentaire |
|---|---|---|
| **Refroidissement par immersion** (suppression des ventilateurs) | Forte | Supprime la source majoritaire de bruit aéré et de vibration de la salle machine |
| **Supports viscoélastiques / à plots** des équipements mécaniques (groupes, pompes, chillers) | Forte | Traitement standard ; coût marginal si conçu dès l'origine |
| **Dalle flottante / découplage** | Moyenne à forte | Efficace sur les fréquences supérieures à 10 Hz ; effet limité sur les basses fréquences |
| **Tranchées d'atténuation périphériques** (sable, caoutchouc broyé) | **Faible à modérée** | Souvent surestimée : peu d'effet sous ~10 Hz, coût d'excavation important, **risque d'infiltration d'eau** et incompatibilité avec un site karstique (catiches). À traiter comme mesure de dernier recours, sur preuves, pas comme principe |
| **Souplesse des raccordements** (bellows, travées), suppressions de points durs | Bonne | Souvent plus efficace que le génie civil |
| **Régime de fonctionnement** | Variable | Fonctionnement par paliers de puissance, arrêt des groupes au-delà d'un seuil thermique |

**Prérequis (mesure avant travaux)** : campagne géophysique **avant** et **après** mise en service, site + habitations les plus proches, en vibrations et en infrasons (méthodologie déjà dégagée dans `datacenter/bruit/infrasons-sante.md` et `datacenter/bruit/NuisancesSonores.md`), avec seuils d'alerte et de suspension intégrats au permis. Sans mesure d'état initial, toute contestation ultérieure sera perdue d'avance.

---

## 6. Prérequis matériels et logiciels

### 6.1 Stack logicielle : la base (non négociable)

| Couche | Choix | Points de vigilance |
|---|---|---|
| Hyperviseur / virtualisation | **KVM / Proxmox VE** (open source, Autrichienne) ou OpenStack | Pas de VMware/Broadcom, pas de Hyper-V/Windows Server |
| OS hôte | **Debian** / **AlmaLinux** (ou Rocky), support long | Alignement avec les durées de support des éditeurs |
| Stockage | **Ceph** | Exige du matériel SATA/SAS avec endurance suivie ; à combiner avec la contrainte « reconditionné » |
| Orchestration | Kubernetes open source (autogéré) ou solution légère type Nomad | Éviter les distributions à code source fermé (OpenShift, Tanzu) |
| Réseau | Routage **FRRouting**/SONiC, plan d'adressage et MTU documentés | Le réseau intra-cluster est le point de lock-in oublié (NVLink/InfiniBand) |
| Supervision | Prometheus + Grafana + OpenTelemetry, stockage de métriques ouvert | La télémétrie ne doit pas sortir de l'UE (exigence SecNumCloud) |
| Firmware | **OpenBMC** / coreboot, sans firmware signé verrouillé | Prérequis de la durabilité : pas d'obsolescence programmée |

> **Cohérence à signaler** : Ceph (Red Hat/IBM, US) et OpenStack (US) sont des projets **à code source ouvert** mais **gérés par des fondations américaines**. Ils ne sont pas des technologies « sous licences américaines » au sens du CLOUD Act, mais ils ne sont pas non plus européens. La règle doit porter sur la **gouvernance, le support, la capacité de fork et l'absence de clause d'audit extra-UE** — pas sur la nationalité du portefeuille (§9-A).

### 6.2 Accélérateurs : la porte ROCm (jalon go/no-go)

Le remplacement de CUDA par ROCm est **le** risque technique principal du projet. Ce n'est pas une question de licence : c'est une question de **performance et de portabilité**.

| Élément | État | Conséquence |
|---|---|---|
| Pile logicielle | ROCm est open source et couvre l'essentiel de l'écosystème (PyTorch, vLLM, ONNX, Triton) | La portabilité **de principe** existe |
| Couverture des opérateurs | Tous les kernels d'attention optimisés ne sont pas au même niveau de maturité / performance | Les gaps se concentrent sur l'attention, le FlashAttention, les kernels quantifiés, certaines communications collectives multi-GPU |
| Interconnexion | Ethernet ouvert (UALink, RoCE) progresse mais reste moins intégré que NVLink/InfiniBand | Sur les modèles de grande taille, l'interconnexion peut dominer le coût total |
| Versions | Suivi des kernels rapide et parfois cassant | Exiger un **verrouillage de version** et un protocole de test de non-régression |
| Compétence | Peu d'ingénieurs formés au portage ROCm | Prérequis de recrutement/formation ; à chiffrer comme un poste d'exploitation, pas comme un coût ponctuel (§8.2) |

**Prérequis P4 — le test d'ouverture (jalon go/no-go)** : avant tout engagement d'investissement lourd sur l'étage Entraînement, publier un **rapport de portabilité** sur une batterie de workloads représentatifs (pré-entraînement, post-entraînement, inférence quantifiée, *serving* multi-modèle) qui mesure, sur la stack cible :

1. Le **débit** (tokens/s ou images/s) et le **coût par job** par rapport à une référence CUDA de la même génération ;
2. Le **taux de précision** des résultats par rapport à la référence (tolérance de non-régression chiffrée dans le document lui-même) ;
3. Le **taux de succès** des jobs (les kernels non supportés sont le vrai piège : un job qui plante coûte une nuit de GPU) ;
4. Le **coût du portage** par modèle (jours-homme) et la **charge de maintenance** de la pile.

Sans ce rapport, le projet ne peut pas vendre une infrastructure d'entraînement sur une stack non validée. **Le seuil de passage doit être écrit dans le document lui-même, avant le test** (critère d'objectivité).

### 6.3 Filière européenne : Rhea et RISC-V — un horizon, pas un socle

| Élément | Réalité | Conséquence |
|---|---|---|
| **SiPearl Rhea1** | Processeur serveur européen conçu dans le cadre de l'European Processor Initiative, **basé sur Arm Neoverse V1** (80 cœurs, HBM, DDR5), tape-out en **juin 2025**, échantillons et serveur de référence « Seine » ; Rhea2 en chiplets ; positionnement sur le segment CSP annoncé | C'est une **avancée européenne réelle**, mais **ce n'est pas une ISA ouverte** : le cœur reste Arm (propriétaire UK, groupe japonais SoftBank depuis 2016). La « souveraineté » de Rhea est **industrielle et politique**, pas architecturale |
| **RISC-V pour le calcul généraliste** | SiPearl elle-même déclare qu'une CPU RISC-V pour le HPC/les datacenters serait « un prototype de laboratoire » et **non commercialisable**, faute d'écosystème logiciel (déclaration du CEO, EETimes) | L'horizon « RISC-V partout » est **post-2030**. À traiter comme un **projet de R&D** avec des jalons, pas comme un socle |
| **Projets européens à suivre** | DARE (*Digital Autonomy with RISC-V in Europe*), EPI (Semidynamics pour les accélérateurs RISC-V), programme RISER/OCP *Higher* (plateformes cloud ouvertes basées sur OCP) | Candidats à un **partenariat de recherche et de qualification**, pas à une commande de production |
| **Écosystème logiciel RISC-V** |- Linux, compilateurs, bibliothèques ; manque l'équivalent mature de CUDA (kernels, bibliothèques d'accélération, outils) | Un GPU RISC-V « nu » ne sert qu'aux usages non-AI et à la R&D |

**Position recommandée** : Data-Commun démarre sur **AMD EPYC + AMD Instinct (ROCm)**, tient un **pilotage RISC-V/EPI** (un serveur, un cluster de test, une publication de résultats), et **conditionne** tout investissement matériel Rhea/RISC-V à la preuve d'un stack logiciel mature. Cela n'invalide pas la proposition initiale : cela la rend **tenable en budget et en calendrier**.

### 6.4 Circularité : rendre « 40 % de reconditionnés » opposable

Le « 40 % » est aujourd'hui un pourcentage sans périmètre. Il faut le rendre **vérifiable** :

| Question à trancher | Rédaction proposée |
|---|---|
| Sur quoi porte le quota ? | Par **an**, sur le **volume de serveurs acquis** (et non sur le parc total), et **hors plan d'accélérateurs** |
| Quels plans sont visés ? | Plan de gestion, plan de stockage, plan réseau, plan CPU de service. **Le plan d'accélérateurs n'est pas réalistiquement réemployable** (HBM, interconnexion, firmware, garantie) : l'exclure explicitement évite un quota de pure façade |
| Base de calcul | Nombre de **racks** ou nombre de **serveurs** ? Le rack (avec son câblage et son alimentation reconditionnés) est la bonne unité |
| Quel standard de remise en état ? | Référentiels **OCP** : Circularity (workstream de l'OCP Sustainability), spécification **CEDaCI** (châssis 2RU « Circular Economy-Ready », 2023), spécification OCP de **sanitisation des données** pour le réemploi |
| Quelle garantie ? | Garantie commerciale **au moins équivalente** au neuf (≥ 3 ans, NBD 4 h sur site) — sans cela, la disponibilité est irrécupérable |
| Quel firmware ? | **OpenBMC / coreboot**, partition de l'OS lisible et remplaçable, aucun scellement du BIOS/UEFI |
| Quelle durée de vie ? | Objectif : **7 ans minimum** de support matériel et logiciel par génération, documenté et opposable |
| Quelle fin de vie ? | Contrats de reprise et de recyclage (éco-organisme DEEE), traçabilité des équipements et de leurs composants critiques |
| Quelle preuve ? | Inventaire annuel par numéro de série, audité par un tiers, publication de l'indicateur |

**Point de droit** : la directive (UE) 2024/1799 sur le droit à la réparation (transposition due en 2026) donne un appui pour inscrire dans les marchés la obligation de **durabilité, de pièces et de mise à jour logicielle** — à confirmer dans les décrets d'application français avant de s'en servir comme argument contractuel.

### 6.5 Réseau et interconnexion

| Élément | Exigence |
|---|---|
| Transport | Deux chemins physiques distincts, deux opérateurs, aucun point unique de défaillance ; secours en fibre ou 5G/SD-WAN pour l'Edge |
| Conduites | L'Edge doit être raccordé **sans arrêt de service** : les occupants (parkings, piscines) n'acceptent pas de coupure de chauffage ; prévoir alors un onduleur et une bascule |
| Latence | L'Edge est un point de présence : la latence vers le cœur doit être compatible avec le service visé (voix, visio, contrôle) |
| Souveraineté | Routeurs et logiciel réseau sans dépendance extra-UE (FRRouting, SONiC, Linux) ; supervision en UE |

---

## 7. Prérequis d'exploitation, de compétences et de modération

| Domaine | Prérequis | Risque si absent |
|---|---|---|
| **Modèle de service** | SLA par plan (latence, disponibilité, engagement de performance du job, reprise), avec un **niveau « calcul.schedule »** distinct du « calcul.données sensibles » | Le client d'ancrage est public : il exigera un SLA opposable |
| **Exploitation** | Astreinte 24/7/365, au moins deux rotations, procédure de reprise après sinistre testée | Un datacenter sans astreinte est un accident en attente |
| **Compétences** | Recrutement ou convention de formation à : KVM/Proxmox, Ceph, Kubernetes, ROCm/XCCL, réseau ouvert, thermique/immersion, géophysique du bruit | **La couche 5 (compétences / réversibilité) est le maillon le plus souvent faible** |
| **Sécurité** | Journalisation, gestion des clés **par la SCIC** (HSM), politique de correctifs, tests d'intrusion annuels, procédure de notification NIS2 | Absence de maîtrise des clés = absence de souveraineté |
| **Reprise d'activité** | Plan de reprise d'activité *et* de **repli sur site secondaire** (géographie distincte) | La souveraineté n'existe pas si la sauvegarde est dans un seul endroit |
| **Sauvegardes** | Copies chiffrées chez un **tiers** (PEPR), politique RPO/RTO testée | Sinon, la sortie du cloudeur (option A/C) est irréversible |
| **Modération** | Voir §3.5 : instance d'arbitrage, allocation en quotas, publication des indicateurs | La charte éthique se dilue au premier client à fortiori |
| **Transparence** | Rapport annuel public : énergie, eau, chaleur, taux de reconditionnement, occupations, incidents | Sans publication, aucune des cibles du §5 n'est opposable |

---

## 8. Prérequis économiques et financiers

### 8.1 Le modèle économique d'une SCIC

Une SCIC **n'a pas d'objectif de maximisation** : son équilibre doit être construit par des flux **délibérément non commerciaux** ou **socialement tarifés**. Cinq sources, dans cet ordre de réalisme :

| Source | Mécanisme | Réalité |
|---|---|---|
| **Client d'ancrage** | Engagement pluriannuel (État, université, CHU, commune) sur un volume garanti | **Le seul levier de crédibilité** : sans lui, pas de financement bancaire |
| **Subventions et appels à projets** | France 2030 (IA), fonds européens (EuroHPC, EPI, CADA), aides régionales et de l'Agence de la transition écologique, aides à la chaleur fatale | Réel, mais lents et conditionnés |
| **Contrat de chaleur** | Revenu de la vente de calories (faible prix unitaire, volume élevé) | Utile mais **très inférieur** au CAPEX : ne pas le surestimer dans le plan |
| **Tarif préférentiel de la coopérative** | Prix de l'appel inférieurs au marché, compensé par la subvention et la chaleur | C'est la traduction financière de la charte de modération |
| **Mécénat / financement participatif / commande publique de R&D** | Financement non dilutif du risque d'exploitation | Réel pour l'amorçage, insuffisant pour l'exploitation |

### 8.2 Structure de coûts : ce qu'il faut chiffrer avant d'engager

| Poste | À chiffrer | Piège |
|---|---|---|
| Raccordement électrique | Poste 225 kV dédié : **80–150 M€**, **3–5 ans** | Un financeur qui paie le raccordement **impose ses conditions** : c'est le vrai risque de souveraineté |
| Bâtiment et travaux | Adaptation de friches ou construction neuve ; mise aux normes ICPE/ERP | La « zéro artificialisation » a un coût de travaux non nul |
| Refroidissement | Immersion / direct-to-chip / air ; coût du circuit d'eau, du fluide, de la maintenance | L'immersion augmente le coût de maintenance, réduit le coût d'exploitation |
| Accélérateurs | **Délais de livraison 36–52 semaines**, prix spot +20–30 % ; refresh GPUs tous les ~4 ans | Un parc IA est un **actif à refresh permanent**, pas un investissement ponctuel |
| Personnel | Astreinte, SRE, modérateurs, géophysicien | Le coût d'exploitation dépasse souvent le coût du bâtiment |
| Certification | Audit SecNumCloud, HDS, ISO 27001, pentests récurrents | Coût récurrent, à inscrire au budget pluriannuel |
| Sortie du cloudeur | Coût de migration des données, des workloads, des clés | **Doit être provisionné dès le départ** |

### 8.3 Le préalable économique n° 1 : l'accès aux accélérateurs

Le poste dominant n'est pas le bâtiment, c'est **le silicium d'accélération**, et son disponibilité est subordonnée aux allocations des fournisseurs. Conséquence opérationnelle : **Data-Commun ne doit pas acheter ses accélérateurs au démarrage**, mais **souscrire de la capacité** chez un fournisseur européen (contrat de capacité pluriannuel à prix échelonné, avec clause de priorité et de non-confinement des workloads). Cela déplace le risque d'approvisionnement vers le contrat et supprime le risque d'obsolescence sur un parc détenu.

**Prérequis P9** : client d'ancrage + plan de financement + contrat de capacité, ou le projet n'est pas finançable.

---

## 9. Points d'incohérence de la spécification initiale (à trancher)

| # | Formulation initiale | Problème | Proposition de correction |
|---|---|---|---|
| 🔴 **A** | « **Interdiction absolue** des technologies sous licences américaines » | Incompatible avec AMD EPYC (x86, US), avec SiPearl Rhea (Arm), avec TSMC, la HBM (KR), les EDA (US), Ceph/OpenStack (fondations US). Rend le cahier des charges **non exécutable** | Remplacer par **6 critères auditables** : (1) pas de soumission à une loi extraterritoriale ; (2) code ouvert et forkable ; (3) support et supervision en UE ; (4) pas de verrouillage propriétaire ni d'obsolescence programmée ; (5) réversibilité et export documentés ; (6) fournisseur et actionnariat non soumis à un contrôle extra-UE |
| 🔴 **B** | « SiPearl Rhea (Europe) » comme socle de calcul, présenté comme ouvert | Rhea1 est **basé sur Arm Neoverse V1** ; Arm est sous contrôle du groupe japonais SoftBank ; l'ISA n'est pas libre. SiPearl déclare par ailleurs que RISC-V « n'est pas prêt » pour le HPC/les datacenters | Présenter Rhea/RISC-V comme un **axe de R&D et de qualification à horizon 3-5 ans**, pas comme socle ; démarrer sur AMD/ROCm avec une porte de sortie documentée |
| 🔴 **C** | « Stack 100 % open-source » + « SecNumCloud 3.2 » sans dire **qui** est qualifié | SecNumCloud qualifie un **service et son fournisseur** ; la SCIC ne le sera pas spontanément | Choisir explicitement A/B/C (§3.3) et **séparer physiquement** les flux sensibles / non sensibles |
| 🔴 **D** | « PUE < 1,15 **et** WUE = 0 **et** chaleur fatale 100 % **et** 40 % reconditionnés » | Quatre cibles maximales simultanément ; il existe des tensions physiques entre elles (notamment chaleur à haute température ↔ circuits froids ↔ absence d'évaporation) | Hiérarchiser : (1) PUE/WUE **par échelle** avec tolérances, (2) chaleur valorisée **en base ferme** et **volume indexé**, (3) reconditionnement **sur les plans éligibles** avec définition opposable |
| 🔴 **E** | « Zéro artificialisation » + « friches industrielles (sols déjà pollués) » | Un sol pollué, c'est une **dépollution** et une responsabilité de l'exploitant (art. L.514-1 et s.) — sur un site industriel ancien, l'antériorité de la pollution est un sujet à instruire, pas un atout | Exiger une étude de sols et un état des risques industriels (ESRIS), puis une convention de répartition des coûts de dépollution **avant** signature du bail ; à défaut, écarter le site |
| 🔴 **F** | « Tranchées d'atténuation » comme dispositif principal contre les vibrations de sol | Efficacité faible sous ~10 Hz, coût d'excavation, **risque d'infiltration et incompatibilité karstique** | Remplacer par : découplage des machines, supports viscoélastiques, dalle découplée, raccordements souples, **mesures avant/après** ; tranchées seulement sur preuves, et exclues a priori en zone karstique |
| 🔴 **G** | « 40 % de serveurs reconditionnés » sans périmètre ni standard | Le quota est inapplicable au plan d'accélérateurs ; l'OCP fournit bien des référentiels (Circularity, CEDaCI, sanitisation) | Définir : par an, par rack, plans éligibles, garantie, firmware ouvert, audit annuel (§6.4) |
| 🔴 **H** | « Alliance exclusive avec un cloudeur EU » + « gouvernance sous contrôle de la SCIC » | Une alliance **exclusive** supprime la concurrence et la réversibilité : c'est l'inverse d'une exigence de souveraineté | Alliance **non exclusive**, avec clause de sortie, plan de réversibilité et droit d'auditer ; la pluralité des fournisseurs est un levier de négociation |
| 🔴 **I** | « Interdiction du minage, du trading HFT, de la surveillance de masse » posés comme simples exclusions | Sans mécanisme (allocation, arbitrage, sanctions, publication), ce sont des intentions | Intégrer la charte aux statuts et aux CGU, avec instance d'arbitrage et transparence (§3.5) |
| 🔴 **J** | « Datacenter souverain » sans préciser la couche | La souveraineté est **le maillon le plus faible** ; le hardware restera non européen | Communiquer explicitement : « **souveraineté de gouvernance, d'exploitation et de données** ; hardware non souverain, réversibilité contractuelle » — c'est vérifiable, donc crédible |

---

## 10. Feuille de route et jalons go/no-go

| Phase | Durée indicative | Livrables | Jalon de sortie (go/no-go) |
|---|---|---|---|
| **P0 — Cadrage juridique et territorial** | 0–6 mois | Avis juridique SCIC ; grille de 6 critères de souveraineté ; note d'opposabilité des autorisations ; 3 sites pressentis (Edge) + 1 site régional + 1 site d'entraînement avec critères de franchissement ; campagne géophysique initiale ; étude de chaleur ; benchmark plan ROCm | **GO 0** : existence d'un site d'entraînement **hors karst et hors artificialisation**, d'un client d'ancrage (**LOI**), d'un engagement cloudeur sur la qualification SecNumCloud |
| **P1 — Conception et autorisations** | 6–18 mois | Dossier ICPE/dérogation ; PTF Enedis ; bail ; convention de chaleur ; statuts définitifs ; marchés de réemploi ; contrat de capacité d'accélérateurs | **GO 1** : autorisation environnementale obtenue **et** convention de chaleur signée **et** PTF accepté |
| **P2 — Edge et inférence régionale** | 12–24 mois | 5–15 caissons Edge en service ; site régional de 1–5 MW ; supervision et exploitation internalisées ; 1er rapport PUE/WUE/chaleur | **GO 2** : SLO tenus sur 6 mois, taux de panne de l'Edge sous 1 %/an, chaleur valorisée facturée |
| **P3 — Entraînement** | 24–48 mois | Tranche d'accélérateurs (AMD Instinct ou équivalent) ; **rapport de portabilité ROCm** ; premier modèle ouvert entraîné ; 40 % de réemploi atteint sur les plans éligibles | **GO 3** : rapport de portabilité conforme au seuil écrit avant test, **et** premier modèle de référence reproduit à précision équivalente |
| **P4 — Industrialisation et R&D européenne** | 48 mois+ | Extension du parc ; pilote RISC-V/EPI ; participation aux programmes OCP ; publication des résultats | **GO 4** : résultats publics du pilote RISC-V (perf/coût comparés) |

**Règle de gestion** : chaque jalon GO est un **arrêt possible sans que le capital engagé soit perdu** (les phases P0/P1 ne créent pas de dette d'équipement ; le parc d'accélérateurs n'est souscrit qu'après GO 2). C'est ce qui distingue une proposition sérieuse d'une opération de communication.

---

## 11. Registre des risques

| # | Risque | Probabilité | Impact | Mitigation |
|---|---|---|---|---|
| R1 | La performance ROCm ne permet pas les modèles de la taille visée | Élevée | Fort | Jalon GO 3 sur rapport chiffré ; parc d'accélérateurs souscrit après GO 2 ; consortium avec les modèles ouverts européens |
| R2 | La chaleur valorisée à haute température impose une CAPEX qui annule l'économie du projet | Moyenne | Fort | Étude 3 scénarios (§5.2) avant GO 1 ; contrat de chaleur avec engagement de volume ; réseau de froid urbain comme débouché estival |
| R3 | Le foncier « zéro artificialisation » introuvable, ou pollué | Moyenne | Fort | Réserve de 3 sites par typologie ; étude de sols préalable ; bail avec clause de substitution |
| R4 | Le raccordement électrique reste bloqué 3–5 ans, ou impose des conditions | Élevée | Fort | PTF obtenu avant conception ; à défaut, mutualiser l'étage d'entraînement sur un site déjà raccordé (mutualisation) |
| R5 | Dépassement du planning d'autorisation (enquête publique, espèces) | Moyenne | Moyen | Note d'opposabilité ; phasage ; commencer par l'Edge, moins exposé |
| R6 | Dérive de la gouvernance : le cloudeur impose sa roadmap | Moyenne | Fort | Clauses §3.2 ; comité technique ; audit annuel ; clause de sortie sans pénalité |
| R7 | Tension sur l'approvisionnement en accélérateurs (allocation, prix) | Élevée | Moyen | Ne pas acheter au démarrage : contrat de capacité ; priorisation par la charte de modération |
| R8 | Un incident de bruit / vibration sur un site Edge urbain | Moyenne | Moyen | Mesures avant/après, découplage mécanique, seuils contractuels avec l'occupant |
| R9 | Non-conformité réglementaire sectorielle (AI Act, RGPD, HDS) | Moyenne | Fort | DPO / référent conformité dans la SCIC ; audit annuel ; documentation par workload |
| R10 | Modération conflictuelle (un client exclu invoque un recours commercial) | Faible | Moyen | Arbitrage prévu au règlement ; inscription dans les CGU ; risque contentieux provisionné |
| R11 | Effet d'opportunité : le temps passé sur Data-Commun laisse le giga-datacenter sans contre-proposition | Élevée | Moyen | Calibrer P0 sur 6 mois maximum ; produire un document public à 6 mois |
| R12 | Le projet est perçu comme un écran de conventionalité du porteur | Moyenne | Fort | Publication ouverte des indicateurs, des jalons et des échecs ; document unique de suivi ; aucune annonce avant GO 0 |

---

## 12. Annexe A — Checklist des prérequis

| ID | Prérequis | Bloquant | Preuve attendue | Responsable | Jalon |
|---|---|---|---|---|---|
| P1.1 | Avis juridique sur la forme SCIC / SEM et le plafond de 20 % | Oui | Note d'avocat | Direction projet | P0 |
| P1.2 | Statuts : 3 catégories d'associés, gouvernance, non-distribution | Oui | Statuts + RCS | Direction projet | P0 |
| P2.1 | Choix d'architecture SecNumCloud (A/B/C) | Oui | Note d'arbitrage | Direction + juriste | P0 |
| P2.2 | Séparation physique/logique des flux sensibles | Oui | Schéma d'architecture | RSSI | P1 |
| P3.1 | Grille de 6 critères de souveraineté + audit de la chaîne | Oui | Grille + audit | RSSI | P0 |
| P4.1 | Batterie de tests ROCm + seuil d'objectivité écrit | Oui | Protocole de test | Lead IA | P0 |
| P4.2 | Rapport de portabilité | Oui | Rapport public | Lead IA | P3 |
| P5.1 | Étude 3 scénarios chaleur | Oui | Étude technico-économique | Thermique | P0 |
| P5.2 | Convention de raccordement chaleur | Oui | Convention signée | Direction | P1 |
| P5.3 | Identification du fluide d'immersion (sans PFAS) | Oui | FDS + analyse de cycle de vie | Thermique | P1 |
| P6.1 | Réserve de sites (3 Edge / 1 régional / 1 entraînement) | Oui | Fiche de site + critères franchis | Foncier | P0 |
| P6.2 | Étude de sols / antériorité de pollution | Oui | ESRIS | Foncier + BE | P0 |
| P6.3 | Bail ≥ 15 ans + clause de substitution | Oui | Bail | Foncier | P1 |
| P6.4 | PTF Enedis/RTE | Oui | PTF accepté | Énergie | P1 |
| P7.1 | Note d'opposabilité des autorisations | Oui | Note BE + avocat | BE ICPE | P0 |
| P7.2 | Autorisation environnementale | Oui | Arrêté | BE ICPE | P1 |
| P8.1 | Charte d'usage dans statuts + CGU | Oui | Règlement + CGU | Direction | P1 |
| P8.2 | Instance d'arbitrage opérationnelle | Oui | Statut de l'instance | Gouvernance | P2 |
| P9.1 | LOI client d'ancrage | Oui | LOI signée | Commercial | P0 |
| P9.2 | Plan de financement pluriannuel | Oui | Plan + scenarii | Direction | P1 |
| P9.3 | Contrat de capacité d'accélérateurs | Oui | Contrat | Achats | P2 |
| P10.1 | Plan de recrutement SRE / IA / thermique | Oui | Plan + conventions | RH | P1 |
| P10.2 | Astreinte 24/7 opérationnelle | Oui | Planning +astreinte | Exploitation | P2 |
| P11.1 | Campagne géophysique avant travaux | Oui | Rapport + seuils | Géophysique | P0/P1 |
| P11.2 | Suivi des vibrations en exploitation | Oui | Rapport périodique | Exploitation | P2+ |
| P12.1 | Reporting PUE/WUE/CUE/chaleur/reemploi | Oui | Rapport mensuel public | Exploitation | P2 |
| P12.2 | Audit annuel du taux de réemploi (tiers) | Oui | Rapport d'audit | Direction | P3 |

---

## 13. Annexe B — Sources

### Cadre juridique

- **SecNumCloud v3.2** — ANSSI, référentiel d'exigences, 8 mars 2022 (14 thèmes, ~360 exigences) — catalogue des offres qualifiées sur *cyber.gouv.fr*.
- **Loi SREN** du 21 mai 2024, art. 31 ; **décret n° 2026-272** du 14 avril 2026 ; **arrêté du 12 août 2026** (JO du 14/08/2026, en vigueur le 15/08/2026) : le référentiel 3.2 devient le cadre exigible pour les données particulièrement sensibles confiées à un cloud commercial par l'État, ses opérateurs et certains groupements d'intérêt public.
- **SCIC** : loi n° 2002-5 du 7 mars 2002 ; décret n° 2002-241 du 21 février 2002 (justification du caractère d'utilité sociale) ; loi n° 2012-387 du 22 mars 2012 (suppression de l'agrément préfectoral) — [legifrance.gouv.fr/loda/id/JORFTEXT000000227145](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000227145) ; plafond de 20 % de capital pour les collectivités.
- **CLOUD Act** (US, 2018), **FISA 702**, RGPD, Data Act (UE), NIS2/DORA — analyse dans `datacenter/souverainete-numerique-generalites.md` §3.1.
- **CADA** (Cloud and AI Development Act), en vigueur 04/08/2026 — `datacenter/souverainete-numerique-generalites.md` §3.4.
- **AI Act** (règl. UE 2024/1689) : obligations GPAI depuis le 02/08/2025, dispositions high-risk depuis le 02/08/2026.
- **Directive (UE) 2024/1799** — droit à la réparation (transposition due en 2026).
- **ICPE** : L.181-1 et s., L.515-28, rubrique 3110, R.122-2 rubriques 1/32/39 ; **L.411-1 / L.411-2** (espèces) ; **L.214-1 et s.** (eau) ; **L.514-1 et s.** (responsabilité pollution des sols).

### Infrastructure, énergie, territoire

- **Réseaux de chaleur urbains** : exemple de Lille Métropole, 6 réseaux publics et un **réseau de froid** en projet — [lillemetropole.fr/les-reseaux-de-chaleur-urbains](https://www.lillemetropole.fr/les-reseaux-de-chaleur-urbains) et [lillemetropole.fr/reseaux-de-chaleur](https://www.lillemetropole.fr/reseaux-de-chaleur).
- **Raccordement** : poste 225 kV dédié, **80–150 M€**, **3–5 ans** ; délai moyen de raccordement observé sur le territoire français : 5–7 ans (France Datacenter / RTE).
- **PUE / WUE** : définitions Schneider Electric (PUE, WUE L/kWh).
- **Nappe de la Craie, karst, catiches** : bases de données géologiques et fiches de risques (BRGM, Fiches Risques) pour la qualification des sols, des karsts et des anciens sites industriels.
- **Bruit, vibrations, infrasons** : `datacenter/bruit/infrasons-sante.md`, `datacenter/bruit/nuisances-sonores-sante.md`, `datacenter/bruit/NuisancesSonores.md`, `datacenter/nuisances-datacenter-11-axes.md`.

### Matériel et circularité

- **OCP Circularity** (workstream de l'OCP Sustainability) — [opencompute.org/projects/sustainability/circularity](https://www.opencompute.org/projects/sustainability/circularity).
- **OCP CEDaCI** — spécification châssis 2RU « Circular Economy-Ready » (2023) — [opencompute.org/documents/2023-ocp-base-specification-cedaci-circular-economy-ready-2ru-server-chassis-design-kk-edit-docx-2-pdf](https://www.opencompute.org/documents/2023-ocp-base-specification-cedaci-circular-economy-ready-2ru-server-chassis-design-kk-edit-docx-2-pdf).
- **OCP — Data Sanitization for the Circular Economy** — [opencompute.org/documents/data-sanitization-for-the-circular-economy-1-pdf](https://www.opencompute.org/documents/data-sanitization-for-the-circular-economy-1-pdf).
- **SiPearl** — [sipearl.com](https://sipearl.com) : Rhea1, 80 cœurs Arm Neoverse V1, HBM embarqué, tape-out **juin 2025**, serveur de référence « Seine » ; Rhea2 en chiplets. Déclaration du CEO (EETimes, « *SiPearl Tapes Out Rhea1 CPU, Closes Series A, Preps Series B* ») : une CPU **RISC-V** pour le HPC/les datacenters serait « un prototype de laboratoire », non commercialisable faute d'écosystème logiciel ; risque de dépendance à l'ISA Berkeley lui-même.
- **EPI / DARE / RISER** : programmes européens (RISC-V pour l'autonomie numérique, plates-formes cloud ouvertes OCP *Higher*).
- **OpenBMC / coreboot** — firmware ouverts pour la durabilité et la fin de support matériel.

### Cadre de référence interne (documents généralistes du dépôt)

`datacenter/souverainete-numerique-generalites.md` (5 couches, niveaux 1→4, grille d'évaluation) · `datacenter/conso-electrique/electricite-france-nucleaire.md` (mix électrique, facteurs de charge) · `datacenter/conso-electrique/optimisation-datacenter-parametres.md` (PUE, WUE, paramètres de dimensionnement) · `datacenter/eau/refroidissement-generalisation-300MW.md` (refroidissement) · `datacenter/nuisances-datacenter-11-axes.md` (nuisances) · `datacenter/bruit/infrasons-sante.md` et `datacenter/bruit/nuisances-sonores-sante.md` (vibrations, infrasons, santé).

---

## 14. Ce que ce document ne couvre pas

- **Aucun chiffrage de CAPEX/OPEX propre** : seuls des ordres de grandeur sourcés sont cités ; le reste reste à établir.
- **Aucun choix de site** : les critères sont posés, la sélection reste à faire sur la base de données réelles (P0).
- **Aucun avis juridique** : les points signalés (SCIC, 20 %, SecNumCloud, responsabilité pollution) exigent une confirmation professionnelle.
- **Aucun benchmark ROCm** : le protocole est décrit, les résultats ne sont pas produits.
- **Les affirmations sur les dates réglementaires 2026** (arrêté SecNumCloud, CADA, AI Act, transposition « droit à la réparation ») sont à re-vérifier à la date d'usage.

> **Document de travail — les points signalés comme incohérents (§9) et les seuils de passage doivent être tranchés par les porteurs du projet avant toute communication publique.**
