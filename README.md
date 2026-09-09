# studio-diffusion

**Diffuser une preuve produite par la méthode sur les canaux où le public se
trouve.**

Ce dépôt applique les **13 étapes de la méthode Architecte IA** à un projet
neuf, en public, dans l'ordre — et il garde la trace de ce que ça coûte
réellement.

---

## Le problème, en une phrase

> Le système s'arrête à la preuve. Tout ce qui la rend publiable sur une
> plateforme vidéo — la structure, le script lisible, le titre, la
> description, les balises — n'est produit par rien, et recommence
> entièrement à chaque fois.

Trois canaux, **un seul servi** : LinkedIn accepte la preuve telle quelle,
parce que c'est du texte. YouTube et TikTok parlent une langue que le système
n'écrit pas — et ce sont eux, les canaux réels.

---

## Où en est le projet

| Phase | Étapes | État |
|---|---|---|
| 1 — COMPRENDRE | [01](docs/methode/01.Besoin_Client.md) → [05](docs/methode/05.Cycle_de_Vie.md) | ✅ |
| 2 — CONCEVOIR | [06](docs/methode/06.Composants.md) → [08](docs/methode/08.Architecture.md) | ✅ |
| 3 — CHOISIR | [09](docs/methode/09.Choix_Technos.md) → [10](docs/methode/10.Justifications.md) | ✅ |
| 4 — CONSTRUIRE | [11](docs/methode/11.Plan_Implementation.md) · [12](docs/methode/12.Strategie_Tests.md) | ✅ · 13 à écrire |

**Décision d'architecture** *(étape 8)* — une application séparée, consommant
les preuves par contrat. Le motif décisif vient d'une friction réelle : dans
l'application qui produit les preuves, un jeton expiré a déjà tout arrêté,
pages publiques comprises.

> **Une preuve doit pouvoir être publiée même quand la diffusion est cassée.**

---

## Le code

**[`app/teleprompteur.html`](app/teleprompteur.html)** — jalon `J1`.

Une page autonome : caméra frontale en plein écran, script superposé **dans le
tiers haut, là où se trouve l'objectif**. Ni serveur, ni base, ni compte.

**→ [Ouvrir le téléprompteur](https://sterve9.github.io/studio-diffusion/app/teleprompteur.html)**

Ce qu'elle a d'unique : elle **distingue ce qui se dit de ce qui se vérifie**.
`#` un titre · `!` un piège · `>` un point de contrôle — ces deux derniers
s'affichent petits et décalés, impossibles à lire par erreur.

---

## Comment lire ce dépôt

| Chemin | Ce qu'on y trouve |
|---|---|
| [`docs/REPRISE.md`](docs/REPRISE.md) | **à lire en premier** — l'état réel, daté |
| [`docs/methode/`](docs/methode/) | les 13 étapes |
| [`docs/CARNET.md`](docs/CARNET.md) | les notes de travail, `N-01` à `N-12` |
| [`docs/FRICTIONS.md`](docs/FRICTIONS.md) | ce qui a coincé en utilisant le système pour de vrai |
| [`docs/TEST_5_VIDEOS.md`](docs/TEST_5_VIDEOS.md) | un test mené, puis **clos sans conclure**, avec ses raisons |
| [`docs/productions/`](docs/productions/) | les artefacts de tournage |
| [`docs/ressources/`](docs/ressources/) | zone de gel — ressources datées, avec leur étape de déblocage |

---

## Ce que ce dépôt a d'inhabituel

**Les erreurs y restent écrites, avec leur date et ce qui les a corrigées.**

Deux affirmations écrites le 08/09 ont été démenties le même jour, et
corrigées dans leur fichier plutôt que réécrites en silence. Un test de cinq
vidéos a été arrêté à trois, parce que la variabilité écrasait l'effet mesuré.

Un lecteur qui arrive plus tard voit le raisonnement **et** ce qui l'a
redressé.
