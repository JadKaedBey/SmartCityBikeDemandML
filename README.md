# Optimizing BikeSharing Systems in Smart Cities: A Machine Learning Forecasting Model

This repository has been created  and contains the full source code and data to produce my Bachelor's thesis on predicting bike-sharing demand in London using machine learning models.

![](/reports/figures/interactive_stations_opacity_coded.png)

## Repository Structure

The repository is organized into the following directories and files:
```
BikeSharingPrediction/
├── data/
│   ├── raw/                      # Raw data files (initial datasets)
│   ├── processed/                # Processed data files (cleaned and merged datasets)
│   └── external/                 # External data sources (e.g., weather data)
├── notebooks/                    # Jupyter notebooks
│   ├── 1_trip_filtering_2017.ipynb
│   ├── 2_trip_weather_merge.ipynb
│   ├── 3_finaldf_revisioned.ipynb
│   ├── 4_london_geospatial_analysis.ipynb
│   ├── 5_model_creation.ipynb
├── models/                       # Trained models
│   ├── xgboost_model.pkl
│   └── asym_xgboost_model.pkl
├── reports/                      # Reports and figures
│   ├── figures/
│   │   └── ...
│   
├── thesis
├── README.md
├── requirements.txt
└── LICENSE
```
## Project Dependencies

#### Using pip

To install all dependencies using `pip`, run the following command:

```sh
pip install folium geopandas geovoronoi matplotlib numpy osmnx pandas scipy seaborn shapely scikit-learn smopy statsmodels xgboost
```
#### Using conda

```
conda install -c conda-forge folium geopandas geovoronoi matplotlib numpy osmnx pan`
```

## Installation

Clone the repository and install the required dependencies:
```bash
git clone https://github.com/yourusername/BikeSharingPrediction.git
cd BikeSharingPrediction
pip install -r requirements.txt
```


## Usage

You can run the notebooks in order to follow the data processing and modeling steps:

1.  Open `1_trip_filtering_2017.ipynb` to filter the trip data.
2.  Proceed with `2_trip_weather_merge.ipynb` to merge trip data with weather data.
3.  Use `3_finaldf_revisioned.ipynb` to finalize the dataframe.
4.  Analyze the geospatial data with `4_london_geospatial_analysis.ipynb`.
5.  Train and evaluate models using `5_model_creation.ipynb`.


### Loading Pre-Trained Models

To save time, you can load the pre-trained models instead of retraining them from scratch:

```
import pickle

# Load the trained XGBoost model
with open('models/xgboost_model.pkl', 'rb') as f:
    xgb_tuned = pickle.load(f)

# Load the trained Asymmetrical XGBoost model
with open('models/asym_xgboost_model.pkl', 'rb') as f:
    asym_xgb_tuned = pickle.load(f)
```

## Bibtex:

The BibTeX for this document is:
```
@bachelorthesis{jad2024bikesharing,
  author       = {Jad Kaedbey},
  title        = {Optimizing BikeSharing Systems in Smart Cities: A Machine Learning Forecasting Model},
  school       = {Università Degli Studi di Padova},
  year         = 2024,
  month        = May,
}
```
