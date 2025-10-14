# Anomalies-bourse-

# 📈 Stock Market Anomaly Detection

## 🎯 Objectif
Ce projet vise à détecter les **anomalies sur les marchés boursiers** à partir de données historiques de prix et de volumes.  
L’idée est d’identifier automatiquement les jours où une action présente un comportement anormal (hausse ou baisse extrême).

---

## 🧩 Données
Le dataset contient les colonnes :
- `date`
- `ticker`
- `open`, `high`, `low`, `close`, `adj close`
- `volume`

Chaque ligne correspond à une observation journalière d’un titre boursier.

Utilisation de PYTHON pour l'ETL avec les librairies pandas, seaborn, matplotlib

## ⚙️ Méthodologie
1. Nettoyage et préparation des données 
2. Calcul du rendement journalier par ticker (`pct_change()`)  
3. Calcul du **z-score global** sur les rendements  
4. Détection des anomalies (|z-score| > 3)  
5. Visualisation des anomalies par ticker et dans le temps  

---

## 📊 Résultats clés
- Détection automatique de jours anormaux sur certains titres  
- Mise en évidence de comportements extrêmes (pics de volatilité ou de volume)  
- Graphiques par ticker montrant les anomalies (points rouges)

---

## 🧠 Conclusion
Le projet montre qu’une approche simple à base de **statistiques descriptives** suffit pour repérer des anomalies de marché pertinentes.  
Ces méthodes peuvent servir de base à un système d’alerte pour traders, analystes ou outils de suivi du risque.

---

## 🚀 Améliorations possibles
- Ajout de modèles ML (Isolation Forest, Local Outlier Factor, DBSCAN)  
- Intégration de données externes (actualités, indices macroéconomiques)  
- Création d’un tableau de bord Power BI ou web interactif

---

