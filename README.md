### Two-Step Forecasting Model for Leptospirosis Incidence in Thailand
Overview
This repository contains the implementation of a two-step modeling approach for forecasting the incidence rate of leptospirosis at the district (amphoe) level in Thailand. The model aims to address the challenge of zero-inflated spatial data and incorporates geospatial and socioeconomic variables.

Research Objectives
Develop an effective two-step forecasting model for highly zero-inflated data.

Apply the model to predict leptospirosis incidence rates across districts in Thailand using spatial and demographic features.

Identify key environmental and socioeconomic factors influencing disease distribution.

Model Structure
The proposed Two-Step Model consists of:

Step 1 - Classification: Identify whether a district has any leptospirosis cases (0 vs. >0).

Step 2 - Regression: Predict the actual incidence rate (cases per 100,000 population) for districts classified as "at risk" in Step 1.

The model uses the Extreme Gradient Boosting algorithm (XGBoost) and applies nested cross-validation to tune hyperparameters.

Key Features Used
Climate data: average rainfall, temperature, humidity

Soil drainage types

Flood history: frequency and recurrence

NDVI, NDWI, and MNDWI indices (satellite-based vegetation and water indices)

Land use characteristics

Elevation and slope

Socioeconomic variables: household income, household expenditure, proportion of registered agricultural households

Data Sources
Thailand Meteorological Department (climate)

Land Development Department (soil and land use)

Geo-Informatics and Space Technology Development Agency (GISTDA) (NDVI, NDWI)

Ministry of Public Health, Thailand (leptospirosis cases)

Department of Provincial Administration (population data)

Satellite data (Landsat, Sentinel)

Tools and Technologies
R: model training and evaluation (packages: xgboost, caret, dplyr)

Python: spatial visualization and plotting (libraries: pandas, geopandas, matplotlib)

QGIS: raster processing, interpolation (IDW), and Zonal Statistics

Performance
Classification Step:

F1 Score: 0.869

Precision (Class 0): 0.668

Regression Step (RMSE): 0.3150

Combined Two-Step Model:

RMSE: 0.1532

MAE: 0.0553

Key Findings
Most influential predictors:

Classification: slope variance, humidity variance, ratio of agricultural households

Regression: mean temperature, soil drainage, NDWI variance

Flood-prone areas, moderate to poor soil drainage, and high humidity are strongly associated with higher incidence

Agricultural communities with low income are more vulnerable

Limitations
Absence of data on rodent populations or personal behaviors

Spatial resolution limited by monthly data aggregation

Under-reporting of district-level case data may exist

Future Recommendations
Integrate rodent surveillance and behavioral surveys

Use real-time weather and flood forecasts

Apply deep learning for spatiotemporal forecasting

Extend to subdistrict-level if data permits
