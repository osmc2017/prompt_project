# prompt_project


# 🛠️ Suite d'Outils PMO & Rendu Visuel SVG Automatique

Cette suite regroupe **4 prompts structurés et déterministes** conçus pour automatiser la gouvernance, la planification, le contrôle financier et l'architecture de vos projets. 

Chaque outil agit comme un robot-compilateur : il prend vos données brutes, applique des règles métiers strictes (normes PMBOK / EVM) et génère instantanément un tableau ou graphique vectoriel au format **SVG**, sans aucun risque de texte tronqué ou de décalage graphique.

---

## 🧭 Ordre Logique d'Utilisation

Pour maximiser l'efficacité de la suite sur un nouveau projet, il est fortement recommandé de suivre l'ordre chronologique du cycle de vie PMO ci-dessous :


```

[ 1. Organigramme WBS ] ➔ [ 2. Matrice RACI ] ➔ [ 3. Planification PERT ] ➔ [ 4. Suivi EVM (Valeur Acquise) ]

```

### 1. 📂 Étape 1 : Conception du WBS (Work Breakdown Structure)
* **Quand l'utiliser :** Dès le lancement du projet, lors de la phase de cadrage.
* **Objectif :** Poser les fondations. Ce prompt structure vos lots et sous-lots de manière descendante et produit un arbre hiérarchique clair pour cartographier tout le périmètre.
* **Sortie :** Organigramme technique structurel en blocs SVG.

### 2. 👥 Étape 2 : Attribution des Responsabilités (RACI)
* **Quand l'utiliser :** Juste après avoir figé votre WBS, avant de démarrer l'exécution.
* **Objectif :** Définir la gouvernance. En croisant votre WBS et votre liste de postes, l'outil attribue de manière logique les rôles (**R**esponsible, **A**ccountable, **C**onsulted, **I**nformed) en sécurisant particulièrement les étapes clés comme la recette client.
* **Sortie :** Matrice RACI croisée, colorée et bilingue en SVG.

### 3. ⏳ Étape 3 : Planification et Chemin Critique (PERT / Loi de Brooks)
* **Quand l'utiliser :** Lors de la phase de planification détaillée, pour fixer le calendrier.
* **Objectif :** Calculer les dates au plus tôt/plus tard, les marges et identifier le chemin critique. L'outil intègre **la loi de Brooks**, ce qui signifie qu'il recalcule automatiquement les durées réelles si vous affectez plusieurs personnes (ETP) sur une même tâche pour compenser les pertes de communication.
* **Sortie :** Réseau PERT complet interconnecté (boîtes de jalons et liaisons critiques rouges) en SVG.

### 4. 📉 Étape 4 : Suivi et Contrôle Budgétaire (EVM)
* **Quand l'utiliser :** En phase d'exécution (par exemple, chaque mois ou à des jalons clés).
* **Objectif :** Analyser la santé financière et temporelle. À partir de vos budgets initiaux, du pourcentage d'avancement constaté et de vos dépenses réelles, l'outil calcule les indicateurs clés (`CPI`, `SPI`, `CV`, `SV`, `EAC`).
* **Sortie :** Tableaux financiers de contrôle et graphique vectoriel de la courbe en S (CBTP vs points réels CBTE/CRTE) en SVG.

---

## 🚀 Comment utiliser ces prompts ?

Chaque invite (prompt) du dépôt suit le même protocole d'utilisation :

1. **Copiez l'intégralité du prompt en Markdown** correspondant à l'outil souhaité.
2. Ouvrez votre interface de modèle de langage (LLM).
3. Allez tout en bas du prompt dans la section `### DONNÉES DU PROJET :`.
4. Remplissez les crochets par vos informations brutes (textes, listes, ou tableaux copiés depuis Excel).
5. **Lancez la génération.**

> ⚠️ **Note importante sur le rendu visuel :** Les modèles génèrent le rendu graphique dans un bloc de code XML unique. Pour afficher votre graphique, copiez le code généré, collez-le dans un éditeur de texte, enregistrez le fichier avec l'extension `.svg` (ex: `mon_raci.svg`), puis ouvrez-le simplement dans n'importe quel navigateur web ou logiciel de dessin.
