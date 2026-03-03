# multi-scale-lstm-energy-forecasting
Multi-scale LSTM model with attention mechanism for daily, weekly, and monthly residential energy forecasting using the London Smart Meters dataset. Integrates weather, holiday, and household features with PCA and Lasso-based feature selection to improve multi-horizon prediction accuracy.

**Overview**
<br>
This project implements a Multi-Scale Long Short-Term Memory (LSTM) model with an Attention mechanism for residential electricity consumption forecasting at multiple time horizons:
<br>
Daily forecasting
<br>
Weekly forecasting
<br>
Monthly forecasting
<br>
The model captures short-, medium-, and long-term temporal dependencies in household energy consumption data.
<br>
Developed as part of an MSc Big Data Science dissertation.
<br>
**Dataset**
<br>
This project uses the Smart Meter Energy Consumption Data in London Households dataset.
<br>
-5,567 London households
<br>
-November 2011 – February 2014
<br>
-Daily aggregated electricity consumption
<br>
Target variable: energy_mean (kWh)
<br>
**Dataset source:**
<br>
https://drive.google.com/drive/folders/1-ovsEUyJc1sabMUmzwCFb6uaqgwdakBE?usp=sharing
<br>
Additional integrated data:
<br>
-Weather data
<br>
-UK bank holidays
<br>
-ACORN household classification data
