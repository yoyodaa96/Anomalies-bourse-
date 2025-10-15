# Anomalies-bourse-

# 📈 Stock Market Anomaly Detection

Utilisation de python sur VS CODE pour analyser les anomalies de prix et de volume sur la bourse.

🎯 Objectif de départ

Détecter et analyser des anomalies de marché (jours “inhabituels”) sur plusieurs actions à partir d’un historique boursier, puis interpréter ces anomalies en croisant prix et volume.

🧩 Données utilisées

Colonnes : date, ticker, open, high, low, close, adj close, volume.

Plusieurs tickers (AAPL, MSFT, TSLA, GOOG, NFLX, …), observations journalières.

🔄 Démarche suivie (étape par étape)

Préparation des données

Conversion des dates, tri chronologique par ticker, contrôle des types.

Choix de Adj Close pour des prix comparables dans le temps (ajusté des splits/dividendes).

Calcul du rendement journalier

Variation quotidienne du prix par ticker (rendement relatif jour J vs J-1).

Acceptation des NaN en 1ʳᵉ ligne de chaque série (pas de veille) ou remplacement par 0 selon le besoin.

Standardisation (z-score) des rendements

Mise sur une échelle commune pour repérer les valeurs extrêmes par rapport au comportement habituel.

Détection d’anomalies de prix

Marquage des jours où le z-score (en absolu) dépasse un seuil (ex. |z| > 3).

Visualisation par ticker : courbe de prix + points rouges sur les jours anormaux.

Analyse du volume

Standardisation du volume (z-score) et détection des pics d’activité.

Visualisation dédiée (volume + anomalies volume) et comparaison avec les anomalies de prix.

Indicateurs de synthèse

Taux d’anomalies de prix par ticker (part de jours extrêmes).

Taux d’anomalies de volume par ticker.

Rapprochement : pourcentage d’anomalies de prix confirmées par un volume anormal le même jour (mesure de robustesse).

Zooms et validation

Zooms temporels autour de certains jours extrêmes pour valider visuellement la cohérence (pic/chute + activité).

📊 Résultats clés (exemple résumé sur ton jeu)

Taux d’anomalies prix : MSFT très faible (~0,4 %), AAPL modéré (~1,2 %), TSLA le plus élevé (~2 %).

Taux d’anomalies volume : AAPL et GOOG/NFLX plus souvent en pics d’activité que MSFT, TSLA plus équilibré.

Confirmation prix↔volume :

AAPL / MSFT / NFLX : 100 % des anomalies de prix accompagnées d’un volume anormal → mouvements crédibles.

GOOG : ~50 % ; TSLA : ~40 % → une partie des mouvements de prix sans pic de volume (volatilité intrinsèque/spéculative).

🧠 Interprétation

Titres stables (ex. MSFT) : peu d’anomalies prix, même si quelques jours de volume inhabituel → résilience.

Titres réactifs (ex. TSLA) : davantage d’anomalies prix, pas toujours confirmées par le volume → volatilité propre et sensibilité aux nouvelles.

Cas intermédiaires (AAPL/GOOG/NFLX) : profils mixtes ; AAPL montre beaucoup de pics de volume mais peu d’extrêmes de prix → activité élevée mais maîtrisée.

⚠️ Limites & pistes d’amélioration

Le seuil |z| > 3 est simple ; on peut l’ajuster ou le rendre adaptatif.

Ajouter des méthodes d’anomalies ML (Isolation Forest, LOF, DBSCAN) pour détecter des patterns non-linéaires.

Croiser avec des événements (news, résultats, macro) pour expliquer les jours extrêmes.

Déployer un dashboard (Power BI/Plotly) avec alertes sur anomalies prix+volume.

✅ Conclusion

L’approche révèle rapidement des jours atypiques et distingue les mouvements crédibles (prix et volume anormaux) des signaux bruités (prix extrême sans volume).
Elle offre une base solide pour un système d’alerte et une analyse de risque par ticker, tout en restant lisible et reproductible pour un portfolio.
