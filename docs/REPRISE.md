# Point de reprise — mis à jour le 02/09/2026

À lire en premier au démarrage de la prochaine session.

---

## 1. Où démarrer

> **Toujours dans `studio-diffusion`.**
> Les autres dépôts, on y va pour une raison précise, on fait la chose, on revient.

C'est ici qu'on réfléchit. Ailleurs, on exécute.

## 2. Les quatre dépôts

| Dépôt | Rôle | GitHub |
|---|---|---|
| **`studio-diffusion`** | 🏠 **La maison.** Les 13 étapes de la méthode, les frictions, le carnet, le journal du test vidéo. | ✅ public |
| `methode-architecte-ia` | 🔧 **L'outil.** L'application derrière `methode.sterveshop.cloud`. On y va pour la réparer. | ✅ |
| `remotion-brand` | 🎬 **Les visuels.** Les compositions Remotion des B-roll. | ✅ privé |
| `crm-prospection-ingrid` | 📖 **Le modèle, en lecture seule.** Ne jamais modifier. | ✅ |

Les 14 autres dossiers de `02_Développement` ne concernent pas ce travail.

## 3. La première chose à faire

**Dépouiller la vidéo n°1 du test.** Publiée le 01/09 à 17h02, elle atteint
48 heures le **03/09 à 17h02**. C'est ce qui débloque l'étape 2.

TikTok Studio → Contenu → la vidéo → la courbe seconde par seconde.

Huit mesures à reporter dans `TEST_5_VIDEOS.md` :

vues · temps de visionnage moyen · part moyenne regardée · vue en entier ·
seconde du décrochage · nouveaux abonnés · commentaires ·
**spectateurs restants à 0:03**

⚠️ **Ne pas dépouiller avant 17h02.** C3 est libellé « vues à 48 h ». Le
relevé J+1 du 02/09 est déjà consigné, dans une section séparée qui ne valide
aucun critère.

### Ce qui a changé le 02/09 : C1 est aveugle

Le critère décisif du test **ne mesure rien**. Vérifié sur plusieurs anciennes
vidéos : le décrochage vaut **0:02 partout, parfois 0:01**, quels que soient
la durée et le hook.

- **C1 reste écrit tel quel** dans `TEST_5_VIDEOS.md`. On ne réécrit pas un
  critère après avoir vu les résultats.
- **Ne pas lire** « 0:02 partout → le hook ne sert à rien ». C'est
  l'instrument qui est sourd, pas le hook qui a échoué.
- Ce qu'il aurait fallu mesurer : la **profondeur** de la chute, pas son
  instant. Relevé **pour information** à partir du 03/09, et destiné à devenir
  le C1 du test suivant.

### Où en est le relevé J+1 (02/09, ne conclut rien)

| | Référence (161 s) | Témoin (90,30 s) | N°1 test (31 s, J+1) |
|---|---|---|---|
| Vues | 425 | 238 | 156 |
| Temps de visionnage | 34,5 s | 35,2 s | 25,9 s |
| Part moyenne | 21 % | 37 % | 83 % |
| Vue en entier | 8,32 % | 12,58 % | 17,08 % |
| Décrochage | 0:02 | 0:02 | 0:02 |
| Abonnés | 5 | 1 | 0 |

⚠️ **Le contre-indice se renforce : plus court = moins de vues.** Trois
points ne font pas une loi, et la n°1 est incomplète. **Rien n'est tranché.**

## 4. Ce qui bloque l'étape 2

Trois mesures manquaient le matin du 01/09. **Il n'en reste qu'une, et elle
tombe le 03/09 à 17h02.**

| Mesure | État |
|---|---|
| Durée réelle de la vidéo de référence | ✅ **2 min 41**, lue directement |
| Ce que M4 sait diffuser | ✅ **`'linkedin' \| 'x'`, texte uniquement.** Ni TikTok ni YouTube. |
| Vidéo témoin du 31/08 | ✅ **relevée le 02/09** — 90,30 s, 238 vues, 37 % |
| **Dépouillement 48 h de la vidéo n°1** | ❓ **C'est ce qui manque.** Disponible le 03/09 à 17h02. |

Tant que ce chiffre n'est pas là, `02.Probleme_Metier.md` ne peut pas être
écrit sans inventer.

⚠️ **N-01 attend aussi l'étape 2** : rendre le mot « ordonné » mesurable.
Aujourd'hui c'est un ressenti. Sans chiffre, ce critère ne pourra jamais être
déclaré résolu.

## 5. Chantiers ouverts, sans urgence

**Vidéos n°2 à n°5** — protocole confirmé le 02/09 : **aucune variable ne
bouge**. ~31 s, même style de hook, même musique, mêmes hashtags, même texte
de couverture, même description. Seul le sujet change.

**Test 2, vidéos 6 à 10** — la thèse de l'« utilité perçue » formulée par le
client le 02/09 (voir `CARNET.md` N-07). À lancer **après** le dépouillement
complet du test en cours. Elle aura ses critères écrits avant tournage, et
cette fois **vérifiés comme variables** sur les données disponibles.

**Motion** — améliorer `CartoucheTitre` : texte en cascade (mot par mot),
reveal derrière un masque, et supprimer les deux secondes d'immobilité au
milieu. Le fondu de sortie est déjà corrigé. ⚠️ Toute animation doit éviter
l'opacité en mode chroma.
⚠️ **L'outro est suspecte** (N-06 b) : 83 % de part moyenne mais 17 % au bout.
**Ne pas y toucher avant la fin du test des 5.**

**Le système** — quatre frictions valent un correctif, aucune n'est bloquante :

- **F-05** — le schéma exige `business_problem` dès l'état `Idée`, alors que
  le cycle de vie ne le produit qu'à la transition vers `Cadré`. Correction
  identifiée : demander le besoin brut à la création, rendre le champ
  nullable. Relève de RM-03.
- **F-06** — **contournée** le 02/09 : le dépôt est public, le livrable a pu
  être attaché. Le prérequis silencieux « dépôt distant public » demeure.
- **F-09** — le bouton « 🌟 Preuve publique » crée **et publie** en un geste,
  sans le dire, et c'est irréversible.
- **F-10** — une étape peut être terminée sans aucun livrable.
- **F-12** — un jeton de session expiré met `next dev` en boucle : plus rien
  n'est servi, route publique comprise. C'est l'angle mort n°6 de la S24.

**YouTube** — la chaîne doit démarrer au **jour 1**, pas au jour 5. Cadrage
éditorial à faire (générique, promesse de chaîne). ⚠️ Ce chantier ne dépend
**pas** de `studio-diffusion` : publier ne demande qu'un compte et un fichier.
Dire « j'attends mon système » serait faux — le système n'arrivera pas avant
l'étape 11.

## 6. Ce qu'il ne faut pas faire

- ❌ **Ne terminer aucune étape de la méthode** avant d'avoir les chiffres.
  Une étape `Terminée` est définitive, et le journal enregistre l'heure du
  clic. Cocher sans mesure fabriquerait une fausse cadence.
- ❌ **Ne changer aucune variable** sur les vidéos n°2 à 5 : même durée, même
  style de hook, même musique, mêmes hashtags. Deux variables bougent déjà, en
  ajouter une troisième rendrait le test illisible. **Cela vaut aussi pour la
  thèse de l'utilité perçue** — elle attend le test 2.
- ❌ **Ne réécrire aucun critère** du test après avoir vu les résultats. C1 est
  aveugle et reste écrit tel quel.
- ❌ **Ne pas déduire une durée** d'un pourcentage. Deux tentatives, deux
  échecs : 1,9 % d'erreur le 01/09, **5,4 % le 02/09**. On lit à l'écran.
- ❌ **Ne pas trancher l'architecture** (M4 ou application séparée) avant
  l'étape 8.
- ❌ **Ne pas cliquer « 🌟 Preuve publique »** sans avoir décidé du titre et
  du résumé : ils ne se corrigent jamais.

## 7. Où en est la méthode

**Étape 1 — Besoin Client : ✅ terminée** le 01/09/2026, livrable attaché et
publié dans le système.

**Étape 2 — Problème Métier : en attente du dépouillement du 03/09 à 17h02.**

Les onze étapes suivantes n'ont pas été ouvertes.
