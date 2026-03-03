# Predictive Modelling of Household Energy Consumption (Multi-Scale LSTM + Feature Engineering)

## Overview
This dissertation project forecasts **daily household energy consumption** using deep learning (LSTM) and extensive feature engineering. The key idea is to improve predictive accuracy by combining:
- historical consumption patterns,
- **weather signals**, and
- **holiday / calendar effects**.

The dataset is based on the **London Smart Meters** household energy data (5,567 households), enriched with daily weather and UK bank holiday information. :contentReference[oaicite:2]{index=2}

---

## Objectives
- Forecast **daily energy consumption** using sequence models (LSTM).
- Engineer informative temporal + exogenous features (weather, holidays).
- Apply feature selection and dimensionality reduction to improve generalization.
- Evaluate forecasting performance using RMSE and validation curves. :contentReference[oaicite:3]{index=3}

---

## Dataset
### Main sources
- **Household information:** `informations_households.csv`
- **Weather (daily):** `weather_daily_darksky.csv`
- **UK bank holidays:** `uk_bank_holidays.csv`
- **Energy consumption (London Smart Meters):** provided in the dataset folder below

### Full dataset link (Google Drive)
https://drive.google.com/drive/folders/1-ovsEUyJc1sabMUmzwCFb6uaqgwdakBE?usp=sharing

> Note: Place the downloaded dataset files in the same folder as the notebook (or update file paths inside the notebook).

---

## Feature Engineering & Preprocessing
Key steps implemented in the project:
- Filtered dates from **2012-01-01 onwards**
- Aggregated energy usage **by day**
- One-hot encoded categorical variables (expanded to **~119 features**)
- Imputed missing values using **mean imputation**
- Added temporal features such as **day of week** and **month**
- Created lag-based features (example: **previous week’s average energy**) :contentReference[oaicite:4]{index=4}

---

## Feature Selection & Dimensionality Reduction
Multiple approaches were explored to identify the most predictive signals:

- **Correlation analysis** (to understand relationships and redundancy) :contentReference[oaicite:5]{index=5}
- **PCA** (dimensionality reduction while retaining ~95% variance) :contentReference[oaicite:6]{index=6}
- **Lasso regression** (penalized selection of important variables) :contentReference[oaicite:7]{index=7}
- **Random Forest feature importance**, where top drivers included:
  - `previous_week_energy`
  - `pressure`
  - `apparentTemperature`
  - `windBearing`
  - `temperature` :contentReference[oaicite:8]{index=8}

The reflective analysis also discusses addressing multicollinearity (e.g., with VIF) and selecting robust lag features across multiple horizons (days/weeks/months). :contentReference[oaicite:9]{index=9}

---

## Model: LSTM (Multi-Scale / Multi-Horizon)
### Model setup (as documented)
- Sequence length: **30 days**
- Loss: **Mean Squared Error (MSE)**
- Early stopping: **patience = 20** (to reduce overfitting)
- Hyperparameter tuning via Keras Tuner (random search) :contentReference[oaicite:10]{index=10}

> The overall dissertation theme includes multi-scale forecasting and attention mechanisms for short/medium/long term prediction (discussed in the reflective essay). :contentReference[oaicite:11]{index=11}

---

##  Results (Informed from your saved notebook outputs + slides)

### From your notebook’s recorded evaluation (Train vs Test RMSE)
Your notebook prints the following **RMSE across daily / weekly / monthly horizons**:

**Train RMSE**
- Daily: **0.1222**
- Weekly: **0.1079**
- Monthly: **0.1048**

**Test RMSE**
- Daily: **0.0911**
- Weekly: **0.0848**
- Monthly: **0.0842**

> These RMSE values are based on the evaluation cell outputs saved in the notebook run.  
> (Depending on scaling/normalization used in the pipeline, RMSE is in the model’s target scale.)

### From the project presentation
- Reported evaluation metric: **RMSE = 0.126177** :contentReference[oaicite:12]{index=12}

---

## Tech Stack
- Python
- Pandas, NumPy
- Scikit-learn
- TensorFlow / Keras
- Matplotlib / Seaborn

---

##  Dataset Access

The dataset used for this dissertation project is publicly accessible via Google Drive:

 **Dataset Folder:**  
https://drive.google.com/drive/folders/1-ovsEUyJc1sabMUmzwCFb6uaqgwdakBE?usp=sharing

Due to size constraints, the full dataset is not stored directly in this repository.  
Please download the required files and ensure they are placed in the correct directory before execution.
