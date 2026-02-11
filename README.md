# Analyse des Performances et Satisfaction des Transports Urbains avec Power BI

## Description du projet
Ce projet vise à analyser et comparer le **ridership des transports publics** entre **Chicago** et **Philadelphie** sur la période **2019–2025**, en se basant sur :
- les **modes de transport** (Bus, Rail),
- les **routes** (lignes de transport).

Le projet combine une approche **Data Engineering + Business Intelligence**, avec :
- **Python** pour l’EDA, le nettoyage et l’agrégation,
- **Power BI** pour la modélisation (schéma en étoile) et la visualisation.

---

## 🔗 Liens du projet
- **Confluence (documentation)**  
  https://fatimazahrabellala.atlassian.net/wiki/x/AQD_/

- **Jira (gestion du projet)**  
  https://fatimazahrabellala.atlassian.net/jira/software/projects/KAN/boards/1

---

## Objectifs
- Analyser l’évolution du ridership entre 2019 et 2025
- Comparer Chicago et Philadelphie par :
  - mode de transport (Bus vs Rail)
  - route
- Harmoniser des données hétérogènes
- Construire un modèle BI professionnel
- Fournir des indicateurs clairs pour l’aide à la décision

---

## Sources de données

### Philadelphia
- Average Daily Ridership by Mode  
- Average Daily Ridership by Route  

Données déjà **agrégées mensuellement** (moyennes journalières).

### Chicago
- Ridership Daily Boarding Totals (Bus & Rail) — Excel  
- Ridership Daily by Route — RDF  

Données **journalières**, nécessitant :
- filtrage temporel (2019–2025),
- agrégation mensuelle,
- harmonisation avec Philadelphia.

---

## Traitement des données

### Philadelphia
- Aucune valeur manquante critique
- Aucun doublon incohérent
- Valeurs positives et réalistes
- Aucune suppression ou correction manuelle

### Chicago – Mode
- Filtrage 2019–2025
- Vérification des valeurs numériques
- Agrégation mensuelle (moyenne journalière)
- Unpivot Bus / Rail → colonne unique `Mode`

Fichier final : `chicago_mode.csv`

### Chicago – Route
- Conversion RDF → CSV via Python
- Filtrage temporel
- Agrégation mensuelle par route
- Vérification des doublons

Fichier final : `chicago_route.csv`

---

## Modélisation Power BI (Schéma en étoile)

### Tables de faits
- Chicago_Mode
- Philadelphia_Mode
- Chicago_Route
- Philadelphia_Route

### Tables de dimensions
- Dim_Year
- Dim_Month
- City
- Modes
- Routes

### Relations
- Dimensions → Tables de faits (1 → *)
- Filtrage : Single Direction
- Modèle optimisé pour DAX et slicers

---

## Visualisations Power BI
- Évolution mensuelle du ridership (Bus & Rail)
- Comparaison Chicago vs Philadelphie
- Répartition du ridership total par ville
- Analyse des routes les plus performantes
- Impact de la pandémie (2020)

---

## Résultats clés
- Forte chute du ridership en 2020 (COVID-19)
- Reprise progressive à partir de 2021
- Le Bus est le mode le plus résilient
- Le Rail est plus sensible aux changements d’habitudes
- Chicago présente un volume de ridership plus élevé

---

## Recommandations
- Renforcer l’offre Bus
- Adapter le Rail aux nouveaux usages (télétravail)
- Optimiser les routes à faible performance
- Enrichir l’analyse avec des données externes (météo, événements)

---

## Conclusion
Ce projet démontre la valeur d’une approche **data-driven** pour l’analyse des transports urbains.  
La combinaison de Python et Power BI permet une analyse fiable, harmonisée et exploitable pour la prise de décision stratégique.

---

##  Auteur
**Fatimazahra Bellala**  


