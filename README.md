# Global Ocean Satellite Analysis (2011-2015)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![BigQuery](https://img.shields.io/badge/Google_Cloud-BigQuery-orange)
![License](https://img.shields.io/badge/License-MIT-grey)

Ce projet porte sur l'analyse de données satellitaires océanographiques (SST et SSH) sur une période de 5 ans. L'objectif principal est de mettre en œuvre une architecture de traitement Big Data (~50 Go de données) utilisant Google Cloud Platform pour extraire des indicateurs climatiques et analyser des phénomènes météorologiques extrêmes.

## Aperçu du projet

Le traitement des données se fait via une approche hybride pour pallier les limitations de mémoire locale :
1.  **Agrégation Cloud (Server-side) :** Utilisation de SQL via Google BigQuery pour effectuer les calculs statistiques lourds directement sur l'infrastructure Google.
2.  **Analyse Locale (Client-side) :** Récupération des données agrégées via Python pour la visualisation fine et la modélisation prédictive.

### Stack Technique
* **Langage :** Python (Pandas, NumPy, Scikit-learn)
* **Cloud & Data :** Google BigQuery (SQL), Google Cloud Storage
* **Visualisation :** Matplotlib, Basemap (Projections géospatiales)

## Analyses Principales

Le notebook présente plusieurs études de cas ciblées sur des dynamiques océanographiques spécifiques :

### 1. Dynamique du Courant des Aiguilles
Étude de la corrélation spatiale entre la température de surface (SST) et la hauteur de mer (SSH) dans la région du courant des Aiguilles (Afrique du Sud), une zone caractérisée par une forte variabilité méso-échelle.

### 2. Monitoring ENSO (El Niño / La Niña)
Calcul de l'indice ENSO dans le Pacifique équatorial. L'analyse des anomalies de température moyenne journalière permet d'identifier les phases chaudes (El Niño) et froides (La Niña) sur la période 2011-2015.

### 3. Impact Thermique des Typhons
Détection des "sillages froids" (Cold Wakes) au sud du Japon. L'algorithme calcule le gradient journalier de SST pour isoler les chutes brutales de température (> 0.4°C/jour) correspondant au passage des cyclones tropicaux, validant le transfert d'énergie océan-atmosphère.

### 4. Modélisation et Tendances
* **Décomposition saisonnière :** Modélisation de la SST en Méditerranée par régression linéaire incluant une tendance climatique et un cycle saisonnier harmonique.
* **Projection du niveau de la mer :** Extrapolation linéaire de la tendance globale du niveau moyen des mers (GMSL) jusqu'à l'horizon 2100 (exercice théorique basé sur les données 2011-2015).

## Installation et Utilisation

Pour reproduire l'analyse, un compte Google Cloud Platform avec accès à BigQuery est nécessaire.

1.  **Cloner le dépôt :**
    ```bash
    git clone [https://github.com/votre-username/ocean-satellite-analysis-gcp.git](https://github.com/votre-username/ocean-satellite-analysis-gcp.git)
    cd ocean-satellite-analysis-gcp
    ```

2.  **Installer les dépendances :**
    ```bash
    pip install pandas matplotlib scikit-learn google-cloud-bigquery
    # Note : L'installation de Basemap peut nécessiter des étapes spécifiques selon l'OS.
    ```

3.  **Lancer le Notebook :**
    Le fichier principal est `miniprojet_MCE_SMA_2025.ipynb`.
    *Note : Les requêtes SQL nécessitent un fichier de clé d'authentification ou un environnement authentifié (ex: Colab).*

## Auteurs

Projet réalisé dans le cadre du Master Données & Océanographie (2025).

* Paul Trassaert
* Nathan Ygé
* Aziz Jallouli
* Mohammed Ali AL Marjani
* Adam Denieul
