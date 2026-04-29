# 📊 Prédiction des ventes - MarketCorp

## 📌 Description du projet
Ce projet consiste à construire un modèle de Machine Learning capable de prédire les ventes (`Item_Outlet_Sales`) de produits dans des supermarchés MarketCorp à partir de certaines caractéristiques comme le poids, la visibilité, le prix et le type de produit.

Le dataset fourni contient des données brutes avec des valeurs manquantes et des incohérences. Le projet suit donc toutes les étapes classiques d’un pipeline de Data Science, depuis l’importation et le nettoyage des données jusqu’à la modélisation et la prédiction.

---

## 🎯 Objectif
L’objectif principal est d’estimer les ventes des produits à l’aide d’un modèle simple de régression linéaire, tout en gardant une approche claire, basique et compréhensible pour un débutant.

Le projet comprend :
- l’importation des données
- l’audit du dataset
- le nettoyage des données
- le feature engineering
- l’analyse exploratoire des données
- l’entraînement d’un modèle de Machine Learning
- la génération de prédictions sur de nouvelles données

---

## 🛠️ Technologies utilisées
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## 📂 Fichiers du projet
- `marketcorp_sales.csv` : données d'entraînement
- `marketcorp_unseen_data.csv` : nouvelles données à prédire
- `marketcorp_predictions.csv` : fichier de sortie contenant les prédictions
- `notebook.ipynb` : notebook principal
- `README.md` : description du projet

---

## ⚙️ Étapes du projet

### 1. Audit des données
Dans cette première étape, le dataset est inspecté pour mieux comprendre sa structure.  
On affiche :
- le nombre de lignes et de colonnes
- les types de données de chaque colonne
- les valeurs manquantes par colonne
- un aperçu des premières lignes

### 2. Nettoyage des données
Plusieurs opérations de nettoyage sont réalisées :
- les valeurs manquantes de `Item_Weight` sont remplacées par la moyenne
- les valeurs manquantes de `Outlet_Size` sont remplacées par `"Inconnu"`
- les valeurs égales à `0` dans `Item_Visibility` sont considérées comme incohérentes et remplacées par la médiane

### 3. Feature Engineering
La colonne `Item_Fat_Content` contient plusieurs écritures différentes pour désigner les mêmes catégories, comme :
- `LF`
- `low fat`
- `reg`

Ces valeurs sont standardisées pour ne garder que :
- `Low Fat`
- `Regular`

### 4. Analyse Exploratoire des Données (EDA)
Un petit dashboard est créé avec Matplotlib pour visualiser :
- la distribution des ventes avec un histogramme
- la répartition des tailles de magasin avec un diagramme en barres
- la relation entre le prix (`Item_MRP`) et les ventes (`Item_Outlet_Sales`) avec un nuage de points

### 5. Machine Learning
Un modèle de **Régression Linéaire Multiple** est entraîné en utilisant les variables suivantes :
- `Item_Weight`
- `Item_Visibility`
- `Item_MRP`
- `Item_Fat_Content`

La variable cible à prédire est :
- `Item_Outlet_Sales`

La colonne textuelle `Item_Fat_Content` est convertie en nombres :
- `Low Fat` → `0`
- `Regular` → `1`

Les données sont ensuite séparées en :
- 80 % pour l’entraînement
- 20 % pour le test

### 6. Évaluation du modèle
Le modèle est évalué à l’aide de deux métriques :
- **MAE (Mean Absolute Error)** : erreur moyenne entre la prédiction et la vraie valeur
- **RMSE (Root Mean Squared Error)** : erreur globale qui pénalise davantage les grosses erreurs

Exemple de résultats obtenus :
- **MAE ≈ 677 €**
- **RMSE ≈ 922 €**

Ces résultats montrent que le modèle fonctionne correctement pour une première approche simple.

### 7. Prédictions sur de nouvelles données
Les mêmes étapes de nettoyage et de transformation sont appliquées au fichier `marketcorp_unseen_data.csv`.

Le modèle génère ensuite des prédictions qui sont enregistrées dans :
- `marketcorp_predictions.csv`

---

## 📈 Résultat
Le projet permet de passer d’un dataset brut à un modèle de prédiction fonctionnel, en suivant une méthode claire et structurée.

Il s’agit d’un bon projet d’introduction au Machine Learning, particulièrement adapté à :
- un débutant en Data Science
- un projet académique
- un portfolio GitHub

---

## 🚀 Améliorations possibles
Plusieurs améliorations peuvent être envisagées :
- tester des modèles plus performants comme Random Forest ou XGBoost
- ajouter plus de variables explicatives
- normaliser les données
- utiliser la validation croisée
- optimiser les hyperparamètres du modèle

---

## 📚 Conclusion
Ce projet permet de comprendre et de pratiquer les bases d’un pipeline complet de Machine Learning :
- importation des données
- nettoyage
- transformation
- visualisation
- modélisation
- évaluation
- prédiction

C’est un projet simple, pédagogique et utile pour débuter en Data Science.

