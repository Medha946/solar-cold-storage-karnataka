# Data Dictionary

This document describes the datasets used in the solar cold-storage planning framework and the main variables derived from them.

## 1. AGMARKNET

AGMARKNET provides agricultural market information used to represent crop arrivals and market price behaviour.

| Variable | Description | Use in Project |
|---|---|---|
| District | District associated with the market observation | District-level analysis |
| Crop | Name of the agricultural crop | Crop-level forecasting |
| Date | Date of market observation | Time-series forecasting |
| Arrival | Quantity of crop arriving at the market | Crop arrival forecasting |
| Modal Price | Modal market price | Market-price feature |
| Price | Market price information | Price analysis |

### Derived Variables

- Average modal price
- Price volatility
- Forecast crop arrivals

---

## 2. NASA POWER

NASA POWER provides meteorological and solar-resource information.

| Variable | Description | Use in Project |
|---|---|---|
| Date | Date of the observation | Temporal alignment |
| Temperature | Temperature information for the location | Shelf-life estimation |
| Solar Irradiance | Solar radiation/irradiance information | Solar PV estimation |

### Derived Variables

- Cooling gap
- Peak solar irradiance
- Temperature-related shelf-life estimates

---

## 3. ICAR-CIPHET

ICAR-CIPHET provides crop-specific post-harvest loss information.

| Variable | Description | Use in Project |
|---|---|---|
| Crop | Crop associated with the loss estimate | Crop mapping |
| Loss Percentage | Estimated post-harvest loss percentage | Daily At-Risk Crop Volume calculation |

The crop-specific loss percentage is used with forecast crop arrivals to estimate the volume of crop at risk.

---

## 4. National Horticulture Board (NHB)

NHB information is used to represent existing cold-storage infrastructure.

| Variable | Description | Use in Project |
|---|---|---|
| District | District associated with storage infrastructure | District-level analysis |
| Existing Storage Capacity | Existing cold-storage capacity | Storage gap estimation |
| Storage Units | Existing storage units where available | Capacity recommendation |

---

## 5. Engineered Variables

The integrated datasets are used to construct features for the machine-learning model.

| Feature | Description |
|---|---|
| Cooling Gap | Temperature-related feature representing the cooling requirement |
| Shelf Life | Estimated crop shelf life using the Arrhenius relationship |
| Average Modal Price | Average modal market price |
| Price Volatility | Variation in market price |
| Peak Solar Irradiance | Maximum/peak solar irradiance used for solar-resource assessment |

These engineered features are provided to the XGBoost regression model.

---

## 6. Target Variable

### Daily At-Risk Crop Volume

Daily At-Risk Crop Volume represents the estimated quantity of crop at risk of post-harvest loss based on forecast crop arrivals and crop-specific loss percentages.

It is used as the target variable for the XGBoost regression model.

---

## 7. Derived District-Level Output

### TA-PUS Score

TA-PUS is calculated after obtaining the predicted Daily At-Risk Crop Volume.

The predictions are normalized and aggregated at the district level to prioritize districts according to their cold-storage urgency.

TA-PUS is therefore a **derived prioritization score**, not a direct XGBoost prediction.
