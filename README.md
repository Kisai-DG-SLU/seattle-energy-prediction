# README.md

# Seattle Energy Prediction

Ce projet vise à prédire la consommation d’énergie (Site EUI) et les émissions de CO₂ (Total GHG Emissions) des bâtiments non résidentiels de Seattle à partir de leurs caractéristiques structurelles (taille, usage, date de construction, localisation, etc.), en s’appuyant sur le relevé 2016.

## Table des matières

- [Contexte et objectifs](#contexte-et-objectifs)  
- [Structure du projet](#structure-du-projet)  
- [Installation et configuration](#installation-et-configuration)  
- [Organisation des données](#organisation-des-données)  
- [Flux de travail et notebooks](#flux-de-travail-et-notebooks)  
- [Usage du package `seattle_energy`](#usage-du-package-seattle_energy)  
- [Tests](#tests)  
- [Résultats](#résultats)  
- [Licence](#licence)  

## Contexte et objectifs

Seattle a pour ambition d’atteindre la neutralité carbone d’ici 2050. Les bâtiments non résidentiels représentent une part significative de la consommation énergétique et des émissions de GES. Ce projet propose un pipeline complet pour :

1. Explorer et nettoyer les données brutales issues du benchmarking énergétique de 2016.  
2. Construire des features pertinentes (âge du bâtiment, usage dominant, surface, etc.).  
3. Entraîner et comparer plusieurs modèles de régression (linéaire et arbres).  
4. Évaluer les performances (RMSE, MAE, R²) et documenter les résultats.  

## Structure du projet

```
seattle-energy-prediction/  
├── pyproject.toml                    # Configuration Poetry et métadonnées  
├── README.md                         # Documentation du projet  
├── .gitignore                        # Fichiers à ignorer par Git  
├── data/                             # Données du projet  
│   ├── raw/                          # Données brutes (lecture seule)  
│   │   └── 2016_Building_Energy_Benchmarking.csv  
│   ├── processed/                    # Données nettoyées pour exploration  
│   └── final/                        # Jeux finaux pour modélisation  
├── notebooks/                        # Notebooks Jupyter  
│   ├── 01-exploration-donnees.ipynb  # Analyse exploratoire  
│   ├── 02-nettoyage-donnees.ipynb    # Préparation et nettoyage  
│   ├── 03-feature-engineering.ipynb  # Création de variables  
│   ├── 04-modelisation.ipynb         # Entraînement des modèles  
│   ├── 05-evaluation.ipynb           # Évaluation et validation  
│   └── figures/                      # Graphiques générés  
├── src/                              # Code source Python  
│   └── seattle_energy/               # Package principal  
│       ├── __init__.py  
│       ├── data/                     # Chargement & preprocessing  
│       │   ├── __init__.py  
│       │   ├── loader.py             # Chargement des CSV  
│       │   └── preprocessor.py       # Nettoyage et transformation  
│       ├── features/                 # Génération de features  
│       │   ├── __init__.py  
│       │   └── engineering.py        # Fonctions d’ingénierie  
│       ├── models/                   # Modèles ML  
│       │   ├── __init__.py  
│       │   ├── base.py               # Classe de base pour modèles  
│       │   ├── linear_models.py      # Régressions linéaires  
│       │   └── tree_models.py        # Arbres de décision et forêts  
│       └── utils/                    # Utilitaires  
│           ├── __init__.py  
│           ├── config.py             # Paramètres et chemins  
│           └── visualization.py      # Fonctions de tracés  
├── tests/                            # Tests unitaires  
│   ├── __init__.py  
│   └── test_data_loader.py           # Validation du loader  
└── results/                          # Résultats et artefacts  
    ├── models/                       # Modèles entraînés (pickle)  
    └── reports/                      # Rapports finaux (markdown, figures)  
```

## Installation et configuration

1. Cloner le dépôt  
   ```bash
   git clone https://github.com/votre-org/seattle-energy-prediction.git
   cd seattle-energy-prediction
   ```  
2. Installer les dépendances avec Poetry  
   ```bash
   poetry install
   ```  
3. Activer l’environnement  
   ```bash
   poetry shell
   ```  

## Organisation des données

- **data/raw/** : données d’entrée brutes, ne pas modifier.  
- **data/processed/** : jeux après nettoyage et typage, pour exploration.  
- **data/final/** : jeux prêts à l’entraînement (features encodées, normalisées).  

## Flux de travail et notebooks

1. **Exploration** :  
   - Exécuter `01-exploration-donnees.ipynb` pour analyser distributions et corrélations.  
2. **Nettoyage** :  
   - `02-nettoyage-donnees.ipynb` pour gérer valeurs manquantes et anomalies.  
3. **Feature Engineering** :  
   - `03-feature-engineering.ipynb` pour créer variables dérivées.  
4. **Modélisation** :  
   - `04-modelisation.ipynb` pour entraîner et comparer modèles.  
5. **Évaluation** :  
   - `05-evaluation.ipynb` pour calculer RMSE, MAE, R² et analyser les performances.  

## Usage du package seattle_energy

A venir

## Tests

A venir

## Résultats

A venir

## Licence

Ce projet est distribué sous licence MIT.
