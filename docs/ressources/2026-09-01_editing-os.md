# Ressource — Editing OS (montage vidéo assisté par IA)

**Capturée le** : 01/09/2026, pendant l'étape 1
**Source** : ressource gratuite diffusée sur LinkedIn
**Licence annoncée** : MIT — utilisation, modification et redistribution libres
**Statut** : 🧊 **GELÉE**

---

## Étape de déblocage

| Usage | Autorisé à partir de |
|---|---|
| La lire pour identifier des composants | **Étape 6 — Composants** |
| S'en servir pour décider une techno | **Étape 9 — Choix Technos** |
| L'intégrer au plan de travail | **Étape 11 — Plan d'implémentation** |
| Alimenter le problème métier (`02`) | ❌ **Jamais** — elle ne contient aucune donnée sur le problème |

## Nature, classée honnêtement

C'est une **solution technique complète**, pas une source de données. Elle ne
mesure rien sur l'audience, la rétention ou la portée. Elle ne peut donc pas
servir à formuler le problème métier.

Ce qu'elle est : un pipeline de montage à 5 agents (coupe des silences,
suppression des ratés, vérification par re-transcription, animations,
recherche de visuels), piloté en langage naturel, avec transcription locale.

## ⚠️ Trois avertissements à relire au déblocage

**1. Elle résout le montage, pas le relais.**
Le besoin capturé en `01` porte sur deux choses : *produire régulièrement*
**et** *relayer facilement sans que ça prenne plus de temps*. Cette ressource
n'adresse que la première moitié, et seulement sa partie fabrication. Le
risque est qu'elle devienne le centre de gravité du projet et que le relais
— peut-être le vrai sujet — passe à la trappe.

**2. Elle est assez complète pour tenir lieu de réponse avant la question.**
C'est précisément le piège que le gel existe pour éviter. Sa complétude est
un argument d'adoption, pas une justification d'architecture.

**3. Elle vise Instagram / reels.**
Les canaux du projet sont TikTok, YouTube et LinkedIn. Le mastering à
-14 LUFS et les formats verticaux sont calés sur Instagram. À vérifier
canal par canal, pas à supposer transposable.

## Dépendances qu'elle impose (décisions d'étape 9)

- Claude Code + abonnement Claude Pro (~17 $/mois)
- FFmpeg (moteur vidéo)
- Whisper en local (transcription, modèle ~1,6 Go)
- Google Chrome (fabrication des animations)
- Performance annoncée : ~7x le temps réel sur un Mac M4 — **machine cible
  du projet : Windows 10. Non vérifié.**

Aucune clé API requise, transcription locale et gratuite.

---

# Contenu intégral, tel que capturé

# Editing OS — monte tes vidéos avec l'IA

<aside>
🎬

**Le système complet que j'utilise pour monter mes reels.** Tu lui donnes ton rush face caméra, il te rend une vidéo montée : silences coupés, ratés supprimés, illustrations animées calées sur tes mots, sous-titres, sound design, et le son au bon niveau pour Instagram.

**Tout se pilote depuis l'application Claude Code.** Tu n'as aucune ligne de commande à connaître : tu écris ce que tu veux en français, il le fait. Compte 20 minutes d'installation, une seule fois.

</aside>

---

## Ce que fait le système

Ce n'est pas un outil de plus. C'est une **chaîne de montage** : cinq agents qui se passent le relais, chacun avec un seul métier.

1. **Snip** coupe les silences et les blancs — au décibel, pas à l'oreille
2. **Redo** supprime les hésitations, les bafouillages et les prises ratées (et garde toujours la meilleure : la dernière)
3. **Vera** vérifie le travail des deux premiers en re-transcrivant le rendu — aucun mot coupé ne passe
4. **Mo** ajoute les animations : interfaces rejouées, compteurs, timelines, mots-clés qui claquent
5. **Scout** va chercher les visuels sur le web quand tu cites un outil ou un site

Entre les deux, une étape que personne d'autre ne fait : le système **écoute ce que tu dis** et te propose un storyboard, seconde par seconde, avant de monter quoi que ce soit. Tu valides, tu corriges, et seulement après il compose.

<aside>
💡

Tout est calé sur un **transcript mot à mot**. Chaque coupe, chaque animation, chaque sous-titre tombe sur un mot précis. C'est pour ça que le montage ne fait pas « automatique ».

</aside>

---

## Télécharge le système

Le système complet — 6,5 Mo

Le système complet — 6,5 Mo

Dézippe-le où tu veux. Je te conseille `Documents`. Le guide d'installation est aussi dedans, dans le fichier `COMMENCE-ICI.md`.

---

## Installation

### 1. Installe l'application Claude Code

Télécharge-la sur claude.com/product/claude-code — elle existe pour Mac et Windows. C'est elle qui va tout faire à ta place, y compris s'installer le reste.

Il te faut un abonnement **Claude Pro** (à partir de 17 $/mois) : Claude Code est inclus dedans.

### 2. Dézippe le système

Dézippe `editing-os.zip` dans ton dossier `Documents`. Tu obtiens un dossier nommé `editing-os`.

### 3. Ouvre ce dossier dans l'application

Lance Claude Code et ouvre le dossier `editing-os` comme projet. À partir de là, Claude voit tout le système : les agents, les scripts, les styles, la méthode.

### 4. Demande-lui de s'installer lui-même

C'est ici que ça devient confortable. Écris-lui, dans la conversation :

<aside>
💬

*« Installe tout ce dont ce système a besoin pour tourner, puis vérifie que tout est bon. »*

</aside>

Il vérifie ce qui manque sur ta machine, installe le moteur vidéo (FFmpeg), la transcription locale (Whisper) et les dépendances du projet, puis lance le diagnostic intégré et te confirme que tout est vert. Il te dira aussi s'il te manque **Google Chrome**, qui sert à fabriquer les animations.

<aside>
🔐

Claude te demande ton accord avant chaque commande : tu vois ce qu'il s'apprête à faire, tu valides d'un clic. Une seule chose qu'il ne peut pas faire à ta place : si une installation réclame ton **mot de passe Mac**, il te donne la ligne exacte à coller toi-même dans le Terminal. C'est la seule fois où tu y touches.

</aside>

<aside>
🔑

**Aucune clé API n'est nécessaire.** La transcription tourne en local, sur ta machine, gratuitement. Le fichier `.env.example` ne concerne que des options avancées.

</aside>

---

## Ta première vidéo

Tout se passe dans la même conversation. Tu n'ouvres rien d'autre.

### 1. Ouvre le tableau de bord

<aside>
💬

*« Lance le tableau de bord. »*

</aside>

Il le démarre et te donne le lien à ouvrir dans ton navigateur. Tu y vois tes projets, l'état de chaque montage et tes rendus.

### 2. Donne-lui ton rush

Glisse ton fichier vidéo directement dans la conversation, et écris :

<aside>
💬

*« Nouveau reel à partir de ce rush. »*

</aside>

### 3. Laisse-le dérouler, et interviens au bon moment

Il choisit le format, transcrit ta parole mot à mot, monte le son, puis **s'arrête et te propose un storyboard** : ce qu'il compte animer, seconde par seconde. C'est ton moment. Tu valides, ou tu corriges en une phrase.

Ensuite il compose, rend, vérifie son propre travail, et te livre un fichier prêt à publier.

<aside>
⚡

Tu peux tout lui dire en langage normal : « refais l'intro plus punchy », « enlève la musique », « la vidéo doit finir quand j'arrête de parler ». Pas de syntaxe à apprendre.

</aside>

---

## Les 3 règles qui font 80 % du résultat

### 1. Donne tes retours par timecode

Chaque projet embarque une interface de review. Tu avances image par image, tu écris « à 00:12 le texte cache mon visage », tu cliques **Copier pour Claude**, tu colles dans la conversation. Il corrige au millimètre, pas approximativement.

### 2. Tes retours sont permanents

Dis-lui **« retiens ça pour les prochaines »**. Il l'écrit dans ses règles, définitivement. La vidéo suivante démarre avec cet acquis.

<aside>
📈

C'est le vrai truc : au bout de trois vidéos, la **première version** ressemble à la dixième version de ta première vidéo. Le système ne se contente pas de monter, il apprend ton œil.

</aside>

### 3. Ne valide jamais ce que tu n'as pas vu

Le système se vérifie lui-même — il re-transcrit son propre rendu pour prouver qu'aucun mot n'a été coupé, contrôle qu'aucun moment n'est visuellement vide, et masterise le son à -14 LUFS (le niveau des plateformes ; un montage brut sort vers -23, soit deux fois moins fort que les autres reels de ton feed). Un rendu qui rate un de ces tests ne t'est pas livré.

Mais regarde quand même. C'est toi le directeur artistique.

---

## Mets-le à ton identité

Le dossier arrive volontairement neutre. Trois choses sont à toi :

| Quoi | Où | Comment |
| --- | --- | --- |
| **Tes sound effects** | `asset-library/sfx/` | Dépose tes `.wav` en gardant les noms de rôles (`whoosh.wav`, `pop.wav`, `click.wav`…). Rien d'autre à configurer. |
| **Tes polices** | `style-library/10-maxence/fonts/` | Dépose tes `.woff2`. Sans ça, le système utilise des polices système. |
| **Ta couleur** | `style-library/10-maxence/tokens.css` | Change la variable `--jaune` par ta couleur de marque : tout le style suit. |

Le plus simple : dis-le à Claude en langage naturel — « configure mon style : ma couleur c'est #XXXXXX, mes polices c'est X et Y » — il s'occupe du reste.

<aside>
⚖️

Pourquoi ce n'est pas fourni : mes sound effects et ma police (Garet) sont sous licence commerciale, je n'ai pas le droit de les redistribuer. Utilise les tiens, ou une banque libre de droits (Pixabay, Freesound, Google Fonts).

</aside>

---

## En cas de problème

- **Claude dit qu'il manque quelque chose sur ma machine**

    Réponds-lui simplement « installe ce qui manque ». Il connaît les commandes et te demandera de valider. S'il faut ton mot de passe Mac, il te donnera la ligne à coller toi-même dans le Terminal.

- **Le diagnostic affiche du rouge**

    Ne cherche pas à comprendre : colle ce que tu vois dans la conversation. Claude lit le diagnostic et se répare lui-même.

- **Le premier montage est très lent**

    Normal : le modèle de transcription (environ 1,6 Go) se télécharge à la première utilisation. Les suivants sont rapides — environ 7x le temps réel sur un Mac M4.

- **Le tableau de bord ne s'ouvre pas**

    Demande-lui « relance le tableau de bord » : il le redémarre et te redonne le lien.

- **Une animation ne me plaît pas**

    Dis-le en langage naturel avec le timecode : « à 00:08, l'animation arrive trop tard » ou « le mot cache la timeline ». C'est exactement comme ça que ce système a été construit.

<aside>
🛠️

Pour tout le reste : décris ton problème à Claude dans la conversation, avec une capture d'écran si besoin. Il a accès à l'ensemble du système et se débugue lui-même la plupart du temps.

</aside>

---

## Ce qu'il y a dans le dossier

- **Le détail du contenu**
    - `COMMENCE-ICI.md` — ce guide, en version fichier
    - `PROCESS.md` — la recette complète d'un reel, phase par phase
    - `MOTION_PHILOSOPHY.md` — la philosophie d'animation (à lire avant toute session créative)
    - `.claude/skills/` — les 13 agents (les 5 du pipeline + les spécialistes)
    - `scripts/` — transcription locale, auto-vérification, mastering audio
    - `style-library/` — les bibliothèques de cartes animées
    - `style-templates/` — les squelettes de projets, prêts à cloner
    - `formats/` — les 3 formats de reel standardisés
    - `editing-os/` — le tableau de bord

---

<aside>
💬

Une question, un blocage, une idée d'amélioration ? Écris-moi. Ce système évolue à chaque retour.

</aside>

*Licence MIT — tu peux l'utiliser, le modifier et le distribuer librement. Construit sur HyperFrames.*
