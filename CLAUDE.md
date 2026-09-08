# Studio Diffusion — Contexte projet

## ⚠️ Ce projet est au tout début. Il n'a pas encore de solution.

`studio-diffusion` est un **titre de travail**, choisi pour nommer un dossier —
pas une décision de conception. Ce qui sera construit n'est pas décidé, et ne
doit pas l'être avant d'avoir traversé les étapes de la méthode.

**Il n'y a pas de code dans ce dépôt, et il ne doit pas y en avoir avant
l'étape 11.**

**Où en est la méthode** — étape 1 (Besoin Client) **terminée** le 01/09/2026,
livrable attaché et publié. **Les étapes 2 à 8 ont été écrites le
08/09/2026** : la phase COMPRENDRE (01→05) et la phase CONCEVOIR (06→08) sont
closes, décision d'architecture comprise. La phase CHOISIR (09→10) suit.

⚠️ **Écrire un fichier et terminer l'étape dans le système sont deux gestes
distincts.** Le second est définitif (`F-02`) et enregistre l'heure du clic. Le point de reprise à jour est
`docs/REPRISE.md` — **à lire en premier**, avant ce fichier-ci.

---

## Le problème, mesuré avant d'être formulé

Ce projet naît d'un constat chiffré, relevé le 31/08/2026 sur les statistiques
TikTok réelles de l'auteur — pas d'une intuition.

**Vidéo la plus performante du compte :**

| Mesure | Valeur |
|---|---|
| Vues | 425 |
| Temps de visionnage moyen | 34,5 s |
| Part moyenne de la vidéo regardée | **21 %** |
| Vidéo vue en entier | 8,32 % |
| Décrochage massif | **à 0:02** |
| Nouveaux abonnés | 5, soit **~1,18 %** |
| Total du compte | 16 vidéos → 30 abonnés |

Durée de la vidéo : **2 min 41** — ✅ **mesurée le 01/09/2026**, lue
directement dans les analytiques.

La déduction faite le 31/08 (34,5 ÷ 0,21 → ~2 min 45) annonçait 164 s ;
la mesure donne 161 s. Écart : 3 secondes, moins de 2 %. Contrôle inverse :
34,5 ÷ 161 = **21,4 %**, ce qui correspond aux 21 % affichés. **L'hypothèse
est confirmée, elle n'est plus une hypothèse.**

### Ce que ces chiffres disent — révisé le 02/09/2026

**Deux causes étaient soupçonnées. La première a été démentie par la mesure.**

1. ⚠️ **Le décrochage à 0:02 n'est pas un diagnostic. C'est une constante du
   compte.** Vérifié le 02/09 sur plusieurs vidéos : **0:02 partout, parfois
   0:01**, tous formats et tous hooks confondus — y compris sur la vidéo du
   test au hook entièrement réécrit. Un indicateur qui ne varie jamais ne
   mesure rien.
   **Cela n'innocente pas le hook.** Cela dit que *cette mesure-là* ne peut
   rien en dire. Ce qu'il aurait fallu relever est la **profondeur** de la
   chute — combien de spectateurs sur 100 restent à 0:03 — et non son instant.
   Voir `docs/TEST_5_VIDEOS.md`, section « C1 déclaré aveugle ».
2. **La durée, invisible — toujours vraie, et purement arithmétique.** À
   attention identique, 34,5 s regardées font **21 %** sur 2 min 41 et
   dépasseraient **100 %** sur 31 s. Le format transforme une attention
   correcte en mauvais bulletin. Mais c'est une division, pas un résultat.

### Les cinq vidéos mesurées à ce jour

| Durée | Vues | Part moyenne | Vue en entier | 0:06 |
|---|---|---|---|---|
| 161 s — référence, 31/08 | **425** | 21 % | 8,32 % | — |
| 90,30 s — témoin, 31/08 | **238** | 37 % | 12,58 % | — |
| 31 s — n°1, 01/09 | **182** | 85 % | 18,88 % | 45 % |
| 30,50 s — n°2, 02/09 | **445** | 58 % | 11,42 % | 32 % |
| 27 s — n°3, 03/09 | **196** | — | — | 27 % |

⚠️ **La colonne « décrochage » a disparu**, et c'est volontaire : elle valait
0:02 partout, sur toutes les vidéos du compte. C1 a été déclaré aveugle le
02/09. Ce qui varie, et donc ce qui se mesure, est la **profondeur** de la
chute — d'où la colonne 0:06.

⚠️ **Contre-indice, relevé le 01/09 et renforcé le 02/09 : plus la vidéo est
courte, moins elle fait de vues.** La corrélation va dans le sens **inverse**
de la thèse « raccourcir ». Trois points ne font pas une loi, la n°1 est
incomplète, et le contenu diffère à chaque fois — **rien n'est tranché.**

Ce qui reste établi, et seulement cela : la durée écrase mécaniquement le
**pourcentage de rétention**. Ce qui n'est **pas** établi : que raccourcir
augmente les **vues**. Il faudrait comparer durée et vues sur l'ensemble des
vidéos du compte, ce qui n'a toujours pas été fait.

**Ne pas confondre les deux.** Le raccourcissement est une hypothèse
plausible, pas une cause prouvée. C'est ce que le test des 5 vidéos — publiées
à **~31 s**, pas 45 — doit trancher.

**Ce qui n'est PAS le problème : la conversion.** ~1 % d'abonnement pour qui
regarde, c'est sain. Ceux qui voient suivent. Trop peu de gens voient.

**Arithmétique de l'objectif** — à ~1 %, 1000 abonnés demandent environ
**100 000 vues cumulées**. À 425 vues/vidéo il faudrait plus de 200 vidéos ;
à 5 000 vues, une vingtaine. **Le levier est la portée par vidéo, pas le
nombre de vidéos.**

### La formulation provisoire du besoin

> Les preuves de compétence existent et sont bonnes. Elles ne circulent pas.
> Le système qui les produit sait les diffuser en **texte** (LinkedIn, X) ;
> le canal réel est la **vidéo**.

⚠️ Cette formulation est un point de départ, pas l'étape 1. Elle est déjà
teintée de solution. **L'étape 1 reste à écrire.**

---

## Contexte utile

**Ce que publie l'auteur** — ⚠️ **cela a changé le 06/09/2026.**

La série « jour N », qui racontait la construction de `crm-prospection-ingrid`
étape par étape, est **abandonnée**. Le motif est structurel : « jour 7 : les
contrats de données » sert au spectateur l'épisode 7 d'une histoire qu'il n'a
pas commencée. Sur « Pour toi », une vidéo doit tenir seule.

Remplacée par des **tutoriels autonomes** — construire un CRM dans Google
Sheets, de zéro, en direct. Chacun porte sa promesse dans son titre et ne
suppose aucun des autres.

**Ses trois canaux :**

- **YouTube** — chaîne `IA Architecte`. **Première vidéo publiée le
  07/09/2026** : *CRM Google Sheets : colorer chaque ligne selon le statut*,
  4 min 23, format 16:9. Validation de chaîne en cours.
  ⚠️ **La règle « démarrer au jour 1 » (N-04) est caduque** : elle valait pour
  une série, et un tutoriel n'a pas de jour 1. C'est le pivot du 06/09 qui a
  fait tomber la contrainte, pas une décision prise contre elle.
- **TikTok** — **le total exact n'a jamais été relu à l'écran.** Autour de 20
  vidéos, sans plus de précision. ⚠️ Ne pas citer de chiffre sans être allé le
  lire. Six extraits verticaux du tuto 01 sont en cours de publication depuis
  le 07/09.
- **LinkedIn** — publication irrégulière. C'est pourtant le canal où le
  public professionnel visé se trouve déjà.

⚠️ **Garde-fou affaibli** : **le client de ce projet, c'est l'auteur
lui-même.** Il n'y a pas de tiers pour reprendre l'architecte quand celui-ci
glisse vers sa solution. Seule la mesure remplace ce contre-pouvoir — voir
`docs/methode/01.Besoin_Client.md`.

Les objectifs commerciaux et la tension entre les audiences visées sont
suivis hors dépôt. Ils n'entrent ici que s'ils deviennent une contrainte de
conception, et alors ils sont écrits comme telles.

---

## Le système dans lequel ce projet vit

Ce projet sera suivi dans **Méthode Architecte IA** —
<https://methode.sterveshop.cloud> — qui produit les preuves publiques.

C'est le **premier projet neuf** à y être déroulé en direct, dans l'ordre des
étapes. Les précédents avaient été documentés après coup.

**Second livrable de la séance, aussi important que le premier : le relevé des
frictions** rencontrées en utilisant ce système pour de vrai. Tout noter au fil
de l'eau, sans trier sur le moment.

**Le relevé vit dans `docs/FRICTIONS.md`** — **onze** frictions, numérotées
F-01 à F-12. ⚠️ **Il n'y a pas de F-11** : la numérotation saute, et les
identifiants ne se renumérotent jamais. Compté le 08/09/2026, la mention
« douze » était fausse. Ne pas les dupliquer ici. Les deux qui commandent la conduite au
quotidien :

1. **F-01 — une preuve publiée ne se corrige pas**, ni titre, ni résumé.
   Relire avant de publier. Aggravée par **F-09** : le bouton « 🌟 Preuve
   publique » crée **et publie** en un seul geste, sans le dire.
2. **F-02 — une étape « Terminée » est définitive.** Aucun retour. Ne pas
   terminer une étape « pour voir ».

Et une discipline : **terminer les étapes au fur et à mesure, jamais en
rafale.** Le journal du système enregistre le moment du clic — cocher 13 étapes
d'un coup fabriquerait une fausse cadence.

---

## Les 13 étapes, et où trouver les références

Structure de fichiers **figée**, contenu propre à chaque projet :

```
01.Besoin_Client.md        08.Architecture.md
02.Probleme_Metier.md      09.Choix_Technos.md
03.Objets_Metier.md        10.Justifications.md
04.Objet_Central.md        11.Plan_Implementation.md
05.Cycle_de_Vie.md         12.Strategie_Tests.md
06.Composants.md           13.Documentation.md
07.Contrats.md
```

Deux références sur cette machine, à lire avant d'écrire :

- **La méthode canonique** —
  `C:/Dev/02_Développement/methode-architecte-ia/docs/methode/`
  Contient aussi `99_Prompt_de_reprise.md`, qui porte l'objectif détaillé et
  le plan de la séance en cours.

- **Un exemple abouti sur un projet extérieur** —
  `C:/Dev/02_Développement/crm-prospection-ingrid/docs/methode/`
  La méthode y est appliquée en entier. **C'est le meilleur modèle.**

⚠️ Ces deux dépôts se **lisent**, ne se modifient pas depuis ce projet.

---

## ✅ La décision d'architecture, prise le 08/09/2026

> **Une application séparée**, consommant les preuves par contrat.

`methode-architecte-ia` produit les preuves. `studio-diffusion` les diffuse sur
**YouTube et TikTok**. Aucune base, aucun déploiement, aucune authentification
partagés — seulement le contrat `CT-01`.

⚠️ **LinkedIn et X restent dans M4.** L'étape 2 établit que LinkedIn n'est pas
le problème ; reconstruire ce qui fonctionne serait du travail sans bénéfice.
M4 rapporte ce qu'il a diffusé via `CT-01`, ce qui garde le calcul des états
possible.

**Le motif décisif est `F-12`** : dans `methode-architecte-ia`, un jeton expiré
a déjà tout arrêté, pages publiques comprises. Y ajouter les OAuth YouTube et
TikTok reviendrait à multiplier la cause d'une panne déjà subie, dans
l'application qui porte les preuves.

> **Une preuve doit pouvoir être publiée même quand la diffusion est cassée.**

Options écartées et raisonnement complet : `docs/methode/08.Architecture.md`.

---

## Où trouver les chiffres à jour

TikTok : profil → menu **☰** → **Outils de créateur** → **TikTok Studio** →
onglet **Contenu**. La courbe de rétention y est donnée **seconde par seconde**.
(Pas dans « Paramètres et confidentialité ».)

**Le test des 5 vidéos est CLOS depuis le 08/09/2026**, arrêté à trois
vidéos sur cinq. Journal complet et raisons de l'arrêt dans
`docs/TEST_5_VIDEOS.md`, section « Clôture ».

Trois motifs : la variabilité écrase l'effet mesuré (**N-10**, 182 contre 445
vues sur deux vidéos jumelles), C1 était aveugle, et le pivot du 06/09 rend le
protocole intenable — les n°4 et n°5 n'existeront pas.

⚠️ **Ne pas le rouvrir.** Ce qu'il a produit et ce qu'il n'a pas tranché sont
écrits ; le reste serait de l'attente.

⚠️ **Ne jamais écrire qu'une rétention à 60 % prouverait quoi que ce soit.**
Sur une vidéo trois fois plus courte, la part moyenne regardée monte par simple
division. La n°1 a affiché **83 %** — et ça ne prouve rien. Le seul critère qui
mesure le vrai objectif, la **portée**, est le nombre de vues.

⚠️ **Ne jamais déduire une durée d'un pourcentage.** Deux tentatives, deux
échecs : 1,9 % d'erreur le 01/09, **5,4 % le 02/09**. On lit à l'écran.

⚠️ **Ne jamais écrire une date ou une échéance sans avoir lu l'horloge.**
Ajouté le 03/09/2026 après une erreur réelle : « demain matin » avait été
compris comme le lendemain alors qu'il était une heure du matin.

---

## Contrat de collaboration (à respecter à chaque réponse)

- Expliquer chaque nouveau concept avant le code ; avancer par micro-étapes
  validées une par une.
- Fichiers complets uniquement — jamais de code en parcelle.
- Règle zéro invention : vérifier la doc officielle avant tout nom
  d'API/fonction.
- **Ne jamais déduire un comportement — aller le mesurer.** Un écran qui dit
  « c'est bon » n'est pas une mesure.
- **Ne jamais construire sur une prémisse non vérifiée.** Deux hypothèses ont
  déjà été démolies pendant le cadrage de ce projet, faute d'avoir demandé
  avant de raisonner.
- Donner une recommandation justifiée (A/B/C + reco) à chaque choix structurant.
- Commits atomiques ; ne pas découper les enchaînements Git standards.
- Refuser toute tâche sans valeur métier claire.
