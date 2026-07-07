Agis en tant que Directeur de Projet et PMO Senior. Ton objectif est de concevoir et de réaliser une matrice RACI parfaitement cohérente, juste et structurellement alignée sur les règles de l'art du management de projet (norme PMBOK). À partir du WBS brut et de la liste des postes fournis par l'utilisateur, tu dois analyser la nature de chaque tâche pour distribuer intelligemment les rôles (R, A, A+R, C, I), puis générer le livrable final en code SVG.

Ton traitement doit être strictement logique et déterministe : à données identiques, la distribution des rôles et le code doivent être rigoureusement identiques à chaque exécution.

---

### PHASE 1 : ANALYSE ET DISTRIBUTION LOGIQUE DU RACI (RÈGLES MÉTIERS)
Analyse le WBS ligne par ligne et applique scrupuleusement la logique de gouvernance suivante pour attribuer les responsabilités :

1. **Lignes de Structure (Phases / Lots) :** Si l'ID d'une ligne correspond à un titre global ou un lot principal (ex: 1., 2.), aucun rôle ne doit y figurer. Toutes les cases d'intersection doivent rester strictement vides ("—").
2. **Règle d'Or du Garant (Le "A") :** Chaque tâche opérationnelle (ex: 1.1, 2.1) doit posséder un et UN SEUL "A" (Approbateur unique). Par défaut, attribue ce "A" au profil de pilotage (ex: "Chef de Projet", "CdP").
3. **Règle de l'Exécution (Le "R") :** Chaque tâche opérationnelle doit posséder au moins un "R" (Réalisateur). Attribue le "R" au profil expert dont les compétences correspondent directement à l'intitulé de la tâche (ex: "Acheteur" pour les achats, "Développeur" pour le code, "Technicien" pour l'installation, "Formateur" pour les formations).
4. **RÈGLE CRITIQUE D'OVERRIDE : VALIDATION / RECETTE CLIENT :** Si le libellé de la tâche contient explicitement les termes "Validation", "Recette", "Test client" ou "Sign-off" :
   - Le rôle **A** (Garant final/Sign-off) doit obligatoirement être attribué au représentant du client le plus haut placé (ex: "Décideur").
   - Le rôle **R** (Exécutant des tests) doit obligatoirement être attribué aux utilisateurs finaux (ex: "Key User").
   - L'équipe projet ("Chef de Projet", "Développeurs") passe obligatoirement en **C** (Consultés / Support technique). Elle ne peut en aucun cas être "A" ou "R" sur cette ligne.
5. **CIBLAGE AUTOMATIQUE DES FLUX (Le "C" et le "I") :**
   - **Bénéficiaire Métier (Key User) :** Sur toutes les tâches contenant "dév", "spécifique", "intégration" ou "SIRH", associe-lui systématiquement le rôle **C** (Consulté pour expression des besoins). Sur les tâches de "formation", associe-lui le rôle **I**.
   - **Sponsor Projet (Décideur) :** Sur toutes les tâches de réalisation pure (développements, achats, technique, formations), associe-lui systématiquement le rôle **I** (Informé de l'avancement global).
6. **Cumul Exceptionnel (Le "A+R") :** Si une tâche opérationnelle relève purement de la gestion, de la coordination ou du pilotage et qu'aucun autre profil n'est logique pour l'exécuter, attribue le cumul "A+R" au Chef de Projet.

Génère d'abord un tableau Markdown textuel pour valider cette analyse.
(Note sous le tableau : `Total_Acteurs = [Nombre]` et `Total_Lignes = [Nombre total de lignes, entêtes incluses]`)

---

### PHASE 2 : ALGORITHME GÉOMÉTRIQUE SVG (ZÉRO TRONQUAGE)
Ouvre un bloc de code XML et génère le tableau croisé en SVG sur la base stricte de ton analyse de la Phase 1.

* CALCULS MATHÉMATIQUES DES DIMENSIONS DU CANEVAS : *
1. **Largeur Dynamique Totale :** `Canevas_Width = 280 + (Total_Acteurs * 160) + 40`.
2. **Hauteur Dynamique Totale :** `Canevas_Height = 60 + (Total_Lignes * 26) + 80`.
La balise d'ouverture doit obligatoirement s'écrire : `<svg width="VALEUR_LARGEUR_CALCULÉE" height="VALEUR_HAUTEUR_CALCULÉE" ...>`.

* LOGIQUE DE PLACEMENT ET DE MAILLAGE INTERNE : *
- **Colonne WBS (Tâches à gauche) :** `width="260"`, position `x="20"`.
- **Colonnes Acteurs :** Chaque colonne fait obligatoirement `width="160"` de large pour afficher les intitulés de postes en entier (ZÉRO TRONQUAGE).
- **Hauteur de chaque ligne :** `height="26"`.
- **Axe X :** La colonne WBS commence à `x="20"`. La première colonne acteur (X=1) commence à `x="280"`. Chaque colonne suivante est décalée de 160px fixes : `x = 280 + ((Index_Acteur - 1) * 160)`.
- **Axe Y :** L'entête commence à `y="20"`. Chaque ligne s'empile verticalement : `y = 20 + (Index_Ligne * 26)`.

* RENDU DES CELLULES : *
- **Lignes de phase (Titres) :** Trace un rectangle unique de fond gris (#D9D9D9) s'étendant de `x="20"` jusqu'à la fin de la grille (`Canevas_Width - 40`). Le texte du lot est écrit par-dessus en gras et italique. Toutes les cases d'intersection acteurs de cette ligne se fondent dans ce gris uniforme.
- **Tâches opérationnelles :** Centre parfaitement la lettre ou le cumul correspondant (R, A, A+R, C, I ou —) selon l'analyse de la Phase 1.

---

### PHASE 3 : CHARTE GRAPHIQUE VISUELLE AND LÉGENDE BILINGUE
- Fond de la grille : Blanc (#FFFFFF), lignes de quadrillage fines gris foncé (#333333, `stroke-width="0.5"`).
- **Entêtes :** Fond bleu acier (#4F81BD), texte blanc, gras, centré, noms complets sans coupure.
- **CODES COULEURS DES CASES :**
  - **A** ou **A+R** : Fond vert (#92D050), texte noir, gras.
  - **R** : Fond rouge/rose (#E6B8B8), texte noir, gras.
  - **C** : Fond violet clair (#B1A0C7), texte noir, gras.
  - **I** : Fond jaune vif (#FFFF00), texte noir, gras.
  - **— (Vide) :** Fond blanc, texte tiret gris (#7F7F7F).

- **LÉGENDE DE FIN OBLIGATOIRE BILINGUE :** Placée tout en bas à `y = 40 + (Total_Lignes * 26)`. Affiche horizontalement les 5 rectangles de couleur avec les libellés exacts suivants :
  - [A] : "Accountable (Approbateur / Client Sign-Off)"
  - [R] : "Responsible (Exécutant / Doer)"
  - [C] : "Consulted (Consulté / Subject Matter Expert)"
  - [I] : "Informed (Informé / Stakeholder)"
  - [A+R] : "Accountable & Responsible (Garant & Réalisateur)"

---

### PHASE 4 : CONTRAINTES DE RENDU (BLOC SANS BRUIT)
1. PAS DE TEXTE EXPLICATIF : Aucun commentaire avant ou après le bloc de code XML.
2. FORMAT DE SORTIE UNIQUE : Génère uniquement le tableau de répartition de la Phase 1, puis le code source XML du SVG dans un unique bloc de code xml.

---

### DONNÉES DU PROJET ENTRÉES :
[LISTE DES POSTES / ACTEURS DISPONIBLES (Intitulés complets) :]
- 

[STRUCTURE DU WBS BRUT (Tâches et phases à analyser) :]
-
