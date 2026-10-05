# Results

## 1. Adaptive Forecasting Results

The adaptive forecasting framework selected forecasting models based on the available historical data for each district-crop combination.

The final model distribution was:

| Forecasting Model | Number of Cases |
|---|---:|
| SARIMAX | 72 |
| Historical Maximum | 22 |
| Prophet | 10 |

SARIMAX was the most frequently selected forecasting approach, while Historical Maximum and Prophet were used for cases with different data availability characteristics.

## 2. XGBoost Prediction

XGBoost was used to predict **Daily At-Risk Crop Volume** for district-crop combinations.

The prediction incorporates engineered features representing agricultural arrivals, market conditions, perishability, and climatic conditions.

## 3. SHAP Analysis

SHAP analysis was performed to interpret the trained XGBoost model.

Two outputs were generated:

- SHAP feature importance
- SHAP summary plot

These outputs provide an interpretable view of the contribution of the input features to the model predictions.

## 4. District Prioritization

The predicted Daily At-Risk Crop Volume was normalized and aggregated to calculate the **TA-PUS score** at the district level.

Districts were then ranked according to their estimated cold-storage urgency.

## 5. Cold Storage Recommendation

The framework generated district-wise recommendations for additional cold-storage capacity.

The recommendation considers:

- Predicted daily at-risk crop volume
- Required storage units
- Existing storage capacity
- Additional storage requirement

## 6. Solar PV Recommendation

Solar PV requirements were estimated from the recommended cold-storage capacity.

The resulting output provides the estimated number of solar panels required to support the recommended cold-storage infrastructure.

## 7. Spatial Visualization

A Karnataka district priority map was generated using the TA-PUS scores to visualize the spatial distribution of cold-storage urgency.

## 8. Overall Outcome

The framework produces an explainable, data-driven approach for:

1. Forecasting crop arrivals
2. Estimating perishability and at-risk volume
3. Prioritizing districts
4. Recommending cold-storage capacity
5. Estimating associated solar PV requirements
