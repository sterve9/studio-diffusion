# Studio Diffusion — Contexte projet

## ⚠️ Ce projet est au tout début. Il n'a pas encore de solution.

`studio-diffusion` est un **titre de travail**, choisi pour nommer un dossier —
pas une décision de conception. Ce qui sera construit n'est pas décidé, et ne
doit pas l'être avant d'avoir traversé les étapes de la méthode.

**Il n'y a pas de code dans ce dépôt, et il ne doit pas y en avoir avant
l'étape 11.** Le travail commence par `docs/methode/01.Besoin_Client.md`.

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

### Ce que ces chiffres disent

**Deux causes, une seule visible :**

1. **Le hook.** Le public part à 2 secondes — avant d'avoir appris quoi que ce
   soit. Il part sur la promesse, pas sur le contenu. TikTok lit cet abandon
   précoce comme un verdict et cesse de distribuer.
2. **La durée, invisible.** À contenu strictement identique, 34,5 s regardées
   font **21 %** sur une vidéo de 2 min 41, mais **77 %** sur une vidéo de 45 s.
   Le format transforme une attention correcte en mauvais bulletin.

⚠️ **Contre-indice relevé le 01/09/2026, à ne pas enterrer.** Cette vidéo est
**une des plus longues du compte**, et c'est **la plus vue**. La corrélation
va donc dans le sens **inverse** de la thèse « raccourcir ».

Ce qui reste vrai : la durée écrase mécaniquement le **pourcentage de
rétention**, c'est de l'arithmétique. Ce qui n'est **pas** établi : que
raccourcir augmente les **vues**. Aucune donnée du compte ne le démontre —
il faudrait comparer durée et vues sur les 16 vidéos, ce qui n'a pas été
fait.

**Ne pas confondre les deux.** Le raccourcissement est une hypothèse
plausible, pas une cause prouvée. C'est précisément ce que le test des
5 vidéos à 45 s doit trancher.

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

**Ce que publie l'auteur** : une série vidéo racontant la construction de
`crm-prospection-ingrid` selon la méthode, étape par étape (au 31/08/2026 :
l'identification de l'objet central).

**Ses trois canaux :**

- **YouTube** — l'explication complète. C'est la preuve elle-même.
  Chaîne créée, **encore vide**. Plus gros actif inutilisé.
- **TikTok** — seul canal actif aujourd'hui. 16 vidéos.
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

Deux frictions déjà connues :

1. **Une preuve publiée ne se corrige pas** — ni titre, ni résumé. Relire avant
   de publier.
2. **Une étape « Terminée » est définitive.** Aucun retour. Ne pas terminer une
   étape « pour voir ».

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

## 🚧 La décision à NE PAS prendre avant l'étape 8

> Le code atterrira-t-il **dans le module M4** de `methode-architecte-ia`, ou
> dans une **application séparée** consommant les preuves par contrat ?

C'est une question d'architecture. La trancher maintenant, ce serait choisir la
solution avant d'avoir écrit le besoin — exactement ce que la méthode interdit.
Si elle revient avant l'étape 8, la reporter.

---

## Où trouver les chiffres à jour

TikTok : profil → menu **☰** → **Outils de créateur** → **TikTok Studio** →
onglet **Contenu**. La courbe de rétention y est donnée **seconde par seconde**.
(Pas dans « Paramètres et confidentialité ».)

**Correction en cours, hors séance** : les 5 prochaines vidéos sont publiées en
**45 secondes, hook réécrit, version longue sur YouTube**. Si la rétention passe
de 21 % à ~60 %, la cause est **prouvée** au lieu d'être supposée — et l'étape 2
s'appuiera sur des données fraîches. Vérifier où en est ce test.

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
