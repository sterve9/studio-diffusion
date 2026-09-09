# Point de reprise — 09/09/2026

À lire en premier au démarrage de la prochaine session, avant `CLAUDE.md`.

---

## 1. La première tâche

> **Écrire `docs/methode/13.Documentation.md`.**

Les étapes 1 à 12 sont écrites. **La 13 manque**, et tant qu'elle manque le
cycle n'est pas clos.

---

## 2. Où démarrer

> **Toujours dans `studio-diffusion`.**
> Les autres dépôts, on y va pour une raison précise, on fait la chose, on revient.

| Dépôt | Rôle |
|---|---|
| **`studio-diffusion`** | 🏠 **La maison.** Les 13 étapes, les frictions, le carnet, les productions, et **le code** |
| `methode-architecte-ia` | 🔧 L'application derrière `methode.sterveshop.cloud` |
| `remotion-brand` | 🎬 Les compositions Remotion des B-roll |
| `crm-prospection-ingrid` | 📖 Le modèle. Lecture seule depuis ici |

---

## 3. Où en est la méthode

| Phase | Étapes | État |
|---|---|---|
| 1 — COMPRENDRE | 01 → 05 | ✅ écrites |
| 2 — CONCEVOIR | 06 → 08 | ✅ écrites |
| 3 — CHOISIR | 09 → 10 | ✅ écrites |
| 4 — CONSTRUIRE | 11 · 12 | ✅ écrites · **13 manque** |

⚠️ **Écrire un fichier et terminer l'étape dans le système sont deux gestes
distincts.** Le second est définitif (`F-02`) et enregistre l'heure du clic.
Plusieurs étapes ont leur fichier en ligne sans être cochées.

**La décision d'architecture est prise** (étape 8) : une application séparée,
consommant les preuves par contrat. LinkedIn et X restent dans M4.

---

## 4. Il y a du code, maintenant

**`app/teleprompteur.html`** — le jalon **`J1`** du plan d'implémentation.

| | |
|---|---|
| Trois vues | éditeur · voix off · **face caméra** |
| En ligne | `sterve9.github.io/studio-diffusion/app/teleprompteur.html` |
| Hébergement | GitHub Pages, HTTPS — condition d'accès à la caméra |

### ✅ La mesure du 09/09, et elle dément une hypothèse

> **Une prise de 90 secondes est passée sur iPhone, sans plantage.**

La limite documentée d'une minute n'était pas une interdiction d'Apple :
c'était l'accumulation en mémoire. **Un morceau par seconde vidé dans
IndexedDB, et le problème disparaît.**

### Ce que la page a d'unique

Elle **distingue ce qui se dit de ce qui se vérifie** — `#` pour un titre,
`!` pour un piège, `>` pour un point de contrôle. Aucune application payante
ne sait faire ça, parce qu'aucune ne connaît `CT-04`.

⚠️ **Les finitions se noteront à l'usage**, pas en anticipant.

---

## 5. La vision produit — nouvelle le 09/09

Le système de prospection, inspiré par une SMM, pourrait devenir **un produit
digital** pour PME et entrepreneurs.

⚠️ **Ce sera un projet neuf, avec ses treize étapes.** Le client change —
d'Ingrid à *« un entrepreneur qui prospecte des commerces locaux »*. Client
différent, besoin différent, projet différent. **Ne pas le greffer sur
`crm-prospection-ingrid`.**

**Deux réserves posées le 09/09 :**

1. ❌ **Ne pas généraliser la source.** La source de collecte *est* le
   produit. Généraliser l'**acheteur**, pas la source : tous ceux qui
   prospectent des commerces locaux — SMM, agences, photographes, comptables.
2. ⚠️ **Le coût par exécution n'est pas mesuré.** Apify facture au résultat,
   Claude à l'appel. **C'est ce nombre qui décide si on vend un fichier ou un
   abonnement.** Il se mesure en une exécution.

**Ce qui est défendable** : ni le scraping, ni le tableur. **Les règles** — la
priorité par le ratio avis/abonnés, la double preuve d'appartenance, le rythme
de relance par statut. Elles viennent toutes d'un échec corrigé.

---

## 6. Les canaux au 09/09

### YouTube — `IA Architecte`

Première vidéo publiée le 07/09 : *CRM Google Sheets : colorer chaque ligne
selon le statut* — 4 min 23, 16:9. <https://youtu.be/uaPnv5LedO4>

⏳ Validation de chaîne lancée. Tant qu'elle n'est pas passée : pas
d'épinglage de commentaire.

### TikTok

**Une seule vidéo publiée le 08/09**, pas trois. Décision du client :

> *« J'ai regardé le contenu des autres extraits, ça avait l'air tout pareil,
> j'ai préféré ne pas saturer avec du déjà-vu. »*

⚠️ **Ça corrige un conseil donné le 08/09.** Six extraits d'une même vidéo ne
sont pas six tentatives : c'est six fois la même. **La variance vient du
contenu, pas du découpage.** Garder deux extraits au maximum, les plus
dissemblables, espacés.

**Profil mis à jour** : bio avec la promesse *« une vidéo = une manipulation
que tu refais ce soir »*, et un commentaire épinglé qui renvoie vers YouTube.

**Heures de publication volontairement variées** tant que le compte est sous
100 abonnés — 87 % du trafic vient de « Pour toi », l'heure ne mesure rien.

---

## 7. Le tuto 2 — construit et vérifié, pas encore tourné

**Sujet** : l'onglet `Relance` d'un CRM à quatre onglets.

La feuille est construite et fonctionne. **Sept pièges ont été trouvés en la
construisant, dont cinq n'étaient dans aucun brouillon** — ils sont dans
`docs/productions/tuto-02/notes-construction.txt`.

### ⚠️ Le `+7` fixe est écarté

> *« Dans un CRM réel, si je relance et que c'est concluant il passe à client.
> On doit apporter une valeur réelle dans un cas réel. »*

**Le rythme dépend du statut** : `Contacté` → 3 jours, `En discussion` →
7 jours, `Client` et `Perdu` → aucune relance.

**Et la règle vit dans un tableau, pas dans la formule.** Changer un délai doit
être changer un chiffre dans une case.

**Reste à construire** : ce tableau de règles et la formule qui le lit.

---

## 8. Chantiers ouverts

| | Quoi |
|---|---|
| **1** | **`13.Documentation.md`** — clore les treize étapes |
| **2** | Le délai de relance selon le statut, puis **tourner le tuto 2** |
| **3** | **Compter les prises** au tournage — le nombre du 07/09 n'a jamais été compté, et sans lui on ne saura jamais si le téléprompteur a servi |
| **4** | Deux dépouillements jamais faits : 04/09 et 05/09 |
| **5** | Mesurer le **coût par exécution** du système de prospection |
| **6** | Attacher les livrables et terminer les étapes 03 à 12 dans le système |

**Frictions à corriger, aucune bloquante** : `F-05`, `F-09`, `F-10`, `F-12`.

**`crm-prospection-ingrid`** : trois défauts connus non corrigés — la règle de
priorité qui se contredit entre « Moyenne » et « Basse », le faux négatif sur
les noms sous 5 caractères, le prospect dont le site est une URL Instagram.

---

## 9. Ce qu'il ne faut pas faire

- ❌ **Ne rien proposer de générique.** Chaque proposition résout un problème
  réel, dans un cas réel. Le marqueur : **la règle vit dans un tableau, pas
  dans la formule.**
- ❌ **Ne pas écrire un script avant que la construction soit vérifiée.** Le
  08/09 en a produit deux, faux sur trois points ; la construction du 09/09 a
  révélé sept pièges dont cinq inconnus.
- ❌ **Ne pas rouvrir le test des 5 vidéos.** Clos le 08/09.
- ❌ **Ne pas généraliser la source** du système de prospection.
- ❌ **Ne pas cliquer « 🌟 Preuve publique »** sans avoir décidé du titre et du
  résumé : ils ne se corrigent jamais (`F-01`, `F-09`).
- ❌ **Ne pas déduire une durée d'un pourcentage.** Deux tentatives, deux
  échecs.
- ❌ **Ne pas écrire une date ou une échéance sans avoir lu l'horloge.**
- ❌ **Ne pas écrire un fichier sans avoir montré son contenu** et obtenu le
  feu vert. Accepter que j'écrive n'est pas accepter ce que j'écris.
