# TRANSFORMER-BASED-FORECASTING-OF-EV-CHARGING-DEMAND-WITH-MULTI-FEATURE-INTEGRATION

## Project Overview

This project investigates hourly Electric Vehicle (EV) charging demand forecasting using deep learning techniques, focusing on Long Short-Term Memory (LSTM) and Transformer architectures. The study evaluates the influence of historical charging demand and external variables, including weather conditions, traffic information, and EV adoption indicators, on forecasting performance.

The research aims to improve hourly EV charging demand prediction to support smart grid planning, electricity demand management, and EV charging infrastructure development.

## Research Objectives

1. To prepare an hourly EV charging demand dataset by integrating historical charging demand with relevant external variables.
2. To develop LSTM and Transformer models for hourly EV charging demand forecasting using different input feature combinations.
3. To evaluate and compare the forecasting performance of LSTM and Transformer models using RMSE, MAE, and R².

## Dataset Description

The study uses EV charging data obtained from the research dataset *Electric Vehicle Charging Dataset with 35,000 Charging Sessions from 12 Residential Locations in Norway* by Sørensen et al. (2024).

Dataset 4, *Hourly Predictions per Charging Session*, was selected for model development. It provides estimated hourly charging energy based on charging-session information.

The forecasting experiments focus on February to December 2019, incorporating the following variables:

- Historical EV charging demand
- Hourly traffic information
- Weather conditions
- Monthly EV sales indicators

## Experimental Configurations

Six input feature configurations were evaluated for both forecasting architectures.

| Configuration | Input Features | Number of Features |
|---|---|---|
| 1 | Historical charging demand | 1 |
| 2 | Historical demand + Traffic | 2 |
| 3 | Historical demand + Weather | 11 |
| 4 | Historical demand + EV sales | 2 |
| 5 | Historical demand + Traffic + Weather | 12 |
| 6 | Historical demand + Traffic + Weather + EV sales | 13 |

The experiments used a 24-hour historical input window to predict EV charging demand one hour ahead.

## Repository Structure

### LSTM

The `LSTM/` directory contains six individual LSTM experimental notebooks, corresponding to the different input feature configurations.

### Transformer

The `Transformer/` directory contains six individual Transformer experimental notebooks, corresponding to the same feature configurations.

Each notebook includes data preprocessing, model development, training, evaluation, and forecasting visualisation.

## Forecasting Performance

The best-performing configurations for each architecture are summarised below.

| Model | Best Input Configuration | RMSE (kWh) | MAE (kWh) | R² |
|---|---|---:|---:|---:|
| LSTM | Historical demand + Traffic | 16.1576 | 11.2205 | 0.8253 |
| Transformer | Historical demand + Traffic + Weather | 13.1388 | 9.7781 | 0.8864 |

The best-performing Transformer configuration achieved an approximately 18.68% reduction in RMSE compared with the best-performing LSTM configuration.

The results indicate that selecting relevant external variables can improve forecasting performance, while incorporating all available features does not necessarily produce the best predictions.

## Tools and Technologies

- Python
- Google Colab
- TensorFlow and Keras
- Scikit-learn
- Pandas and NumPy
- Matplotlib
- Google Drive

## Research Limitations

The charging energy values in the revised dataset are estimated rather than directly measured. Furthermore, the experiments focus on a limited observation period and residential charging locations in Norway. Additional validation using measured charging data from different locations and years is recommended.

## Future Work

Future research could extend the forecasting framework to daily and weekly demand prediction, incorporate additional external variables, and investigate further Transformer hyperparameter optimisation.

## Project Information

**Programme:** Bachelor of Electrical and Electronics Engineering (Honours)

**Specialisation:** Power Systems

**Institution:** Universiti Teknologi PETRONAS (UTP)

**Project Type:** Final Year Project

**Year:** 2026

## References

Sørensen et al. (2024). *Electric Vehicle Charging Dataset with 35,000 Charging Sessions from 12 Residential Locations in Norway*. Data in Brief.
