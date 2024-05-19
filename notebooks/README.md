
# Notebooks Overview

This directory contains Jupyter notebooks used for the data preprocessing, analysis, model training, and evaluation involved in producing the Machine Learning Models. Find below a brief description of each notebook:

## 1. Data Filtering for 2017 Trips (`1_data_filtering_2017.ipynb`)
### Description:
This notebook focuses on filtering and preprocessing the trip data for the year 2017. The main tasks include:
- Merging the raw data ~50 files from [Transport for London Website]((https://cycling.data.tfl.gov.uk/))
- Cleaning the data by removing entries with missing values.
- Filtering trips to retain only those within the specified date range (2017).
- Saving the filtered data for further analysis.

## 2. Merging Trip and Weather Data (`2_merge_trip_weather_data.ipynb`)
### Description:
This notebook merges the filtered trip data with weather data to provide a comprehensive dataset for analysis. The tasks include:
- Importing weather data for the city of London for the year of 2017 ("london_2017_weather_data_hourly&daily.csv"), downloaded from [Open-Meteo]( https://open-meteo.com/)
- Merging the datasets based on date and time.

## 3. Final Dataframe Preparation (`3_final_dataframe_preparation.ipynb`)
### Description:
This notebook prepares the final dataframe for modeling by performing feature engineering and final cleaning steps. Tasks include:
- Handling discrepancies and ensuring data consistency.
- Creating new features based on existing data (e.g., extracting date-time features).
- Saving the final prepared dataframe.

### Key Sections:
- **Feature Engineering**: Create new features such as day of the week, hour of the day, etc.
- **Data Normalization**: Normalize and scale features for modeling.


## 4. Geospatial Analysis (`4_geospatial_analysis.ipynb`)
### Description:
This notebook performs a geospatial analysis of bike-sharing stations in London. Tasks include:
- Visualizing the spatial distribution of stations and trips.
- Analyzing the relationship between station locations and trip frequency.
- Generating geospatial plots and maps.

### Produced Plots:

#### Station Locations Map
- **Filename**: `interactive_stations_opacity_coded.html`
- **Description**: An interactive map of London displaying the locations of all bike-sharing stations. Each station is marked with a circle, where the opacity of the circle indicates the station's capacity. Clicking on a marker displays the station's name and capacity. Uses the Folium library to create an interactive map where each station is marked by a circle. The opacity of the circle is proportional to the station's capacity.

#### Voronoi Diagram of Station Service Areas
- **Filename**: Not explicitly saved in the provided code.
- **Description**: A plot of Voronoi regions representing the service areas of each bike-sharing station in London. This visualization helps to understand the spatial coverage of each station based on its geographical coordinates. Uses Voronoi polygons generated from station coordinates to represent the service areas. Each polygon corresponds to the region closest to a specific station.

#### Station Statistics Map
- **Filename**: `interactive_stations_2017_map.html`
- **Description**: An interactive map of London showing bike-sharing stations with markers indicating various statistics. Each marker displays station-specific data such as the number of daily journeys, total yearly journeys, capacity, and median journey duration when clicked. Uses the Folium library to create an interactive map with markers that display various station statistics. The opacity of each marker reflects the station's capacity.

#### Min-Max Table for Station Statistics
- **Filename**: Not explicitly saved as a plot but printed in the notebook.
- **Description**: A printed table in the notebook showing the minimum and maximum values for various station statistics (e.g., journey count, daily journey count, total duration hours, median journey duration, journey count per capacity) along with the corresponding station names. This table provides insights into the stations with the highest and lowest values for these metrics.

## 5. Model Creation (`5_model_creation.ipynb`)
### Description:
This notebook focuses on creating and evaluating machine learning models, specifically XGBoost and Asymmetrical XGBoost, for predicting bike-sharing demand. Tasks include:
- Defining and training various machine learning models.
- Performing hyperparameter tuning.
- Cross-Validation
- Evaluating model performance using metrics and visualization techniques.

### Key Sections:
- **Data Preparation**: Load and preprocess the data for modeling.
- **Model Training**: Train machine learning models (e.g., XGBoost, Asymmetrical XGBoost).
- **Hyperparameter Tuning**: Optimize model parameters using cross-validation.
- **Model Evaluation**: Evaluate and compare model performance using metrics and visualizations.
-  **Pickling Models**: The trained XGBoost and Asymmetrical XGBoost models are saved to disk using the `pickle` module.

### Produced Plots
1. **Algorithm Accuracy by RMSLE Bar Plot**
   - **Filename**: `alg_accuracy_rmsle_barplot.png`
   - **Description**: A bar plot comparing the Root Mean Squared Logarithmic Error (RMSLE) of different machine learning algorithms. This plot helps identify which algorithm performs best in terms of prediction accuracy.

2. **Algorithm Execution Time Bar Plot**
   - **Filename**: `alg_execution_time_barplot.png`
   - **Description**: A bar plot comparing the execution time of different machine learning algorithms. This plot provides insights into the computational efficiency of each algorithm.

3. **XGBoost Hyperparameter Tuning Heatmap**
   - **Filename**: Not explicitly saved in the provided code.
   - **Description**: A heatmap showing the results of hyperparameter tuning for the XGBoost model. The heatmap displays the performance of different combinations of hyperparameters, helping to identify the optimal settings.

4. **Residual Plots for XGBoost Predictions**
   - **Filename**: `XGBoost_residuals_plots.png`
   - **Description**: A set of three plots (scatter plot, histogram, and Q-Q plot) showing the residuals of the XGBoost model predictions. These plots help evaluate the distribution and patterns of prediction errors.

5. **Residual Plots for Asymmetrical XGBoost Predictions**
   - **Filename**: `Asym_XGBoost_residuals_plots.png`	
   - **Description**: A set of three plots (scatter plot, histogram, and Q-Q plot) showing the residuals of the Asymmetrical XGBoost model predictions. These plots help evaluate the distribution and patterns of prediction errors.

6. **Model Evaluation Scores on Training and Test Sets**
   - **Filename**: Not explicitly saved in the provided code.
   - **Description**: Printed evaluation scores (e.g., RMSLE, R-squared) for the XGBoost and Asymmetrical XGBoost models on both training and test datasets. These scores provide a quantitative measure of model performance.

