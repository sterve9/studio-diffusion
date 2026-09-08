# Point de reprise — 08/09/2026

À lire en premier au démarrage de la prochaine session.

⚠️ **Ce fichier remplace celui du 03/09, devenu faux.** L'ancien annonçait le
programme d'un jeudi disparu : dépouiller la n°1 à 17h02, tourner le jour 7,
ne changer aucune variable du test. Rien de cela n'a plus cours.

---

## 1. Où démarrer

> **Toujours dans `studio-diffusion`.**
> Les autres dépôts, on y va pour une raison précise, on fait la chose, on revient.

C'est ici qu'on réfléchit. Ailleurs, on exécute.

| Dépôt | Rôle |
|---|---|
| **`studio-diffusion`** | 🏠 **La maison.** Les 13 étapes, les frictions, le carnet, le journal du test, les productions |
| `methode-architecte-ia` | 🔧 **L'outil.** L'application derrière `methode.sterveshop.cloud` |
| `remotion-brand` | 🎬 **Les visuels.** Les compositions Remotion des B-roll |
| `crm-prospection-ingrid` | 📖 **Le modèle.** Lecture seule depuis ici |

---

## 2. Où en est la méthode

| Étape | État |
|---|---|
| **01. Besoin Client** | ✅ **Terminée** le 01/09/2026, livrable attaché et publié |
| **02. Problème Métier** | ✅ **Écrit le 08/09.** Livrable prêt — pas encore coché « Terminée » dans le système |
| 03 à 13 | non ouvertes |

**Ce qui bloquait l'étape 2 n'existe plus.** Elle attendait le dépouillement du
test des 5 vidéos — test **clos le 08/09 à trois vidéos sur cinq**, avec ses
raisons écrites dans `TEST_5_VIDEOS.md`, section « Clôture ».

⚠️ **N-01 attend aussi l'étape 2** : rendre le mot « ordonné » mesurable. Sans
chiffre, ce critère ne pourra jamais être déclaré résolu.

---

## 3. Ce qui a changé le 06/09 — le pivot

**La série « jour N » est abandonnée.** Décision du client.

Le motif est structurel, pas esthétique : *« jour 7 : les contrats de
données »* sert au spectateur l'épisode 7 d'une histoire qu'il n'a pas
commencée, dans un vocabulaire d'architecte logiciel. Sur « Pour toi », chaque
vidéo doit tenir seule ou elle est perdue avant la deuxième seconde.

**Remplacée par des tutoriels autonomes** : construire un CRM dans Google
Sheets, de zéro, en direct. Chaque vidéo porte sa promesse dans son titre et ne
suppose aucune des autres.

**Conséquence : la chaîne YouTube s'est ouverte.** Elle était vide depuis le
début, bloquée par la règle « démarrer au jour 1 » (**N-04**). Un tuto n'a pas
de jour 1 — la contrainte est tombée d'elle-même.

---

## 4. L'état des canaux au 08/09

### YouTube — `IA Architecte`

**Première vidéo publiée le 07/09** : *CRM Google Sheets : colorer chaque
ligne selon le statut (sans code)* — 4 min 23, format 16:9.
<https://youtu.be/uaPnv5LedO4>

⏳ **Validation de chaîne lancée** (vidéo de 6 secondes), en attente de
quelques heures. Tant qu'elle n'est pas passée : pas d'épinglage de
commentaire, pas de vidéo de plus de 15 min, pas de lien externe en carte.

**À faire dès qu'elle est validée** — épingler ce commentaire :

```
=$C2="Client"

Le $ bloque la colonne, le 2 descend.
Ta plage commence en ligne 2 → $C2. En ligne 5 → $C5.
```

### TikTok

**Six extraits verticaux produits depuis la même prise**, par la fonction
« Vidéo longue en vidéos courtes » de CapCut Pro.

| Quand | Combien |
|---|---|
| 07/09 à 15h00 | 1 publié |
| 08/09 | 3 prévus |
| 09/09 | 2 prévus |

⚠️ **Les espacer de plusieurs heures.** TikTok pousse rarement deux vidéos d'un
même compte en même temps.

**Heures de publication volontairement variées.** Décision du client le 07/09 :
sous 100 abonnés, la distribution est algorithmique et non liée à l'audience —
87,4 % du trafic vient de « Pour toi ». Analyser les heures maintenant ne
mesurerait rien. On varie, on lira plus tard.

⚠️ Le champ **site web** de la bio demande 1000 abonnés. Le **lien de compte
YouTube**, non. À défaut : le nom `IA Architecte` en clair dans la bio, et un
commentaire épinglé sur chaque vidéo.

### LinkedIn

Inchangé. Publication irrégulière, alors que c'est le canal où le public
professionnel visé se trouve déjà.

---

## 5. Ce qui est mesuré, et qui sert de matière à l'étape 2

### Les cinq vidéos relevées

| Durée | Vues | Part moyenne | Vue en entier | 0:06 |
|---|---|---|---|---|
| 161 s — référence | **425** | 21 % | 8,32 % | — |
| 90,30 s — témoin | **238** | 37 % | 12,58 % | — |
| 31 s — n°1 | **182** | 85 % | 18,88 % | 45 % |
| 30,50 s — n°2 | **445** | 58 % | 11,42 % | 32 % |
| 27 s — n°3 | **196** | — | — | 27 % |

Médiane autour de **238 vues**. Compte à ~30 abonnés pour une vingtaine de
vidéos.

### Les faits durs

- **La conversion est saine, la portée est la contrainte.** ~1 % d'abonnement
  pour qui regarde.
- **Le levier est la portée par vidéo, pas le nombre de vidéos.** À ~1 %,
  1000 abonnés demandent environ 100 000 vues cumulées.
- **La variabilité écrase l'effet.** Deux vidéos jumelles : 182 et 445 vues
  (**N-10**).
- **M4 ne sait diffuser que du texte** — `'linkedin' | 'x'`. Ni TikTok, ni
  YouTube. Mesuré, pas supposé.

### La mesure que le test ne cherchait pas

| Période | Une journée de travail donne |
|---|---|
| 01 → 05/09 | **1 vidéo** |
| 07/09 | **1 vidéo YouTube + 6 TikTok**, depuis une seule prise |

⚠️ **C'est cette mesure qui correspond au besoin écrit le 01/09** — *« sans que
ça ne me prenne plus de temps »* — et non la portée, sur laquelle le test
s'était concentré une semaine durant.

---

## 6. Chantiers ouverts

**Étape 2 : le fichier est écrit, l'étape n'est pas cochée.**
`02.Probleme_Metier.md` existe depuis le 08/09. Le clic « Terminée » dans le
système reste à faire — après relecture, jamais avant. Une étape terminée est
définitive (**F-02**), et le journal enregistre l'heure du clic.

**Puis `03.Objets_Metier.md`** — nommer les objets que le problème met en jeu,
sans choisir encore ce qui les manipulera.

**Deux dépouillements jamais faits** : la vidéo du 04/09 (16h40) et celle du
05/09 (19h00, hors test). Ni l'un ni l'autre ne bloque quoi que ce soit.

**Tuto 2 — la colonne relance.** Annoncé par le CTA de la vidéo 1 : *« à
relancer aujourd'hui » qui s'affiche toute seule*. La série prévue :

| # | Sujet |
|---|---|
| 1 | ✅ colorer la ligne selon le statut |
| 2 | la colonne relance automatique |
| 3 | le compteur qui se met à jour seul |
| 4 | validation, réglages, protection |
| 5 | *le remplir sans toi* — la passerelle vers l'offre |

**Frictions à corriger, aucune bloquante** : **F-05** (schéma exigeant
`business_problem` trop tôt), **F-09** (le bouton « Preuve publique » crée
**et** publie sans le dire), **F-10** (une étape peut être terminée sans
livrable), **F-12** (jeton expiré → `next dev` en boucle).

**`crm-prospection-ingrid`** — documentation à jour et poussée le 05/09. Trois
défauts connus non corrigés : la règle de priorité se contredit entre
« Moyenne » et « Basse » ; le nom d'entreprise sous 5 caractères produit un
faux négatif ; un prospect dont le site EST une URL Instagram n'est pas
détecté.

---

## 7. Ce qu'il ne faut pas faire

- ❌ **Ne pas rouvrir le test des 5 vidéos.** Clos le 08/09, raisons écrites.
- ❌ **Ne terminer aucune étape sans livrable ni mesure.** Une étape
  « Terminée » est définitive (**F-02**), et le journal enregistre l'heure du
  clic.
- ❌ **Ne pas cliquer « 🌟 Preuve publique »** sans avoir décidé du titre et du
  résumé : ils ne se corrigent jamais (**F-01**, **F-09**).
- ❌ **Ne pas trancher l'architecture** — module M4 ou application séparée —
  avant l'étape 8.
- ❌ **Pas de code avant l'étape 11.**
- ❌ **Ne pas déduire une durée d'un pourcentage.** Deux tentatives, deux
  échecs : 1,9 % puis 5,4 % d'erreur. On lit à l'écran.
- ❌ **Ne pas écrire une date ou une échéance sans avoir lu l'horloge.**
