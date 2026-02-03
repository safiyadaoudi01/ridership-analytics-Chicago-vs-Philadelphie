# Ridership Analytics – Chicago vs Philadelphie

### Description du projet
Ce projet vise à analyser et comparer la fréquentation des transports urbains à Chicago et Philadelphie, en combinant :
- données historiques (mensuelles / journalières)
- données temps réel (fréquence, ponctualité des lignes)

L’objectif est de construire un dashboard Power BI interactif permettant de :
- suivre l’évolution du ridership par ligne et type de jour,
- comparer les performances entre les deux villes,
- détecter les anomalies entre valeurs observées et valeurs prédites à partir des données historiques et temps réel,
- fournir des recommandations stratégiques pour optimiser les services.

### Objectifs spécifiques
- Importer et nettoyer les données hétérogènes (RDF, CSV, APIs temps réel).
- Construire un modèle en étoile pour l’analyse dans Power BI.
- Calculer des KPIs avancés via DAX (ex. MoM, volatilité, indice de performance).
- Réaliser des analyses statistiques avec Python (test t, ANOVA, corrélation).
- Développer un dashboard Power BI interactif (3 pages principales).

### Structure du repository
```
├── data/
│   ├── chicago_rdf/           # Données historiques RDF de Chicago
│   ├── philadelphia_csv/      # Données historiques CSV de Philadelphie
│   ├── api_data/              # Données temps réel (CTA / SEPTA)
├── notebooks/
│   ├── etl_preparation.ipynb  # Nettoyage et transformation des données
│   ├── stats_analysis.ipynb   # Analyses statistiques Python
├── powerbi/
│   ├── ridership_analytics.pbix         # Fichier Power BI
├── scripts/
│   ├── rdf_to_csv.py          # Script Python pour convertir RDF → CSV
├── README.md                  # Ce fichier
└── requirements.txt           # Librairies Python nécessaires
```
### Installation et configuration

Cloner le repository :

```bash
git clone https://github.com/<username>/ridership-analytics.git
cd ridership-analytics
```
Installer les dépendances Python :

```bash
pip install -r requirements.txt
```
Préparer les données :
- Placer les fichiers RDF/CSV dans le dossier data/.
- Exécuter rdf_to_csv.py pour convertir les fichiers RDF de Chicago.
- Vérifier les clés API pour les flux temps réel (CTA / SEPTA) et les ajouter dans api_data/.
- Ouvrir le dashboard Power BI (ridership_analytics.pbix) et connecter les données traitées.

### Contenu du projet

**ETL / Python** : préparation, nettoyage, harmonisation des données.

**Modélisation Power BI** : tables de faits et dimensions, modèle en étoile.

**KPIs DAX** : croissance mensuelle, indice de performance, pourcentage de jours au-dessus de l’objectif, volatilité.

**Statistiques Python** : test t, ANOVA, Shapiro-Wilk, corrélations.

**Dashboard Power BI** : 3 pages interactives avec filtres, comparaisons et visualisations statistiques.

 ### Résultats attendus
- Comparaison des performances entre Chicago et Philadelphie.
- Identification des anomalies et des écarts entre valeurs observées et prédites.
- Recommandations stratégiques pour l’optimisation des services de transport.

### Technologies utilisées

**Python :** Pandas, NumPy, SciPy, Matplotlib/Seaborn

**Power BI :** Dashboard interactif, DAX, modèle en étoile

**APIs :** CTA Bus Tracker, SEPTA TransitView

**Formats :** CSV, RDF, JSON

### 🔗 Liens utiles

[CTA Bus Tracker API](https://www.transitchicago.com/developers/bustracker/)
