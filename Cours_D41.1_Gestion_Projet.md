# 📘 Cours complet — UC D41.1
## Conduite et management de projet informatique — Fondamentaux

> Objectif : te donner **tout** ce dont tu as besoin pour réussir l'épreuve (2 dossiers, 150 points, 1h30).
> Tu pars de zéro → on construit chaque notion brique par brique.

---

## 🎯 Plan du cours

1. **Vue d'ensemble** : à quoi sert la gestion de projet
2. **Dossier 1 — Méthodes Agiles** (Scrum + Kanban)
3. **Dossier 2 — Méthode traditionnelle** (cycle en V, Gantt, chemin critique)
4. **Application directe au sujet de janvier 2025**
5. **Fiche mémo de dernière minute**

---

# 0. Vue d'ensemble : les deux grandes familles

Un **projet** = un ensemble d'activités coordonnées pour atteindre un objectif **unique**, avec un **début, une fin, un budget et des ressources** limités.

Il existe deux grandes philosophies pour gérer un projet :

| | **Traditionnelle (cascade / cycle en V)** | **Agile (Scrum, Kanban)** |
|---|---|---|
| Logique | Tout planifier au début, puis exécuter | Avancer par petits incréments, s'adapter |
| Besoin client | Figé dès le départ | Peut évoluer pendant le projet |
| Livraison | Une seule grosse livraison à la fin | Plein de petites livraisons régulières |
| Documents | Beaucoup (cahier des charges, specs…) | Moins, on privilégie le produit |
| Quand l'utiliser ? | Projet bien défini, contraintes fortes (BTP, aérospatial, banque) | Projet incertain, besoins évolutifs (web, mobile, startup) |

👉 Ton examen teste **les deux**. Il faut savoir reconnaître les concepts et les manipuler.

---

# 📦 DOSSIER 1 — Gestion de projet Agile (75 points)

## 1.1 La philosophie Agile (à comprendre, pas à réciter)

Née en 2001 avec le **Manifeste Agile**, qui pose 4 valeurs :

1. **Les individus et leurs interactions** plutôt que les processus et les outils
2. **Un logiciel qui fonctionne** plutôt qu'une doc exhaustive
3. **La collaboration avec le client** plutôt que la négociation contractuelle
4. **L'adaptation au changement** plutôt que le suivi d'un plan rigide

> 🧠 Mnémo : **« Individus, Produit, Client, Changement »** — dans cet ordre, ce qui est à gauche compte plus.

Agile **n'est pas** une méthode. C'est un état d'esprit. **Scrum** et **Kanban** sont des méthodes **qui appliquent** Agile.

---

## 1.2 SCRUM en détail

Scrum, c'est un cadre de travail (un *framework*) qui organise l'équipe autour de **sprints** (cycles courts, généralement 2 à 4 semaines).

### 🧑‍🤝‍🧑 Les 3 rôles

| Rôle | Mission |
|---|---|
| **Product Owner (PO)** | Représente le client. **Responsable du Product Backlog** : il décide *quoi* faire et dans quel ordre (priorisation). |
| **Scrum Master** | Gardien du framework Scrum. Il facilite le travail de l'équipe, lève les obstacles. **Ce n'est PAS un chef de projet.** |
| **Équipe de développement** | 3 à 9 personnes auto-organisées. Elles décident *comment* faire. |

> ⚠️ Question piège classique : **« Qui est responsable du Product Backlog ? »** → **le Product Owner**.
> **« Qui valide qu'une user story passe de "test" à "done" ? »** → **le Product Owner** (c'est lui qui dit "OK, ça correspond à ce que je voulais").

---

### 📋 Les 3 artefacts (les "documents" de Scrum)

#### 1) **Product Backlog**
- Liste **complète et priorisée** de tout ce qui pourrait être fait sur le produit.
- Contient des **User Stories** (« En tant que [rôle], je veux [action] afin de [bénéfice] »).
- **Vivante** : elle évolue tout au long du projet.
- **Géré par le Product Owner**.

#### 2) **Sprint Backlog**
- ✅ **OUI, le Sprint Backlog existe en Scrum.** (Question typique de l'exam !)
- C'est le **sous-ensemble du Product Backlog** que l'équipe s'engage à réaliser **dans le sprint en cours**.
- Géré par **l'équipe de développement**.
- Figé pendant le sprint (on n'ajoute pas de tâches en cours de route).

#### 3) **Incrément**
- Le résultat concret produit à la fin de chaque sprint.
- Doit être **potentiellement livrable** (= ça marche, c'est testé).

---

### 🗓️ Les 5 événements (les rituels Scrum)

| Événement | Quand ? | Durée | But |
|---|---|---|---|
| **Sprint** | Le cycle lui-même | 2–4 semaines | Produire un incrément |
| **Sprint Planning** | Début du sprint | 2–8h | Choisir ce qu'on fait → remplir le Sprint Backlog |
| **Daily Scrum (mêlée)** | Tous les jours | 15 min | Synchronisation rapide : « hier / aujourd'hui / blocages » |
| **Sprint Review** | Fin du sprint | 1–4h | Montrer ce qui a été fait au PO et aux parties prenantes |
| **Rétrospective** | Tout fin du sprint | 1–3h | Amélioration continue de l'équipe : qu'est-ce qui a bien marché ? Quoi améliorer ? |

> 🧠 Mnémo : **« Plan → Daily → Review → Retro »** (PDRR).

---

### 🔄 Cycle de vie d'une User Story

Une user story passe en général par les états :

```
To Do  →  In Progress  →  Test  →  Done
```

- **To Do** : à faire, pas encore commencé
- **In Progress** : en cours de développement
- **Test** : développé, en cours de validation/tests
- **Done** : terminé ET **validé par le Product Owner**

> 👉 C'est le **Product Owner** qui fait passer une story en "Done" (réponse à la Question 1 du sujet).

---

## 1.3 KANBAN

Méthode plus souple que Scrum, basée sur la **visualisation du flux** de travail.

### Le tableau Kanban

C'est un tableau avec des **colonnes représentant les étapes du processus**. Les cartes (tâches) circulent **de gauche à droite**.

Exemple minimal :

```
┌──────────┬─────────────┬───────┐
│  To Do   │ In Progress │ Done  │
├──────────┼─────────────┼───────┤
│ Tâche A  │  Tâche B    │       │
│ Tâche C  │             │       │
└──────────┴─────────────┴───────┘
```

> 👉 Le tableau du sujet (questions 5-7) est un **tableau Kanban**. C'est la réponse à la Question 5.

---

### Règles d'or du Kanban

1. **Visualiser le travail** (chaque tâche = une carte).
2. **Limiter le travail en cours (WIP – Work In Progress)** : pas plus de X cartes dans la colonne "In Progress" → évite la dispersion.
3. **Flux tiré** : on prend une nouvelle tâche **quand on a fini la précédente**, pas avant.
4. **Amélioration continue**.

---

### Que doit contenir une carte Kanban ?

Réponse type pour la Question 8 du sujet :

- **Le titre/nom de la tâche** (ex : "Codage")
- **La personne ou l'équipe responsable** (ex : team1, team2)
- **La date d'échéance** (deadline)
- **La priorité** (haute / moyenne / basse)
- **Une description courte** de ce qu'il faut faire
- **Les critères d'acceptation** (quand la tâche est-elle terminée ?)
- **Les éventuelles dépendances** avec d'autres tâches
- **Des tags/étiquettes** (type de tâche, projet…)

---

### Lire un tableau Kanban (Questions 6 et 7 du sujet)

**Question 6 — Quelle carte passera prochainement « in progress » ?**

Logique : la colonne "To Do" contient plusieurs cartes. La prochaine à passer est en général **celle qui a la date d'échéance la plus proche** OU **celle en haut de la pile**.

Dans le sujet : "Codage" est daté du **28 février 2025**, "tests" et "deployment" n'ont pas de date.
👉 La carte **« Codage »** (team2) sera la prochaine à passer "In Progress" car elle a la date la plus proche.

**Question 7 — Quelle équipe finit le projet en dernier ?**

Il faut regarder la **dernière carte chronologiquement** (la plus à droite dans le temps).
Dans le second tableau du sujet :
- deployment → team2 → 4 avril 2025 ← **la plus tardive**
- tests → team1 → 14 mars 2025

👉 **team2** finit le projet en dernier (c'est elle qui s'occupe du déploiement, étape finale).

---

## 1.4 Avantages et inconvénients de l'Agile

### ✅ Avantages

- **Flexibilité** : on peut changer les priorités à chaque sprint.
- **Livraisons fréquentes** → le client voit vite des résultats.
- **Feedback rapide** → on corrige le tir tôt.
- **Forte implication du client / utilisateur**.
- **Motivation de l'équipe** (auto-organisation, autonomie).
- **Détection précoce des problèmes**.
- **Risques réduits** (on ne découvre pas les problèmes à la fin).

### ❌ Inconvénients

- **Difficile à budgéter** précisément à l'avance (le périmètre évolue).
- **Manque de documentation** : peut poser problème pour la maintenance.
- **Demande une forte disponibilité du client / Product Owner**.
- **Pas adapté aux projets à exigences réglementaires strictes** (besoin de specs figées).
- **Difficile à grande échelle** sans framework dédié (SAFe, LeSS…).
- **Demande une équipe expérimentée et auto-discipliné**.
- **Vision à long terme parfois floue**.

> 🧠 Astuce exam : pour ce genre de question, donne **3-4 points par côté**, formulés en phrase complète.

---

# 🏗️ DOSSIER 2 — Gestion de projet traditionnelle (75 points)

## 2.1 Les modèles classiques

### Le modèle en cascade (waterfall)

Les phases s'enchaînent **séquentiellement**, sans retour en arrière :

```
Analyse → Conception → Développement → Tests → Déploiement → Maintenance
```

### Le cycle en V

Variante : chaque phase de conception (descente du V) a sa phase de test miroir (remontée du V).

```
Cahier des charges ─────────────── Recette utilisateur
   Spécifications ────────────── Tests d'intégration
      Conception ─────────── Tests unitaires
         Développement
```

> 👉 Dans le sujet, les phases "tests unitaires", "tests d'intégration" et "validation utilisateur" sont typiques du cycle en V.

---

## 2.2 Les acteurs : MOA et MOE

C'est une distinction **fondamentale** en France pour les projets IT.

| Acteur | Sigle complet | Rôle | Analogie |
|---|---|---|---|
| **MOA** | Maîtrise d'Ouvrage | **Le client.** Exprime le besoin, valide le résultat. | Le particulier qui veut faire construire sa maison |
| **MOE** | Maîtrise d'Œuvre | **Le réalisateur.** Conçoit et fabrique la solution. | L'architecte + les artisans |

### Question 6 du sujet : « Quelle fonction est réalisée par le MOA dans la phase d'expression de besoin ? »

Réponse type :
> **La MOA est responsable de l'expression du besoin.** C'est elle qui :
> - Définit les objectifs métier du projet
> - Identifie les utilisateurs finaux et leurs besoins
> - Rédige (ou fait rédiger) le **cahier des charges fonctionnel**
> - Définit les contraintes (budget, délai, qualité)
> - Validera le produit fini (recette utilisateur)

---

## 2.3 Le cahier des charges

### Question 5 du sujet : « Quel document exprime les fonctions de service et les contraintes attendues par les utilisateurs ? »

👉 **Le cahier des charges** (plus précisément, le **cahier des charges fonctionnel — CdCF**).

Il contient :
- Le **contexte** du projet (pourquoi on le fait)
- Les **fonctions de service** : ce que le produit doit faire (= fonctionnalités)
- Les **contraintes** : techniques, budgétaires, réglementaires, délais
- Les **critères d'acceptation** : comment on valide que c'est bon
- Les **livrables** attendus

> 🧠 Mnémo : un cahier des charges répond à **« QUOI ? »** et **« POUR QUI ? »**, pas à **« COMMENT ? »**.

---

## 2.4 La planification

### Question 7 du sujet : « Quelle est la première étape de la planification ? »

👉 **Identifier / définir les tâches du projet** (souvent appelée **décomposition du projet en tâches** ou **WBS – Work Breakdown Structure**).

Les étapes globales de la planification :

1. **Identifier les tâches** (WBS — découper le projet en activités)
2. **Estimer la durée** de chaque tâche
3. **Identifier les dépendances** entre tâches (qui doit finir avant quoi)
4. **Affecter les ressources** (qui fait quoi)
5. **Construire le planning** (Gantt, PERT…)
6. **Identifier le chemin critique**

---

### Notion clé : le **jour-homme** (j/h)

Un **jour-homme** = le travail effectué par **une personne pendant un jour**.

#### Formule :
```
Durée totale en j/h = somme(durée d'une tâche × nb de personnes affectées)
```

#### Exemple :
- Tâche A : 5 jours, 2 personnes → 10 j/h
- Tâche B : 3 jours, 1 personne → 3 j/h
- Total : **13 j/h**

#### Application au sujet (Question 2) :

Le projet d'application mobile fait :
- Phase 1 : 2 semaines = 10 jours
- Phase 2 : 8 semaines = 40 jours
- Phase 3 : 3 semaines = 15 jours
- Phase 4 : 1 semaine = 5 jours

**Total = 70 jours ouvrés.**

⚠️ Le sujet ne précise pas le nombre de personnes par phase. Si on suppose **1 personne par phase**, alors **70 j/h**. Si l'énoncé donne un nombre de personnes, multiplie par celui-ci.

---

## 2.5 Le diagramme de Gantt

C'est une **représentation visuelle du planning**. Chaque tâche est une **barre horizontale** dont la longueur représente sa durée.

```
            Sem 1  Sem 2  Sem 3  Sem 4  Sem 5
Tâche A    ████████
Tâche B           ████████
Tâche C                  ████████████
```

### Comment le construire (méthode pas à pas)

1. Lister toutes les tâches.
2. Estimer la durée de chacune.
3. Identifier les dépendances (qui dépend de qui).
4. Placer chaque tâche sur un axe temporel.
5. Marquer les jalons (étapes clés).

### ⚠️ Application au sujet (Question 1 — la plus complexe)

**Données :**
- Début : **lundi 3 février 2025**
- Week-ends non travaillés, jours fériés travaillés
- 4 phases :
  1. Planification et conception : **2 semaines** (10 jours ouvrés)
  2. Développement : **8 semaines** (40 jours ouvrés)
  3. Tests et validation : **3 semaines** (15 jours ouvrés)
  4. Lancement et déploiement : **1 semaine** (5 jours ouvrés)
- **La phase 3 commence quand il reste 2 semaines à effectuer dans la phase 2** → la phase 3 démarre en **chevauchement** avec la phase 2.

**Décomposition :**

| Phase | Début | Fin | Durée |
|---|---|---|---|
| 1. Planification/conception | Lun 3 février 2025 | Ven 14 février 2025 | 2 semaines (10 j) |
| 2. Développement | Lun 17 février 2025 | Ven 11 avril 2025 | 8 semaines (40 j) |
| 3. Tests et validation | Lun 31 mars 2025* | Ven 18 avril 2025 | 3 semaines (15 j) |
| 4. Lancement et déploiement | Lun 21 avril 2025** | Ven 25 avril 2025 | 1 semaine (5 j) |

\* Phase 3 démarre **2 semaines avant la fin** de la phase 2 (chevauchement).
\** Le lundi 21 avril 2025 est le **lundi de Pâques** : c'est férié, mais l'énoncé dit que **les jours fériés en semaine sont travaillés**, donc OK.

**Visuellement :**

```
Phase 1 ████
Phase 2     ████████████████
Phase 3                ██████
Phase 4                       ██
        Fév         Mars       Avril
```

---

## 2.6 Le chemin critique

### Définition

Le **chemin critique** est la **séquence de tâches** qui :
- détermine la **durée totale minimale** du projet
- ne comporte **aucune marge** (si une seule tâche du chemin critique prend du retard, **tout le projet** prend du retard)

### Comment l'identifier dans un Gantt ?

1. Repère toutes les **chaînes de tâches dépendantes** du début à la fin.
2. Calcule la durée totale de chaque chaîne.
3. La **plus longue** = chemin critique.

### Application au sujet (Question 3 — sur l'autre Gantt)

D'après les tâches listées :
- Identifier les exigences → 02/02–04/02
- Concevoir l'architecture → 05/02–07/02
- Créer les maquettes → 10/02–12/02
- Planifier les ressources → 13/02–14/02
- Développer les fonctionnalités → 17/02–28/02
- Intégrer les API externes → 03/03–14/03
- Tester les fonctionnalités → 17/03–28/03
- Corriger les bogues → 31/03–11/04
- Effectuer les tests unitaires → 03/03–07/03 (en parallèle des API)
- Effectuer les tests d'intégration → 17/03–21/03 (en parallèle des tests fonctionnels)
- Valider avec les utilisateurs → 14/04–18/04
- Préparer la version finale → 21/04–25/04

👉 Le **chemin critique** suit la **branche la plus longue** :

```
Identifier les exigences
 → Concevoir l'architecture
  → Créer les maquettes
   → Planifier les ressources
    → Développer les fonctionnalités
     → Intégrer les API externes
      → Tester les fonctionnalités
       → Corriger les bogues
        → Valider avec les utilisateurs
         → Préparer la version finale
```

Soit du **02/02 au 25/04/2025**.

Les "tests unitaires" et "tests d'intégration" sont **en parallèle** d'autres tâches plus longues → ils **ne sont PAS sur le chemin critique**.

---

### Question 4 du sujet : « Si les tests unitaires sont décalés d'une semaine, la date de fin change-t-elle ? »

👉 **NON.** Les tests unitaires (03/03 → 07/03) ne sont **pas sur le chemin critique**. Ils ont une **marge** (ils se déroulent pendant que l'intégration des API se fait, qui est plus longue). Décaler d'une semaine cette tâche reste dans sa marge → **la date de fin du projet ne change pas**.

> 💡 Règle générale : **un retard sur une tâche hors chemin critique ne décale pas le projet, tant qu'il reste dans la marge**.

---

## 2.7 Question 8 : Quelle phase consiste à contrôler la conformité d'un produit ?

👉 La **phase de tests** (plus précisément **les tests et la validation / recette**).

Plus précisément, on distingue :
- **Tests unitaires** : on vérifie chaque morceau de code isolé.
- **Tests d'intégration** : on vérifie que les morceaux fonctionnent ensemble.
- **Tests fonctionnels** : on vérifie que le produit fait ce qui est attendu.
- **Recette / validation utilisateur (UAT)** : le client (MOA) valide le produit final.

---

## 2.8 Avantages et inconvénients de la gestion traditionnelle

### ✅ Avantages (Question 9)

- **Structure claire** et **étapes bien définies**.
- **Documentation complète** (cahier des charges, specs…) → utile pour la maintenance.
- **Planification précise** dès le départ (budget, délai connus).
- **Adapté aux projets complexes** avec des exigences stables.
- **Suivi facile** grâce aux jalons et au Gantt.
- **Bonne traçabilité**.
- **Rôles et responsabilités clairs** (MOA / MOE / chef de projet).
- Idéal pour les projets à **fortes contraintes réglementaires**.

### ❌ Inconvénients (Question 10)

- **Manque de flexibilité** : difficile de changer en cours de route.
- **Le client ne voit le produit qu'à la fin** → risque de décalage avec ses besoins réels.
- **Détection tardive des problèmes** (souvent à la phase de tests, donc tard).
- **Phase de spécifications longue** avant tout démarrage concret.
- **Risque élevé** si les besoins évoluent.
- **Démotivation possible de l'équipe** sur les longs projets.
- **Effet tunnel** : peu d'interactions avec le client pendant la réalisation.
- **Surcoût élevé** en cas de modifications tardives.

---

# 🎯 Application complète au sujet de janvier 2025

Je récapitule les réponses-types pour t'auto-évaluer :

### Dossier 1 — Agile

| Q | Réponse synthétique |
|---|---|
| 1 | Le **Product Owner** valide les user stories pour les passer en "Done". |
| 2 | **Oui**, le Sprint Backlog existe. C'est le sous-ensemble du Product Backlog que l'équipe s'engage à réaliser pendant le sprint en cours. Il est géré par l'équipe de dev. |
| 3 | Le **Product Owner** est responsable du Product Backlog. |
| 4 | Voir section 1.4 (3-4 avantages + 3-4 inconvénients). |
| 5 | C'est un **tableau Kanban**. |
| 6 | La carte **« Codage »** (team2, échéance 28/02/2025) — c'est la seule du To Do à avoir une date d'échéance. |
| 7 | **team2** — elle s'occupe du déploiement (4 avril 2025), qui est la tâche la plus tardive. |
| 8 | Voir section 1.3 (titre, responsable, date, priorité, description, critères d'acceptation, dépendances, tags). |

### Dossier 2 — Traditionnelle

| Q | Réponse synthétique |
|---|---|
| 1 | Gantt à dessiner (voir section 2.5 ci-dessus). |
| 2 | **70 jours-homme** (10 + 40 + 15 + 5), si on considère 1 personne/phase. |
| 3 | Chemin critique : exigences → archi → maquettes → ressources → dev → API → tests fonctionnels → corrections bugs → validation utilisateurs → version finale (= du 02/02 au 25/04). |
| 4 | **Non**, les tests unitaires ne sont pas sur le chemin critique → ils ont une marge. La date de fin ne change pas. |
| 5 | Le **cahier des charges** (CdCF — cahier des charges fonctionnel). |
| 6 | La MOA **exprime le besoin** : objectifs, contraintes, utilisateurs cibles, validation. Elle rédige (ou commande) le cahier des charges. |
| 7 | **L'identification (ou décomposition) des tâches** — WBS. |
| 8 | La phase de **tests et validation** (incluant tests unitaires, intégration, recette utilisateur). |
| 9 | Voir section 2.8 (avantages). |
| 10 | Voir section 2.8 (inconvénients). |

---

# 📌 Fiche mémo de dernière minute (à relire 30 min avant l'épreuve)

### Scrum — les 3 piliers à retenir absolument

- **3 rôles** : Product Owner / Scrum Master / Équipe de développement
- **3 artefacts** : Product Backlog / **Sprint Backlog** / Incrément
- **5 événements** : Sprint / Planning / Daily / Review / Rétrospective

### Qui fait quoi en Scrum ?

- **Product Owner** = QUOI (priorise le backlog, valide les stories)
- **Scrum Master** = COMMENT bien travailler (facilite, lève les blocages)
- **Équipe Dev** = FAIRE (auto-organisée, décide de l'implémentation)

### Kanban — l'essentiel

- Visualisation du flux par **colonnes** : To Do → In Progress → Done (parfois Test, Review…)
- **WIP limit** : limiter le travail en cours
- Une **carte** = une tâche, avec : titre, responsable, date, description, priorité

### Traditionnel — l'essentiel

- **MOA = client** ; **MOE = réalisateur**
- **Cahier des charges** = QUOI et POUR QUI (pas COMMENT)
- **Première étape de planification** = identifier les tâches (WBS)
- **Jour-homme** = 1 personne × 1 jour de travail
- **Chemin critique** = la chaîne de tâches la plus longue. Tout retard sur le chemin critique = retard du projet
- **Marge** : un retard sur une tâche HORS chemin critique ne décale rien tant qu'on reste dans sa marge

### Cycle en V — les phases miroir

```
Cahier des charges  ↔  Recette utilisateur (MOA valide)
Spécifications      ↔  Tests d'intégration
Conception          ↔  Tests unitaires
       ↘ Développement ↙
```

---

## 🚀 Conseils de méthode pour le jour J

1. **Lis tout le sujet avant de commencer**, identifie les questions faciles → fais-les en premier.
2. **Le Gantt prend du temps** : prévois 20-25 minutes pour le dessiner proprement.
3. **Justifie tes réponses** : sur les questions ouvertes (avantages/inconvénients, chemin critique, etc.), donne **3-4 éléments** par point.
4. **Sois précis sur le vocabulaire** : "Product Owner", "Sprint Backlog", "cahier des charges", "chemin critique" — utilise les bons termes.
5. **Pas de panique sur le chemin critique** : il suffit de lister la chaîne de tâches la plus longue.

Bonne révision ! 💪

Si tu veux qu'on enchaîne avec le D41.2 (Java, SQL, MongoDB), dis-moi.
