# Point de reprise — écrit le 01/09/2026 au soir

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

**Relever les chiffres du test.** C'est ce qui débloque tout le reste.

TikTok Studio → Contenu → la vidéo → la courbe seconde par seconde.

### Vidéo n°1 du test — publiée le 01/09/2026 à 17h02, durée 31 s

Sept mesures à reporter dans `TEST_5_VIDEOS.md` :

vues · temps de visionnage moyen · part moyenne regardée · vue en entier ·
**seconde du décrochage** · nouveaux abonnés · commentaires

**Le décrochage est le chiffre décisif.** Ligne de base : **0:02**. S'il
recule, le hook a fonctionné.

⚠️ **Piège écrit d'avance** : la part moyenne regardée va probablement
exploser, et **ça ne prouvera rien** — sur 31 secondes au lieu de 161, le même
temps d'attention donne mécaniquement un bien meilleur pourcentage. C'est de
la division, pas du progrès. Ne pas annoncer de victoire là-dessus seul.

### Vidéo témoin — publiée le 31/08/2026

Ses analytiques n'étaient pas encore disponibles le 01/09. Si elles sont
apparues, les relever : c'est la mesure de l'ancien format la plus proche dans
le temps, donc la plus comparable. **Ne pas supprimer cette vidéo.**

## 4. Ce qui bloque l'étape 2

Trois mesures manquaient le matin du 01/09. **Il n'en reste qu'une.**

| Mesure | État |
|---|---|
| Durée réelle de la vidéo de référence | ✅ **2 min 41**, lue directement (la déduction disait 2 min 45 — juste à 3 s près) |
| Ce que M4 sait diffuser | ✅ **`'linkedin' \| 'x'`, texte uniquement.** Ni TikTok ni YouTube. « Il faut juste calibrer » est faux : la vidéo n'existe nulle part dans le système. |
| **Résultats du test des 5 vidéos** | ❓ **C'est ce qui manque.** |

Tant que ce chiffre n'est pas là, `02.Probleme_Metier.md` ne peut pas être
écrit sans inventer.

## 5. Chantiers ouverts, sans urgence

**Motion** — améliorer `CartoucheTitre` : texte en cascade (mot par mot),
reveal derrière un masque, et supprimer les deux secondes d'immobilité au
milieu. Le fondu de sortie, lui, est déjà corrigé. ⚠️ Toute animation doit
éviter l'opacité en mode chroma.

**Le système** — quatre frictions valent un correctif, aucune n'est bloquante :

- **F-05** — le schéma exige `business_problem` dès l'état `Idée`, alors que
  le cycle de vie ne le produit qu'à la transition vers `Cadré`. Correction
  identifiée : demander le besoin brut à la création, rendre le champ
  nullable. Relève de RM-03.
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
  ajouter une troisième rendrait le test illisible.
- ❌ **Ne pas trancher l'architecture** (M4 ou application séparée) avant
  l'étape 8.
- ❌ **Ne pas cliquer « 🌟 Preuve publique »** sans avoir décidé du titre et
  du résumé : ils ne se corrigent jamais.

## 7. Où en est la méthode

**Étape 1 — Besoin Client : ✅ terminée** le 01/09/2026, livrable attaché et
publié dans le système.

**Étape 2 — Problème Métier : en attente des chiffres.**

Les onze étapes suivantes n'ont pas été ouvertes.
