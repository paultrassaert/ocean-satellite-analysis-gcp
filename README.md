# Global Ocean Satellite Analysis (2011-2015)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![BigQuery](https://img.shields.io/badge/Google_Cloud-BigQuery-orange)
![License](https://img.shields.io/badge/License-MIT-grey)

This project focuses on the analysis of global oceanographic satellite data (SST and SSH) over a 5-year period. The primary objective is to implement a Big Data processing pipeline (~50GB of data) using Google Cloud Platform to extract climate indicators and analyze extreme weather events.

## Project Overview

To address local memory limitations, data processing follows a hybrid approach:
1.  **Cloud-Side Aggregation:** Leveraging Google BigQuery (SQL) to perform heavy statistical computations directly on the cloud infrastructure.
2.  **Client-Side Analysis:** Fetching aggregated results via Python for detailed visualization and predictive modeling.

### Tech Stack
* **Language:** Python (Pandas, NumPy, Scikit-learn)
* **Cloud & Data:** Google BigQuery (SQL), Google Cloud Storage
* **Visualization:** Matplotlib, Basemap (Geospatial projections)

## Key Analyses & Case Studies

The notebook presents several targeted studies on specific oceanographic dynamics:

### 1. Agulhas Current Dynamics
Investigation of the spatial correlation between Sea Surface Temperature (SST) and Sea Surface Height (SSH) in the Agulhas Current region (South Africa), an area characterized by intense mesoscale variability.

### 2. ENSO Monitoring (El Niño / La Niña)
Calculation of the ENSO index in the Equatorial Pacific. Analysis of daily mean temperature anomalies allows for the identification of warm phases (El Niño) and cold phases (La Niña) over the 2011-2015 period.

### 3. Thermal Impact of Typhoons
Detection of "Cold Wakes" south of Japan. The algorithm computes the daily SST gradient to isolate rapid temperature drops (> 0.4°C/day) corresponding to the passage of tropical cyclones, validating ocean-atmosphere energy transfer.

### 4. Modeling and Trends
* **Seasonal Decomposition:** Modeling Mediterranean SST using linear regression including a climate trend and a harmonic seasonal cycle.
* **Sea Level Rise Projection:** Linear extrapolation of the Global Mean Sea Level (GMSL) trend up to the year 2100 (theoretical exercise based on 2011-2015 data).

## Installation and Usage

To reproduce the analysis, a Google Cloud Platform account with access to BigQuery is required.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/ocean-satellite-analysis-gcp.git](https://github.com/your-username/ocean-satellite-analysis-gcp.git)
    cd ocean-satellite-analysis-gcp
    ```

2.  **Install dependencies:**
    ```bash
    pip install pandas matplotlib scikit-learn google-cloud-bigquery
    # Note: Installing Basemap might require specific steps depending on the OS.
    ```

3.  **Run the Notebook:**
    The main file is `miniprojet_MCE_SMA_2025.ipynb`.
    *Note: SQL queries require an authentication key file or an authenticated environment (e.g., Colab).*

## Contributors

Project realized as part of the Master's curriculum in Data Science & Oceanography (2025).

* Paul Trassaert
* Nathan Ygé
* Aziz Jallouli
* Mohammed Ali AL Marjani
* Adam Denieul
