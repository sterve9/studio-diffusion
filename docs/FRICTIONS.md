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

### F-05, précision — la friction est confinée à la porte d'entrée

**Observée par le client le 01/09/2026, une fois le projet créé.**

Passé le formulaire de création, le système est **fidèle à la méthode** :

- Étape 1, « Besoin Client » — *« Formaliser le besoin brut exprimé par le
  client tel qu'il a été énoncé, sans reformulation prématurée. »*
- Étape 2, « Problème Métier » — *« Transformer le besoin brut en problème
  métier mesurable et actionnable. »*

L'ordre est juste, les intitulés sont justes, l'enchaînement est juste. Seul
le formulaire de création demandait l'inverse de ce que le canevas qu'il
génère va exiger trois secondes plus tard.

**Conséquence sur l'ampleur du correctif** : c'est un champ à déplacer, pas
une méthode à revoir. Le diagnostic passe de « le système contredit la
méthode » à « le système contredit la méthode **à sa porte d'entrée
uniquement** ».

## F-09 — SYSTÈME — « Créer une preuve » publie immédiatement, sans le dire

**Trouvée le 01/09/2026, en mesurant le bouton avant de cliquer.**

La chaîne réelle, depuis un livrable :

| Action | Effet | Réversible ? |
|---|---|---|
| **Publier** (livrable) | `Brouillon` → `Publié`. Statut interne. Ne publie rien vers l'extérieur. Débloque le bouton suivant. | ✅ **Oui** — le bouton devient « Dépublier » |
| **Créer une preuve** | Crée la preuve **et la publie** sur `/p/{slug}` | ❌ **Non** |

`create-proof-button.tsx` enchaîne sans interruption :

```ts
const result = await createProof({...})
const publishResult = await updateProofStatus(result.proofId, 'publié')
```

**Le statut `'publié'` est passé en dur, immédiatement après la création.**
Il n'existe aucun état intermédiaire, aucune relecture, aucune confirmation.

Le libellé du bouton dit « Créer une preuve ». Il devrait dire « Créer **et
publier** ». Combiné à F-01 — une preuve publiée ne se corrige ni en titre ni
en résumé, et `UpdateProofInput` n'est importé nulle part — c'est l'action la
plus dangereuse du système, et la seule qui ne s'annonce pas.

**Correction identifiée** : soit renommer le bouton pour qu'il dise ce qu'il
fait, soit ne pas appeler `updateProofStatus` dans la foulée et laisser la
preuve en brouillon, avec un second geste explicite pour publier.

**Note** : `updateProofStatus` existe déjà et prend le statut en paramètre.
Le brouillon de preuve est donc à portée de main — c'est l'enchaînement
automatique qui le supprime, pas une limite du modèle.

## F-10 — SYSTÈME — Une étape peut être terminée à vide

**Trouvée le 01/09/2026, en lisant `update-step-status.ts`.**

`updateStepStatus` valide uniquement la transition de statut
(`assertCanStepTransition`). **Aucune vérification sur les livrables** : ni
qu'il en existe un, ni qu'il soit publié.

Une étape peut donc être marquée `Terminée`, émettre l'événement CT-10
« Étape terminée » vers M5, et alimenter les statistiques de cadence — **sans
qu'aucun livrable ne l'atteste**.

Combiné à F-02 (l'état `Terminée` est terminal, aucun retour), une étape
terminée à vide l'est pour toujours.

**Question ouverte, non tranchée** : est-ce un défaut ou une liberté
volontaire ? Certaines étapes de la méthode peuvent légitimement ne rien
produire d'attachable. Mais alors la mesure de cadence compte des étapes qui
ne prouvent rien, et le système mesure des clics plutôt que du travail.

### F-09, correction — le libellé réel est encore moins parlant

**Constaté à l'écran le 01/09/2026, une fois le livrable publié.**

Le bouton ne s'intitule pas « Créer une preuve » comme le laissait penser le
nom du composant `CreateProofButton`. À l'écran, il affiche :

> 🌟 **Preuve publique**

**Aucun verbe.** Un utilisateur ne peut pas deviner qu'un clic déclenche une
action, encore moins une action irréversible qui met un contenu en ligne.
Le libellé ressemble à une étiquette ou à un lien de consultation.

Cela aggrave F-09 plutôt que de la nuancer : l'action la plus définitive du
système porte le libellé le moins explicite de toute l'interface.

## F-12 — SYSTÈME — L'angle mort n°6 de la S24 s'est manifesté en direct

**Rencontrée le 01/09/2026 au soir, en tentant de vérifier F-08 en local.**

Le prompt de reprise S24 listait, en angle mort n°6 :

> « Le refresh de session **après expiration réelle du jeton** n'est toujours
> pas couvert. `session.spec.ts` prouve la survie à un rechargement immédiat,
> pas au renouvellement effectif. **Premier suspect en cas de déconnexion
> inattendue.** »

### Ce qui a été mesuré

Serveur `next dev` lancé, démarrage nominal (`Ready in 1350ms`). Puis :

| Moment | Route | Résultat |
|---|---|---|
| T+0 | `GET /` | **307** en 150 ms — normal |
| T+0 | log serveur | `AuthApiError: Invalid Refresh Token: Refresh Token Not Found` |
| T+2 min | `GET /login` | **aucune réponse**, timeout à 60 s, et **rien dans le log** |
| T+3 min | `GET /p` (route publique) | **aucune réponse**, timeout à 25 s |
| T+3 min | `GET /` | **aucune réponse**, timeout à 15 s |
| T+3 min | processus | **4,91 s de CPU en 5 s** — un cœur à 100 %, en continu |

Le serveur passe donc de « répond en 150 ms » à « ne répond plus du tout,
route publique comprise », tout en brûlant un cœur entier.

### Ce que ça dit

Un jeton de rafraîchissement invalide ne provoque pas une déconnexion propre :
il met le serveur dans un état où **plus rien n'est servi**, pas même les
pages qui ne demandent aucune authentification.

L'angle mort n°6 annonçait « premier suspect en cas de déconnexion
inattendue ». Le symptôme réel est pire qu'une déconnexion : c'est un déni de
service complet.

⚠️ **Observé en `next dev` uniquement.** Non reproduit en production, où le
comportement peut différer (Vercel isole chaque requête dans une lambda). **À
ne pas transposer sans mesure.**

### Ce que ça bloque

La vérification à l'écran de `DT-S25-01` (le filtre des projets `[E2E]`) n'a
pas pu être faite en local. Elle reste à faire.

### F-06, suite — la friction est contournée, pas résolue

**Constaté le 02/09/2026.**

Le dépôt a désormais un distant public — `github.com/sterve9/studio-diffusion`
— et le livrable de l'étape 1 a pu être attaché sous forme d'URL.

**Le blocage est levé en pratique. La friction reste entière** : rien dans
le système n'annonce qu'il faut un dépôt distant public avant de pouvoir
déclarer le moindre livrable. Le formulaire demande une URL sans dire d'où
elle doit venir.

**Statut** : de « bloquante » à **contournée**. À conserver au relevé — c'est
un prérequis silencieux, pas un défaut disparu.
