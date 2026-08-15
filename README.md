# Melbourne Pedestrian Mobility Analytics 2026

An end-to-end project analysing over **500,000 hourly pedestrian observations** from Melbourne's pedestrian sensor network and developing machine-learning models to forecast pedestrian demand.

## Project Overview

Pedestrian activity varies substantially across Melbourne depending on location, time and day.

This project investigates three questions:

1. When and where is pedestrian demand highest?
2. Which factors are most strongly associated with pedestrian demand?
3. How accurately can future pedestrian activity be predicted using machine learning?

The project covers the complete data science workflow from data validation and exploratory analysis through statistical testing, feature engineering, machine learning, model interpretation and responsible AI considerations.

## Dataset

**Source:** City of Melbourne Open Data – Pedestrian Counting System

**Period:** January–August 2026  
**Observations:** 505,887 hourly sensor records  
**Locations represented:** 101  
**Target:** Hourly pedestrian demand

A supplementary sensor-location dataset was joined to the count data to provide descriptive location information.

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- SciPy
- scikit-learn
- Quarto
- Git / GitHub

## Analysis

The project includes:

- Data quality validation and cleaning
- Exploratory data analysis
- Temporal feature engineering
- Statistical comparison of weekday and weekend demand
- Chronological train/test splitting
- Baseline forecasting
- Linear regression
- Random forest regression
- Gradient boosting
- Model comparison
- Permutation feature importance
- Prediction error analysis
- Cyclical feature engineering
- Data governance and model-risk analysis

## Model Performance

Models were trained using January–July observations and evaluated on unseen August 2026 data.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Historical Average Baseline | 392.79 | 567.26 | -0.001 |
| Linear Regression | 288.53 | 437.84 | 0.404 |
| Random Forest | 173.35 | 285.93 | 0.746 |
| **Gradient Boosting** | **98.99** | **183.74** | **0.895** |

Gradient boosting reduced mean absolute error by approximately **75% relative to the baseline**.

## Key Findings

- **Location and hour of day are the strongest predictors** of pedestrian demand.
- Pedestrian activity displays strong recurring intraday patterns.
- Demand varies substantially across sensor locations.
- Gradient boosting explained approximately **89.5% of variation in unseen August observations**.
- The largest prediction errors were concentrated around unusual demand spikes, particularly around RMIT and Swanston Street on 9 August.
- External information such as events, weather, public holidays and transport disruptions could potentially improve forecasting of abnormal demand.

## Responsible Model Use

The sensor network does not represent every Melbourne location equally, and sensor readings may be affected by infrastructure or measurement issues.

The model also learns primarily from historical location and temporal patterns and cannot directly anticipate external shocks.

Predictions should therefore be treated as decision-support information rather than autonomous decisions, with performance monitored as pedestrian behaviour and sensor infrastructure change.

## Repository Structure

```text
melbourne-mobility-analytics/
├── data/                  # Source datasets
├── figures/               # Project visualisations
├── mobility_analysis.qmd  # Complete analysis and Python code
├── mobility_analysis.html # Rendered Quarto report
├── requirements.txt       # Python dependencies
├── .gitignore
└── README.md
```

## Reproducibility

Install the required Python packages with:

```bash
pip install -r requirements.txt
```

Then render the Quarto analysis with:

```bash
quarto render mobility_analysis.qmd
```

## Future Improvements

Potential extensions include incorporating:

- Weather conditions
- Public holidays
- Major event schedules
- Public transport disruptions
- Longer historical periods
- Time-series cross-validation
- Hyperparameter optimisation
- Interactive forecasting dashboard
