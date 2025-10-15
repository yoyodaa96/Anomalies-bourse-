# Anomalies-bourse-

# 📈 Stock Market Anomaly Detection

Utilisation de python sur VS CODE pour analyser les anomalies de prix et de volume sur la bourse.

🎯 Objectif du projet

L’objectif de ce projet était de détecter et d’analyser des anomalies de marché à partir de données boursières historiques. En d’autres termes, identifier les jours où une action présente un comportement inhabituel, que ce soit par une variation de prix extrême ou un volume d’échanges anormal.

Les données utilisées contiennent les prix quotidiens de plusieurs entreprises (AAPL, MSFT, TSLA, GOOG, NFLX…), avec les colonnes classiques de marché : date, ticker, adj close, volume, etc.

🔍 Méthodologie

L’analyse a débuté par une phase de préparation des données, incluant la mise au bon format des dates, le tri chronologique et la vérification des types. Le prix ajusté (Adj Close) a été choisi comme référence, car il tient compte des splits et dividendes, rendant les comparaisons dans le temps plus fiables.

Ensuite, nous avons calculé le rendement journalier de chaque titre, c’est-à-dire la variation de son prix par rapport au jour précédent. Ces rendements ont été standardisés à l’aide du z-score, afin d’identifier les jours où la performance s’écarte significativement de la moyenne. Les jours où la valeur absolue du z-score dépassait un certain seuil (|z| > 3) ont été considérés comme des anomalies de prix.

La même approche a ensuite été appliquée au volume d’échanges. Cette étape a permis de repérer les jours où l’activité de marché était exceptionnellement forte ou faible, indépendamment de l’évolution du prix.

Enfin, nous avons comparé les anomalies de prix et celles de volume pour déterminer si les variations extrêmes de cours étaient confirmées par un volume anormal, signe d’un mouvement réellement soutenu par le marché.

📊 Résultats et interprétation
<img width="989" height="490" alt="image" src="https://github.com/user-attachments/assets/066e852b-f0e2-4f3f-bd43-f15f240995da" />

<img width="989" height="390" alt="image" src="https://github.com/user-attachments/assets/36b134dd-b957-4d1a-abe2-4eeda79fdec4" />

Les résultats obtenus montrent des comportements cohérents avec la réputation de chaque titre. Microsoft se démarque comme l’action la plus stable, avec très peu d’anomalies de prix (0,4 %). Apple, Google et Netflix présentent des variations modérées mais une activité de volume plus élevée, signe d’un marché souvent animé sans pour autant créer de fortes fluctuations de prix.

À l’inverse, Tesla affiche la plus forte proportion d’anomalies de prix (2 %), illustrant sa nature très volatile. Cependant, toutes ces anomalies ne sont pas accompagnées d’un volume exceptionnel, ce qui traduit une volatilité parfois spéculative.

Le rapprochement entre prix et volume révèle que pour Apple, Microsoft et Netflix, 100 % des anomalies de prix sont confirmées par un volume anormal. Cela indique des mouvements de marché solides, soutenus par une réelle intensité d’échanges. En revanche, Google et Tesla affichent une confirmation partielle (50 % et 40 %), traduisant des variations de prix plus indépendantes du comportement général des investisseurs.

🧠 Conclusion

Cette étude montre qu’une approche statistique simple permet déjà d’obtenir une lecture fine du comportement des titres boursiers. L’analyse croisée entre rendement et volume permet de distinguer les vraies anomalies de marché — c’est-à-dire celles qui reflètent une forte réaction des investisseurs — des fluctuations isolées ou du bruit.

En résumé, les titres comme Microsoft ou Apple se révèlent stables et cohérents, tandis que Tesla illustre la volatilité et la réactivité propres aux valeurs spéculatives.

Ce travail pourrait être enrichi par des approches de machine learning ou par l’intégration de données externes (actualités, indicateurs macroéconomiques) pour aller vers une détection d’anomalies plus intelligente et prédictive.
