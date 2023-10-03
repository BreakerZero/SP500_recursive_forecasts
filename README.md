# Prédiction d'Indice Boursier et Stratégie de Trading
## Description

Ce projet utilise des réseaux de neurones pour prédire les mouvements de l'indice boursier SP500.
### Contenu

- Importation des données d'indices financiers depuis Yahoo Finance
- Analyse exploratoire des données
- Sélection des features via l'analyse de corrélation et le VIF
- Normalisation des données
- Recherche d'architecture neuronale via Optuna pour les features puis pour le modèle final
- Entraînement et validation des modèles
- Prédiction récursive et évaluation
- Stratégie de trading et évaluation de la performance

### Technologies

Ce projet utilise les bibliothèques et méthodes suivantes :

yfinance, numpy, pandas, tensorflow, sklearn, seaborn, XGboost, SARIMA, keras, optuna, matplotlib, scipy, bitsandbytes ainsi que les dépendances liés

### Démarche
#### Importation des Données

1. Importation de données de plusieurs indices financiers à partir de Yahoo Finance
2. Choix de l'indice pour l'analyse et la prédiction (ici SP500, la méthode est supposément adaptable sur d'autre indice avec une efficacité sensiblement identique)

#### Analyse Exploratoire des Données (EDA)

3. Étude de la corrélation entre les différentes features
4. Utilisation du VIF pour éviter la multicolinéarité

#### Normalisation des Données

5. Application de la normalisation Robust sur les features sélectionnées

#### Recherche d'Architecture Neuronale

6. Utilisation d'Optuna pour trouver la meilleure architecture pour les modèle de réseau de neurones pour chaque feature selon divers critères
7. Entraînement complet sur les 5 meilleures architectures trouvées par Optuna
8. Prédiction avec XGboost comme prédiction de secours en cas de prédiction peu satisfaisante avec les réseaux neuronaux
9. Prédiction faites avec SARIMA comme prédiction témoin
10. Évaluation des modèles en utilisant le RMSE

#### Prédiction Récursive et Évaluation

11. Utilisation du meilleur modèle pour faire des prédictions récursives
12. Évaluation du modèle en utilisant le MDA (Mean Directional Accuracy)
13. Comparaison avec un modèle naïf
14. Répétions de la recherche d'architecture et des prédiction récursives pour le modèle final

#### Stratégie de Trading

15. Élaboration d'une stratégie de trading basée sur les prédictions
16. Évaluation de la performance de la stratégie en utilisant des métriques (taux gain absolu et relatif, évolution du capital si suivi de stratégie, etc.)

#### Conclusion

17. Comparaison avec les performances du marché, perspectives d'évolution...

## Avertissement

Ce notebook est avant tout un challenge technique et ses résultats ne doivent pas être considéré comme un conseil financier ou une recommandation pour acheter ou vendre des actifs financiers. Investir en bourse comporte des risques et vous devriez consulter un conseiller financier professionnel avant de prendre toute décision d'investissement.

Ce notebook possède quelques erreurs et approximations techniques connues (la plupart référencés dans la conclusion et perspectives d'évolution), cette notion est à prendre en compte lors de votre appréciation de ce code.

Note importante : Les performances passées de ce modèle ne garantissent pas sa justesse pour les prédictions futures. Les marchés financiers sont influencés par une multitude de facteurs qui sont hors du contrôle de tout modèle prédictif. Utilisez les informations et la méthodologie de ce notebook à vos propres risques.
