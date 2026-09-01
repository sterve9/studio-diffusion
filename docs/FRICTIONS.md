# Relevé de frictions — S25

Second livrable de la séance, aussi important que le premier.

`studio-diffusion` est le **premier projet neuf** déroulé en direct dans
`methode-architecte-ia`. Les précédents avaient été documentés après coup.
Tout ce qui accroche se note ici **au fil de l'eau, sans trier sur le
moment**. Le tri viendra après.

Deux origines distinctes, à ne pas confondre :

- **SYSTÈME** — l'application <https://methode.sterveshop.cloud>
- **MÉTHODE** — les documents de référence eux-mêmes

---

## F-01 — SYSTÈME — Une preuve publiée ne se corrige pas

**Connue avant la séance.**

Ni le titre, ni le résumé. Aucune reprise possible après publication.
`UpdateProofInput` est déclaré dans le code mais importé nulle part : une
preuve publiée ne peut être que retirée.

**Conséquence de travail** : relire intégralement avant de publier.

## F-02 — SYSTÈME — Une étape « Terminée » est définitive

**Connue avant la séance.**

Aucun retour arrière. Ne jamais terminer une étape « pour voir ».

**Conséquence de travail** : terminer les étapes au fur et à mesure, jamais
en rafale — le journal enregistre le moment du clic, et cocher 13 étapes
d'un coup fabriquerait une fausse cadence.

## F-03 — MÉTHODE — Le README canonique décrit une structure qui n'existe plus

**Trouvée le 01/09/2026, en cherchant le modèle de l'étape 1.**

`methode-architecte-ia/docs/methode/00.README.md` annonce **12 fichiers** :

```
07.Contrats_de_Donnees.md   09.Choix_Techno.md
10.Plan_Implementation.md   11.Plan_de_Tests.md
12.Journal_Decisions_Architecture.md
```

Le dossier réel en contient **13**, avec d'autres noms : `07.Contrats.md`,
`09.Choix_Technos.md`, `10.Justifications.md`, `11.Plan_Implementation.md`,
`12.Strategie_Tests.md`, `13.Documentation.md`.

Le README de la méthode est en retard sur sa propre méthode. Quelqu'un qui
suit le README crée les mauvais fichiers.

**Statut** : à corriger dans `methode-architecte-ia`, **hors séance** — ce
dépôt se lit, ne se modifie pas depuis ici.

## F-04 — MÉTHODE — Le projet modèle contient 4 renvois cassés

**Trouvée le 01/09/2026, en lisant le meilleur modèle disponible.**

`crm-prospection-ingrid` renvoie quatre fois à « **D-02 dans
`01.Besoin_Client.md`** » — dans `02.Probleme_Metier.md`, deux fois dans
`05.Cycle_de_Vie.md`, et dans `08.Architecture.md`.

Mesuré par `grep` : `01.Besoin_Client.md` **ne contient aucun `D-XX`**. Les
décisions vivent dans `10.Justifications.md`.

`git log` donne la cause : **un seul commit**, `bd5f8cb "Initial commit :
documentation méthode 13 étapes"`. Le projet a été documenté après coup, et
les renvois n'ont jamais été rejoués contre les fichiers finaux.

**C'est exactement le défaut que la S25 cherche à éliminer** en déroulant en
direct. Deux conséquences adoptées pour `studio-diffusion` :

1. Les décisions `D-XX` iront dans `10.Justifications.md`, jamais dans `01`.
2. Chaque renvoi inter-fichier est vérifié au moment où il est écrit.

**Statut** : renvois à corriger dans `crm-prospection-ingrid`, **hors
séance**.
