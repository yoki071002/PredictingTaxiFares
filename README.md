# Predicting Taxi Fares: A Comparative Study of Multiple Linear and Ridge Regression Models

**Authors:** Chenjie Xu, Simiao Wu, Yutong Qin  
**Date:** 2025-12-08  

## Overview
This repository contains a statistical modeling pipeline comparing Multiple Linear Regression (MLR) and Ridge Regression to predict taxi trip prices. The project evaluates the influence of distance, duration, traffic, and time of day on fares, and extends to Logistic Regression for binary price classification. The analysis uses the [Taxi Price Prediction dataset](https://www.kaggle.com/datasets/denkuznetz/taxi-price-prediction?resource=download).

## Methods
Three main modeling approaches were applied:  
1. Multiple Linear Regression (MLR) – to explain variability in continuous taxi fares.  
2. Ridge Regression – to improve coefficient stability and handle moderate multicollinearity.  
3. Logistic Regression – to classify trips as high- or low-price based on the median fare.  

Variable selection techniques included Drop-1 residuals analysis, Added-Variable Plots (AV-Plots), and Lasso Regression traces.

Preliminary checks and data processing included:  
- Missing value imputation using median (continuous) and mode (categorical)  
- Normality test (Kolmogorov-Smirnov test) and Q-Q plots  
- Variance homogeneity (Bartlett’s test)  
- Multicollinearity tracking (VIFs and Multicollinearity Indices)  
- Logarithmic transformation of the response variable to address severe heteroscedasticity and heavy-tailed residuals  

## Key Findings
- `Trip_Distance` and `Trip_Duration` are highly significant predictors of taxi fares (p-values effectively 0).  
- Variables like `Day_of_Week`, `Weather`, and `Passenger_Count` were found to be redundant or marginally significant and were dropped or heavily penalized.  
- The original MLR model exhibited severe heteroscedasticity (Bartlett’s p = 0), which was successfully stabilized by applying a log transformation to the price.  
- Ridge Regression (optimal λ = 1) provided a conservative trade-off, serving as a safeguard against moderate multicollinearity (MCI ≈ 2.28) without sacrificing predictive accuracy.  

**Conclusion:** The study demonstrates a complete modeling pipeline, highlighting the practical importance of distance and duration in fare prediction and the value of combining classical regression diagnostics with modern regularization techniques.

## Files
- `MA416_Project2_Final.Rmd` – The full project report detailing the data preprocessing, model refinement, and classification.  
- `taxi_trip_pricing.csv` – The dataset used for the analysis.
