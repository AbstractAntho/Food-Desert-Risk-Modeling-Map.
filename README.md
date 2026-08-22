# Food Desert Risk Modeling and Interactive Map

An end-to-end data science project that analyzes USDA census-tract data to identify and visualize communities at risk of limited food access.

## Project Overview

This project uses demographic, socioeconomic, and food-access data from the USDA Food Access Research Atlas. A Random Forest model identifies influential predictors, while logistic regression estimates each census tract's probability of experiencing food-access risk.

Tract-level probabilities, average risk, and the percentage of at-risk tracts are aggregated into county-level scores. The results are presented through an interactive map, with locally generated policy recommendations powered by Ollama.

## Key Features

- Cleaned and analyzed USDA census-tract data containing approximately 140 features
- Used Random Forest feature importance for feature selection
- Trained a logistic regression model to estimate tract-level food-access risk
-ggractive geographic map for exploring county and tract risk
- Integrated Ollama to generate location-specific policy recommendations

## Technologies

Python, pandas, NumPy, scikit-learn, GeoPandas, Plotly, Folium/Leaflet, and Ollama

## Methodology

1. Load and clean USDA food-access and demographic data
2. Select relevant predictors using Random Forest feature importance
3. Train and evaluate a logistic regression classifier
4. calculate risk probabilities for individual census tracts
5. Aggregate tract-level results into county-level scores
6. Visualize geographic patterns through an interactive map
7. Generate policy recommendations using a locally hosted Ollama model

## Running the Project

The complete analysis is available in:

[`Food_Deserts_Logistic_Regression_Map_analysis.ipynb`](Food_Deserts_Logistic_Regression_Map_analysis.ipynb)

The notebook was developed in Google Colab. Ollama-generated recommendations require a locally running Ollama server and are not available directly through GitHub's notebook preview.

## Data Source

Data was obtained from the USDA Food Access Research Atlas.
