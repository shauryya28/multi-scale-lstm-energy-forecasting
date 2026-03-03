# multi-scale-lstm-energy-forecasting
Multi-scale LSTM model with attention mechanism for daily, weekly, and monthly residential energy forecasting using the London Smart Meters dataset. Integrates weather, holiday, and household features with PCA and Lasso-based feature selection to improve multi-horizon prediction accuracy.

Overview
This project implements a Multi-Scale Long Short-Term Memory (LSTM) model with an Attention mechanism for residential electricity consumption forecasting at multiple time horizons:
Daily forecasting
Weekly forecasting
Monthly forecasting
The model captures short-, medium-, and long-term temporal dependencies in household energy consumption data.
Developed as part of an MSc Big Data Science dissertation.
Dataset
This project uses the Smart Meter Energy Consumption Data in London Households dataset.
5,567 London households
November 2011 – February 2014
Daily aggregated electricity consumption
Target variable: energy_mean (kWh)
Dataset source:
https://www.kaggle.com/datasets/jeanmidev/smart-meters-in-london
Additional integrated data:
Weather data
UK bank holidays
ACORN household classification data
