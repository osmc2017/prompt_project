# prompt_project


Voici la version corrigée, reprenant exactement la structure et les détails de sorties du premier modèle, tout en intégrant avec une précision chirurgicale les éléments d'entrée requis :

```markdown
# 🛠️ Suite d'Outils PMO & Rendu Visuel SVG Automatique

Cette suite regroupe **4 prompts structurés et déterministes** conçus pour automatiser la gouvernance, la planification, le contrôle financier et l'architecture de vos projets. 

Chaque outil agit comme un robot-compilateur : il prend vos données brutes, applique des règles métiers strictes (normes PMBOK / EVM) et génère instantanément un tableau ou graphique vectoriel au format **SVG**, sans aucun risque de texte tronqué ou de décalage graphique.

---

## 🧭 Ordre Logique d'Utilisation, Entrées & Sorties

Pour maximiser l'efficacité de la suite sur un nouveau projet, il est fortement recommandé de suivre l'ordre chronologique du cycle de vie PMO ci-dessous :


```

[ 1. Organigramme WBS ] ➔ [ 2. Matrice RACI ] ➔ [ 3. Planification PERT ] ➔ [ 4. Suivi EVM (Valeur Acquise) ]

```

### 1. 📂 Étape 1 : Conception du WBS (Work Breakdown Structure)
* **Quand l'utiliser :** Dès le lancement du projet, lors de la phase de cadrage.
* **Objectif :** Poser les fondations et cartographier tout le périmètre.
* **Données d'Entrée à fournir :** * La liste textuelle brute de vos lots (Niveau 1) et de vos sous-lots (Niveau 2) sous forme de liste à puces ou de texte numéroté.
* **Livrables de Sortie générés :** * Un tableau d'ancrage logique textuel listant les ID hiérarchiques et les niveaux.
  * L'organigramme technique structurel en blocs d'arborescence descendante au format SVG.

### 2. 👥 Étape 2 : Attribution des Responsabilités (Matrice RACI)
* **Quand l'utiliser :** Juste après avoir figé votre WBS, avant de démarrer l'exécution.
* **Objectif :** Définir la gouvernance et distribuer les rôles de manière fluide.
* **Données d'Entrée à fournir :** * La liste des rôles, postes ou acteurs disponibles (Axe Horizontal).
  * La structure complète de votre WBS brut (Axe Vertical).
* **Livrables de Sortie générés :** * Un tableau Markdown textuel validant la répartition logique des rôles.
  * La matrice RACI croisée, colorée et bilingue avec sa légende en SVG.

### 3. ⏳ Étape 3 : Planification et Chemin Critique (PERT / Loi de Brooks)
* **Quand l'utiliser :** Lors de la phase de planification détaillée, pour fixer le calendrier.
* **Objectif :** Calculer les dates au plus tôt/plus tard, les marges et identifier le chemin critique via la loi de Brooks.
* **Données d'Entrée à fournir :** * Le tableau des tâches avec leurs intitulés, leurs durées initiales et leurs antécédents directs.
  * Le nombre d'ETP (personnes) affectés par tâche *(optionnel)*.
  * Le TJM de l'équipe *(optionnel, uniquement pour le calcul financier)*.
* **Livrables de Sortie générés :** * Le tableau d'ancrage et de contrôle logique (ES, EF, LS, LF, Marge, Rang, Statut critique).
  * La chaîne textuelle du chemin critique et le bilan financier/humain.
  * Le diagramme de réseau PERT interconnecté (boîtes de jalons et liaisons critiques rouges) en SVG.

### 4. 📉 Étape 4 : Suivi et Contrôle Budgétaire (EVM - Valeur Acquise)
* **Quand l'utiliser :** En phase d'exécution (par exemple, chaque mois ou à des jalons clés).
* **Objectif :** Analyser la santé financière et temporelle du projet.
* **Données d'Entrée à fournir :** * Le tableau de planification initial (Lots, Budgets et mois/périodes cibles prévus).
  * Le tableau de suivi à date (Lots et pourcentage d'avancement réel actuel).
  * Le tableau des coûts réels (Dépenses cumulées déjà payées par lot).
  * La période clé exacte de l'analyse (ex: "M5").
* **Livrables de Sortie générés :** * Tableau 1 : Planification Temporelle (CBTP Mensuel & Cumulé).
  * Tableau 2 : Analyse par Lot à la Période Clé (BAC, CBTE, CRTE).
  * Tableau 3 : Synthèse des indicateurs de performance textuels (CV, CPI, SV, SPI, EAC).
  * Le graphique vectoriel de la courbe en S (trajectoire théorique vs points réels) en SVG.

---

## 🚀 Comment utiliser ces prompts ?

Chaque invite (prompt) du dépôt suit le même protocole d'utilisation :

1. **Copiez l'intégralité du prompt en Markdown** correspondant à l'outil souhaité.
2. Ouvrez votre interface de modèle de langage (LLM). => des gem de gémini par exemple.
3. Allez tout en bas du prompt dans la section `### DONNÉES DU PROJET ENTRÉES :`.
4. Remplissez les sections ou les crochets par les **Données d'Entrée** spécifiées pour l'étape.
5. **Lancez la génération.**

> ⚠️ **Note importante sur le rendu visuel :** Les modèles génèrent le rendu graphique dans un bloc de code XML unique. Pour afficher votre graphique, copiez le code généré, collez-le dans un éditeur de texte, enregistrez le fichier avec l'extension `.svg` (ex: `mon_projet.svg`), puis ouvrez-le simplement dans n'importe quel navigateur web ou logiciel de dessin.

```
