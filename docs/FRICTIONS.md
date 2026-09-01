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

## F-05 — SYSTÈME — Le formulaire de création exige l'étape 2 pour créer le projet

**Trouvée le 01/09/2026, en lisant le code avant de cliquer.**

`/dashboard/projects/new` demande deux champs, tous deux **obligatoires** :

- `name` — le nom du projet
- `business_problem` — « **Problème métier traité** »

`create-project.ts` refuse la création si le second est vide :
« Le problème métier traité est obligatoire. »

Or **le problème métier est l'étape 2**. Le système impose donc d'écrire
l'étape 2 pour avoir le droit de commencer l'étape 1 — alors que la RPC
`create_project_with_steps` clone justement les 13 étapes dont la première
s'appelle « Besoin Client » et se décrit : *« sans reformulation
prématurée »*.

**Le système contredit la méthode qu'il sert.**

**Atténuation** : `/dashboard/projects/[id]/edit` existe, le champ est donc
corrigible plus tard. Ce n'est pas irréversible comme F-01 et F-02.

**Piste** : rendre `business_problem` optionnel à la création et le remplir
au passage de l'étape 2, ou renommer le champ en quelque chose d'honnête à
l'instant où on le demande.

## F-06 — SYSTÈME — Un livrable ne peut être qu'une URL publique

**Trouvée le 01/09/2026, en lisant `add-deliverable-form.tsx`.**

Le formulaire d'ajout de livrable impose trois champs, dont deux requis :

- `title` — texte, requis
- `url` — `type="url"`, **requis**
- `description` — optionnel

Il n'existe **aucun moyen d'attacher un fichier**. Un livrable qui vit en
local — un `.md` dans un dépôt non poussé — ne peut pas être rattaché.

**Conséquence directe pour `studio-diffusion`** : `git remote -v` ne renvoie
rien. Le dépôt est local uniquement. **Le livrable de l'étape 1 ne peut pas
être attaché tant que le dépôt n'est pas poussé sur un hébergeur public.**

**Ce n'est pas forcément un défaut** — une preuve doit être consultable, donc
publique. Mais ça impose un prérequis que rien n'annonce : *avoir un dépôt
distant public avant de pouvoir déclarer le moindre livrable.*

## F-07 — MÉTHODE — Collision de vocabulaire sur le mot « Diffusion »

**Trouvée le 01/09/2026.**

« Diffusion » désigne déjà **M4**, un module existant du système
(`/dashboard/diffusion`, `src/modules/m4-diffusion/`). Le nouveau projet
s'appelle `studio-diffusion`.

Deux choses différentes portent le même nom. Au moment de l'étape 8, la
question « le code va-t-il dans M4 ou dans une application séparée ? » sera
d'autant plus confuse que les deux s'appellent pareil.

**Statut** : à surveiller. `studio-diffusion` reste un titre de travail.

## F-08 — SYSTÈME — La liste des projets est noyée sous les projets de test

**Trouvée le 01/09/2026, en ouvrant `/dashboard/projects` pour créer le
projet de la séance.**

**21 projets `[E2E] Chaîne critique …`** occupent la liste, contre 4 projets
réels ou semi-réels. Le premier vrai projet est invisible sans faire défiler
tout l'écran.

### Ce qui a été mesuré

- `listProjects()` fait un `.select('*')` **sans aucun filtre**, trié par
  `created_at DESC`. Les projets de test sortent donc en premier, étant les
  plus récents.
- **Aucune suppression de projet n'existe** dans M1 : `create-project`,
  `update-project`, `archive-project`, et rien d'autre.
- Le système **a déjà tranché ce débat ailleurs** :
  `m5-mesures/domain/event-rules.ts` définit `E2E_PROJECT_PREFIX = '[E2E]'`
  et `/dashboard/mesures` écarte les événements de test **à la lecture,
  jamais de la base**. Le principe est décidé et implémenté — il n'a jamais
  été appliqué à la liste des projets.

### Confirmation d'un angle mort de la S24

`[E2E] Chaîne critique 1788032168183` est bien au statut **Idée** au lieu
d'`Archivé` — l'angle mort n°5 de la S24, constaté en direct à l'écran.

### La cause racine, plus profonde que l'affichage

**Le test E2E écrit dans la base de production.** Nettoyer la liste traite le
symptôme : le prochain run recréera des projets. Supprimer ne règle donc
rien durablement, et se heurterait au journal `events` append-only qui
référence ces projets.

**Statut** : chantier réel, mais dans `methode-architecte-ia` — **hors
périmètre de ce dépôt**, qui ne modifie pas les dépôts de référence.

### Question ouverte, volontairement non tranchée le 01/09/2026

**Pourquoi le test E2E écrit-il dans la base de production ?**

Deux réponses possibles, toutes deux à instruire ailleurs :

1. Une base de test séparée — coûteuse, mais elle règle le problème à la
   source et rendrait aussi mesurable l'isolation RLS entre utilisateurs
   (angle mort n°2 de la S24 : un seul compte existe, les policies ont été
   relues et jamais éprouvées).
2. Un nettoyage en fin de run — moins cher, mais il se heurte au journal
   `events` append-only, qui référence les projets créés.

Décidé le 01/09/2026 : **on trace, on ne tranche pas.** C'est une décision
d'architecture de test, trop lourde pour être prise en passant pendant une
séance dont l'objet est ailleurs.

**Correctif retenu à court terme** : appliquer à `listProjects` le filtre que
M5 applique déjà aux événements — écarter `[E2E]` à la lecture, avec un
`?tests=1` pour les revoir. Aucune suppression, aucune perte, et le prochain
run E2E ne repollue pas l'affichage.

### F-05, suite — ce n'est pas l'écran, c'est le schéma

**Mesuré le 01/09/2026, après que le client a identifié la friction seul
devant le formulaire.**

La contradiction est démontrable avec les seuls documents du système.

`05.Cycle_de_Vie.md` définit les états du Projet :

| | État | Définition, mot pour mot |
|---|---|---|
| E1 | `Idée` | « Le projet est formulé mais pas encore engagé. Le besoin existe, **rien n'est formalisé**. » |
| E2 | `Cadré` | « Le besoin client et le problème métier sont définis et documentés. » |

Et la transition T1 `Idée` → `Cadré` : « Le besoin client **et le problème
métier** sont formalisés et documentés ».

`20260816153643_create_projects_table.sql` déclare :

```sql
business_problem  text NOT NULL,
```

Un projet naît à l'état `Idée`. **La base exige donc à E1 une information que
le cycle de vie ne produit qu'à T1.**

### La cause, mécanique

`03.Objets_Metier.md` liste « Problème métier traité » comme attribut du
Projet. C'est exact — l'erreur n'est pas là.

Modéliser un objet demande deux questions ; une seule a été posée :

1. ✅ Quels attributs cet objet porte-t-il ?
2. ❌ **À partir de quel moment de son cycle de vie chaque attribut
   devient-il connaissable ?**

Un `NOT NULL` est une promesse : « cette information existe dès la naissance
de l'objet ». Ici la promesse est fausse. Le formulaire ne fait que la
transmettre à l'utilisateur.

### Correction identifiée, non appliquée

- À la création, demander le **besoin client brut** — présent dès `Idée`,
  puisque « le besoin existe ».
- Rendre `business_problem` **nullable**, et le remplir au passage à `Cadré`,
  c'est-à-dire quand l'étape 2 de la méthode est écrite.

Migration + révision de `03.Objets_Metier.md` : relève de RM-03. **Hors
périmètre de ce dépôt**, et non tranché aujourd'hui.

### Leçon transposable

Un modèle d'objet qui ignore le **moment** où chaque attribut devient
connaissable produit des contraintes de base qui forcent l'utilisateur à
mentir. Ici, le système qui sert la méthode obligeait à sauter une étape de
cette même méthode.

C'est le genre de défaut qu'aucune relecture de schéma ne révèle, et qu'un
seul usage réel fait apparaître en trente secondes.
