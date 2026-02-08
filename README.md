# Ridership Analytics – Chicago vs Philadelphie

## Description du projet
Ce projet vise à analyser et comparer la fréquentation des transports urbains à Chicago et Philadelphie.

L’objectif est de construire un dashboard Power BI interactif permettant de :
- Suivre l’évolution du ridership par **route** et par **mode de transport** (Bus / Rail)
- Comparer les performances entre les deux villes
- Fournir des recommandations stratégiques pour optimiser les services

## Objectifs spécifiques
- Importer et nettoyer les données hétérogènes (RDF, CSV, Excel).
- Construire un modèle en étoile pour l’analyse dans Power BI.
- Calculer des KPIs avancés via DAX, par exemple :
  - Croissance mensuelle (MoM Growth %)
  - % de différence de ridership entre villes
  - Moyenne et somme du ridership par route et par mode
- Développer un dashboard Power BI interactif avec deux pages principales :
  - Route Analysis
  - Mode Analysis

## Structure du repository
```
├── data/
|   ├── chicago_csv/           # CSV généré après transformation des RDF (routes)
|   ├── chicago_excel/         # Données modes de transport pour Chicago
│   ├── chicago_rdf/           # Données brutes RDF de Chicago par route (19 fichiers)
│   ├── philadelphia_csv/      # Données routes et modes de Philadelphie (CSV)
│   ├── processed/             # CSV finaux prêts à l’analyse
├── notebooks/
│   ├── etl_preparation.ipynb  # Nettoyage et transformation des données
├── powerbi/
│   ├── ridership_analytics_chicago-vs-philadelphia.pbix
├── scripts/
│   ├── rdf_to_csv.py          # Script Python pour convertir RDF → CSV (Chicago)
├── slides/
│   ├── Urban_Mobility_Chicago_Philadelphia_Comparison.pdf
├── README.md                  # Ce fichier
└── requirements.txt           # Librairies Python nécessaires
```
## Installation et configuration

Cloner le repository :

```bash
git clone https://github.com/safiyadaoudi01/ridership-analytics-Chicago-vs-Philadelphie.git
cd ridership-analytics-Chicago-vs-Philadelphie
```
Installer les dépendances Python :

```bash
pip install -r requirements.txt
```
Préparer les données :
- Placer les fichiers RDF/CSV dans le dossier data/.
- Exécuter rdf_to_csv.py pour convertir les fichiers RDF de Chicago.
- Ouvrir le dashboard Power BI (ridership_analytics_chicago-vs-philadelphia.pbix) et connecter les données traitées.

## Contenu du projet

**ETL / Python** : préparation, nettoyage, harmonisation des données.

**Modélisation Power BI** : tables de faits et dimensions, modèle en étoile.

**KPIs DAX** : croissance mensuelle, indice de performance, pourcentage de jours au-dessus de l’objectif, volatilité.

**Dashboard Power BI** : 2 pages interactives avec filtres, comparaisons et visualisations statistiques.


## Technologies utilisées

**Python :** Pandas, NumPy, SciPy, Matplotlib/Seaborn

**Power BI :** Dashboard interactif, DAX, modèle en étoile

**Formats :** CSV, RDF, EXCEL

## Dashboard Power BI – Visualisations

Cette section présente les écrans du dashboard développés pour l’analyse du ridership à Chicago et Philadelphie.

### Page Route Analysis
Visualisations :

| Visual               | Description                                                                                                                                                                                              |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Cartes KPI           | - Volume total de passagers – Chicago<br>- Volume total de passagers – Philadelphie<br>- % différence ridership (réf Philadelphie)<br>- % différence ridership (réf Chicago)<br>- Nombre total de routes |
| Graphique en courbes | Axe X : Date, Axe Y : MoM Growth %, Légende : City. Suivi de la croissance mensuelle par ville.                                                                                                          |
| Histogramme empilé   | Axe X : Route, Axe Y : Moyenne de avg_ridership, Légende : City. Comparaison directe des routes les plus fréquentées.                                                                                    |

Screenshot suggéré :
![page_route_analysis](https://github.com/user-attachments/assets/02136db7-192d-4e21-b818-f698a9efbbdc)

### Page Mode Analysis
Visualisations :

| Visual                 | Description                                                                                         |
| ---------------------- | --------------------------------------------------------------------------------------------------- |
| Cartes KPI             | Moyenne de avg_ridership – Chicago<br>Moyenne de avg_ridership – Philadelphie (filtrées par mode)   |
| Graphiques en secteurs | Répartition du ridership par mode pour chaque ville (Somme de avg_ridership), avec filtre par année |
| Graphique en aires     | Axe X : Date, Axe Y : Somme de avg_ridership Chicago et Philadelphie, filtres : année et mode       |
| Histogramme groupé     | Axe X : Mode, Axe Y : Somme de avg_ridership par ville, filtre : année                              |

Screenshot suggéré :

![page_mode_analysis](https://github.com/user-attachments/assets/7004b979-5353-4ecc-a171-bb0e92889309)

