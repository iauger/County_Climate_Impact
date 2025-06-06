 # Weathering Inequality: A Data-Driven Profile of U.S. County Risk

This project investigates how weather extremes and socioeconomic inequality intersect at the county level across the United States. Using over a decade of demographic and climate data, we identify and cluster U.S. counties into distinct macro risk profiles. The goal is to support more equitable regional planning and risk mitigation strategies by surfacing shared patterns of exposure, vulnerability, and resilience.

---

## Project Structure

### Notebooks

| Notebook | Purpose |
|---------|---------|
| `Phase_1_Proposal.ipynb` | Defines the original project scope, motivation, and data acquisition plan. |
| `Data_Acquisition.ipynb` | Extracts raw demographic and weather data from Google BigQuery and NOAA sources. |
| `Data_Preparation.ipynb` | Cleans and filters input data, applies feature engineering, and imputes missing values. |
| `Data_Clustering.ipynb` | Performs factor analysis and KMeans clustering on socioeconomic and weather datasets independently. |
| `Weather_Data_Clustering.ipynb` | Focuses exclusively on clustering weather exposure data and interpreting spatial climate risk. |
| `Data_Presentation.ipynb` | Merges datasets, derives second-order latent factors, assigns macro-clusters, and prepares data for visualization and Looker Studio dashboards. |

---

## Datasets

### Primary Sources
- **American Community Survey (ACS)**: Demographic, income, and housing data (2012–2022)
- **NOAA GSOD & Storm Events**: Weather summaries, storm events, and property damage data (2000–2023)
- **USDA RUCC Codes**: Rural-Urban Continuum Classification

### Processed Datasets
- `county_weather_acs_training.csv` – Cleaned, merged county-year dataset used for clustering
- `county_weather_acs_complete.csv` – Cleaned, merged county-year dataset but includes full weather data
- `weather_clusters.csv` – Final weather cluster assignments
- `socioeconomic_clusters.csv` – Final demographic cluster assignments
- `macro_clusters.csv` – Final compressed and merged dataset

---

## Final Report and Visualizations

### Looker Studio Dashboard
- Interactive geographic tool to explore county-level macro clusters
- Designed to support single-variable tooltips and clean regional navigation
- Built for exploratory analysis of U.S. counties by risk tier, allowing stakeholders to identify high-vulnerability regions as well as the latent factors driving the classifications.


---

## Reproducibility

### Requirements
- Python 3.12+
- Key libraries:
  - `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`
  - `factor_analyzer`, `geopandas`, `statsmodels`, `pandas_gbq`
- Google Cloud Project with BigQuery enabled
- Service account credentials stored locally

### How to Run
1. Set up your virtual environment and install dependencies
2. **Optional:** authenticate with Google Cloud and set `project_id` and `dataset_id` in notebooks
3. Run notebooks in the following order:  
   `Data_Acquisition` → `Data_Preparation` → `Data_Clustering` → `Weather_Data_Clustering` → `Data_Presentation`

4. **Optional:** export `compressed_visualization_df` to BigQuery for visualization

---

## License & Acknowledgments

- Project created by **Ian Auger** and **Nav Singh** as part of the Drexel MSDS curriculum (DSCI 521)
- Data provided by the U.S. Census Bureau, NOAA, and USDA
- This project is licensed under the [MIT License](LICENSE)

