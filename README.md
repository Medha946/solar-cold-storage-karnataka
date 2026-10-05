Absolutely. Here's the **full README**, kept clean and professional, with enough detail for a GitHub research/project repository but without turning it into a report.

```markdown
# Data-Driven Optimal Placement and Sizing of Solar Cold Storage for Perishable Crops in Karnataka Using Machine Learning

A data-driven framework for forecasting crop arrivals, estimating perishability, prioritizing districts, and recommending solar-powered cold-storage infrastructure in Karnataka.

## Overview

Perishable agricultural produce is highly vulnerable to post-harvest losses due to inadequate and unevenly distributed cold-storage infrastructure.

This project develops a data-driven framework that integrates agricultural, climatic, post-harvest loss, and existing cold-storage infrastructure data to support cold-storage planning across Karnataka.

The framework combines adaptive forecasting, Arrhenius-based shelf-life estimation, XGBoost regression, SHAP explainability, TA-PUS prioritization, cold-storage capacity recommendation, and solar PV estimation.

## Objectives

- Forecast future crop arrivals
- Estimate temperature-dependent crop shelf life
- Predict Daily At-Risk Crop Volume
- Prioritize districts using TA-PUS
- Recommend additional cold-storage capacity
- Estimate solar PV panel requirements

## Data Sources

| Source | Data Used |
|---|---|
| **AGMARKNET** | Crop arrivals and market prices |
| **NASA POWER** | Temperature and solar irradiance |
| **ICAR-CIPHET** | Crop-specific post-harvest loss percentages |
| **NHB** | Existing cold-storage infrastructure |

## Methodology

```text
AGMARKNET + NASA POWER + ICAR-CIPHET + NHB
                    ↓
             Data Preprocessing
                    ↓
                  CUSUM
                    ↓
          Adaptive Forecasting
     ┌──────────┬───────────┐
     ↓          ↓           ↓
  SARIMAX    Prophet    Historical Max
     └──────────┴───────────┘
                    ↓
       Arrhenius Shelf-Life Estimation
                    ↓
            Feature Engineering
                    ↓
             XGBoost Regression
                    ↓
        Daily At-Risk Crop Volume
                    ↓
             SHAP Analysis
                    ↓
            TA-PUS Computation
                    ↓
         District Prioritization
                    ↓
       Cold Storage Recommendation
                    ↓
           Solar PV Estimation
```

## Adaptive Forecasting

The forecasting framework selects a model based on the amount of historical data available for each district-crop combination.

| Forecasting Model | Cases |
|---|---:|
| SARIMAX | 72 |
| Historical Maximum | 22 |
| Prophet | 10 |

## Machine Learning

XGBoost regression is used to predict **Daily At-Risk Crop Volume** using engineered agricultural, climatic, market, and perishability-related features.

SHAP is then used to interpret the contribution of the input features to the model predictions.

The predicted Daily At-Risk Crop Volume is normalized and aggregated at the district level to calculate the **Temperature-Adjusted Perishability Urgency Score (TA-PUS)**.

## Key Outputs

- Crop arrival forecasts
- Daily At-Risk Crop Volume predictions
- SHAP feature importance
- District-wise TA-PUS ranking
- Cold-storage capacity recommendations
- Solar PV panel requirements
- Karnataka district priority visualization

## Repository Structure

```text
solar-cold-storage-karnataka/
│
├── architecture/
│   ├── system_architecture.png
│   └── architecture.md
│
├── data/
│   ├── README.md
│   └── data_dictionary.md
│
├── docs/
│   ├── methodology.md
│   ├── results.md
│   └── project_overview.md
│
├── notebooks/
│   ├── README.md
│   └── solar_cold_storage.ipynb
│
├── outputs/
│   ├── forecasting/
│   ├── shap/
│   ├── ta_pus/
│   └── recommendations/
│
├── src/
│   └── README.md
│
├── README.md
└── requirements.txt
```

## Documentation

- [Project Overview](docs/project_overview.md)
- [Methodology](docs/methodology.md)
- [Results](docs/results.md)
- [Data Dictionary](data/data_dictionary.md)
- [System Architecture](architecture/architecture.md)

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Prophet
- XGBoost
- SHAP
- Scikit-learn
- Google Colab

## Results

The framework produced an adaptive forecasting distribution of:

- **72 SARIMAX cases**
- **22 Historical Maximum cases**
- **10 Prophet cases**

The complete results include SHAP-based feature interpretation, district-level TA-PUS ranking, cold-storage recommendations, solar PV requirements, and spatial visualization.


## Conclusion

This project presents a data-driven framework for planning solar-powered cold-storage infrastructure for perishable crops in Karnataka. By combining adaptive crop-arrival forecasting, shelf-life estimation, XGBoost-based prediction, SHAP explainability, TA-PUS prioritization, and capacity-aware recommendations, the framework supports more informed identification and sizing of cold-storage facilities.

The resulting outputs provide district-level priorities, storage capacity recommendations, and associated solar PV requirements for sustainable cold-storage planning.

---

**Project by Medha Vidyananda & Lakshitha R**  
**Guide:** Dr. P. Kavitha  
**CoDMAV, PES University**
```
