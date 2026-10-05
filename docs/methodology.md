# Methodology

## 1. Data Integration

The framework integrates agricultural, climatic, post-harvest loss, and cold-storage infrastructure data from:

- AGMARKNET
- NASA POWER
- ICAR-CIPHET
- National Horticulture Board (NHB)

## 2. Data Preprocessing

The collected datasets are cleaned, standardized, and merged using common crop, district, and temporal information. Missing and inconsistent observations are handled before further analysis.

## 3. Change-Point Detection

CUSUM (Cumulative Sum) analysis is used to identify significant changes in crop arrival patterns and support adaptive forecasting model selection.

## 4. Adaptive Forecasting

Three forecasting approaches are used:

- SARIMAX
- Prophet
- Historical Maximum

The forecasting method is selected according to the amount of historical data available for each district-crop combination.

## 5. Shelf-Life Estimation

The Arrhenius equation is used to estimate temperature-dependent crop shelf life using climatic temperature data.

## 6. Feature Engineering

The forecasting and external datasets are combined to generate features including:

- Cooling gap
- Shelf life
- Average modal price
- Price volatility
- Peak solar irradiance

## 7. XGBoost Regression

XGBoost regression is used to predict **Daily At-Risk Crop Volume** for district-crop combinations.

The model uses the engineered agricultural, climatic, market, and perishability-related features as inputs.

## 8. SHAP Explainability

SHAP (SHapley Additive exPlanations) is applied to the trained XGBoost model to interpret feature contributions and identify the factors influencing the predictions.

## 9. TA-PUS Computation

The predicted Daily At-Risk Crop Volume is normalized and aggregated at the district level to calculate the **TA-PUS score**, which is used to prioritize districts according to cold-storage urgency.

## 10. Cold Storage Recommendation

District priorities are used to estimate required cold-storage capacity. The recommendation considers existing storage capacity and the additional storage requirement.

## 11. Solar PV Estimation

The recommended cold-storage capacity is used to estimate the corresponding solar PV panel requirement.

## 12. End-to-End Workflow

AGMARKNET + NASA POWER + ICAR-CIPHET + NHB

→ Data Preprocessing

→ Adaptive Forecasting

→ Arrhenius Shelf-Life Estimation

→ Feature Engineering

→ XGBoost Regression

→ Daily At-Risk Crop Volume

→ SHAP Analysis

→ TA-PUS Ranking

→ Cold Storage Recommendation

→ Solar PV Estimation
