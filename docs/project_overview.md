# Project Overview

## Project Title

Data-Driven Optimal Placement and Sizing of Solar Cold Storage for Perishable Crops in Karnataka Using Machine Learning

## Problem

Post-harvest losses of perishable crops can occur due to inadequate storage capacity, temperature-sensitive deterioration, and a mismatch between crop arrivals and available cold-storage infrastructure.

The project develops a data-driven framework to identify districts requiring additional cold-storage infrastructure and estimate the corresponding solar PV requirements.

## Objective

The objective is to develop a framework that:

- Forecasts crop arrivals
- Estimates crop shelf life
- Predicts Daily At-Risk Crop Volume
- Prioritizes districts using TA-PUS
- Recommends cold-storage capacity
- Estimates solar PV requirements

## Data Sources

The framework integrates:

- AGMARKNET
- NASA POWER
- ICAR-CIPHET
- National Horticulture Board (NHB)

## Methodology

The workflow consists of:

1. Data preprocessing
2. CUSUM-based change-point detection
3. Adaptive forecasting using SARIMAX, Prophet, and Historical Maximum
4. Arrhenius-based shelf-life estimation
5. Feature engineering
6. XGBoost regression
7. SHAP explainability
8. TA-PUS computation
9. Cold-storage capacity recommendation
10. Solar PV estimation

## Key Outputs

The framework produces:

- Crop arrival forecasts
- Daily At-Risk Crop Volume predictions
- SHAP-based feature interpretation
- District-wise TA-PUS rankings
- Cold-storage capacity recommendations
- Solar PV panel recommendations
- Karnataka district priority visualization

## Project Scope

The current implementation focuses on perishable crops and district-level cold-storage planning in Karnataka using historical agricultural, climatic, post-harvest loss, and infrastructure data.
