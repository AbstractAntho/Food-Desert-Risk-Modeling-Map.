# Food Desert Risk Modeling and Interactive Policy Map

An end-to-end data science project that uses USDA census-tract data, machine
learning, and geospatial visualization to identify communities experiencing
limited food access.

The project combines Random Forest feature selection, logistic regression,
county-level risk scoring, an interactive Folium map, and locally generated
Ollama policy recommendations.


## Project Overview

Food deserts are communities where residents face limited access to affordable
and nutritious food. This project analyzes demographic, socioeconomic, and
food-access indicators from the USDA Food Access Research Atlas to estimate
food-desert risk across the United States.

A logistic regression model estimates the probability of food-access risk for
individual census tracts. These probabilities and the percentage of tracts
identified as food deserts are then aggregated into county-level risk scores.

The results are presented through an interactive geographic map. Users can
select a county to examine its food-access statistics and request a locally
generated policy recommendation through Ollama.

## Interactive Map

The completed map is available in:

[`food_desert_interactive.html`](food_desert_interactive.html)

Download the HTML file and open it in a browser to explore the map.

The map remains usable without Ollama, but AI-generated recommendations require
a locally running Ollama server.

## Methodology

### 1. Data Collection and Cleaning

Data was gathered from the USDA Food Access Research Atlas. The original
dataset contained approximately 140 census-tract features describing:

- Population and urbanization
- Poverty and household income
- Vehicle availability
- SNAP participation
- Age demographics
- Racial and ethnic demographics
- Low-income and low-access classifications

The data was cleaned, standardized, and prepared for machine-learning analysis.

### 2. Feature Selection

A Random Forest model was used to evaluate feature importance and identify
influential predictors of food-access risk.

### 3. Risk Modeling

A logistic regression classifier was trained to estimate the probability that
each census tract experiences food-access risk.

Logistic regression was selected because its probability outputs are
interpretable and can be incorporated into a continuous risk-scoring system.

### 4. County-Level Scoring

Tract-level predictions were aggregated into county-level scores using:

- Average predicted tract risk
- Percentage of tracts identified as food deserts
- Food-access prevalence indicators

This produces a continuous score that communicates severity more effectively
than a simple binary classification.

### 5. Interactive Visualization

GeoPandas and Folium were used to join model results with Census geographic
boundaries and build an interactive county-level map.

The map displays:

- County and state
- Average food-desert risk score
- Percentage of tracts identified as food deserts
- Demographic and food-access statistics
- Locally generated policy recommendations

### 6. Ollama Policy Recommendations

The project includes a collaboratively developed Ollama integration. When a
county is selected, its risk profile is sent to a locally hosted language model,
which generates a short, county-specific policy recommendation.

Recommendations may include interventions such as:

- Mobile food markets
- SNAP outreach
- Public-transit improvements
- Grocery-store development incentives
- Local zoning changes

Ollama processes the information locally rather than sending it to a hosted
language-model API.

## Project Leadership and Contributions

I spearheaded this project from initial concept through modeling and
visualization. My contributions included:

- Proposed the food-desert topic and established the project direction
- Gathered and cleaned the USDA census-tract data
- Developed the complete Google Colab analysis pipeline
- Implemented Random Forest feature selection
- Trained and evaluated the logistic regression model
- Designed the tract-level and county-level risk-scoring methodology
- Built the interactive geospatial map
- Proposed and co-developed the Ollama recommendation feature
- Coordinated the integration of the data, models, map, and AI functionality

The final Ollama implementation was completed collaboratively by teammate Erin,
who extended the analysis and map foundation developed in my Colab notebook.

## Technologies

- Python
- pandas
- NumPy
- scikit-learn
- GeoPandas
- Folium and Leaflet
- Plotly
- Matplotlib
- Seaborn
- Ollama
- Google Colab

## Running the Analysis

The primary analysis is contained in:

[`food_desert_analysis.ipynb`](food_desert_analysis.ipynb)

The notebook was originally developed in Google Colab.

1. Download or clone this repository.
2. Open the notebook in Google Colab or Jupyter.
3. Install the required packages:

   ```bash
   pip install -r requirements.txt
