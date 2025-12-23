# Paris Traffic Predictive Congestion System

## Overview

The **Paris Traffic Predictive Congestion System** is a machine learning project designed to forecast traffic congestion in Paris by predicting the **Occupancy Rate ($k$)** one hour in advance. The project transitions from simple linear baselines to advanced ensemble methods to provide actionable insights for proactive urban mobility management.

## Authors

* **Houssam ELMOUEDDEN** 


* **Rochdy BACHABI** 


* **Gabriel MENDES** 



## Dataset & Scope

* **Source:** "Trafic Capteurs 2024" from Paris Open Data.


* **Timeframe:** 9 weeks of data (January to March 2024).


* **Scope:** Focused on a strategic subset of **10 high-density arcs** (including the Champs-Élysées and Boulevard Voltaire) to ensure high data quality and model reliability.


* **Target Variable:** **Occupancy Rate ()**, representing the percentage of time a road sensor is covered by a vehicle.



## Methodology & Preprocessing

To address data quality issues and improve predictive power, several preprocessing steps were implemented:

* **Missing Data Handling:** Used **KNN Imputation ()** to reconstruct missing sensor readings based on spatial neighbors.


* **Feature Engineering:** * **Temporal Features:** Created features for hour of the day and day of the week to capture traffic seasonality.


* **Lag Features:** Integrated historical "lags" () to provide models with the context of the previous hour's traffic.


* **Spatial Encoding:** Utilised One-Hot Encoding for unique Arc IDs to differentiate specific street segments.



## Models Compared

The project benchmarks four distinct architectures to identify the most effective forecaster:

1. **Linear Regression (LR):** The foundational baseline used to establish performance against linear trends.


2. **Bagging SVM:** An ensemble approach using Support Vector Machines with Bootstrap Aggregating to reduce variance and enhance stability.


3. **Random Forest (RF):** A tree-based ensemble model chosen for its ability to capture complex, non-linear relationships and traffic spikes.


4. **LSTM (Deep Learning):** A Recurrent Neural Network intended to learn long-term sequential dependencies in time-series data.



## Results

| Model | Performance Summary |
| --- | --- |
| **Random Forest** | <br>**Winner:** Achieved the highest accuracy with an **** and the lowest RMSE.

 |
| **Linear Regression / SVM** | <br>**Strong Baselines:** Both maintained an ****, indicating strong linear correlations in traffic patterns.

 |
| **LSTM** | <br>**Underperformed:** Showed surprisingly low  and high loss, likely due to the dataset size being insufficient for deep learning requirements.

 |

## Key Takeaway

High-quality feature engineering—specifically the use of temporal lags and time-based variables—proved more critical to model success than algorithmic complexity for this 1-hour forecasting challenge.

## Future Roadmap

* **Scaling:** Expanding the model to encompass the entire Parisian sensor network beyond the initial 10 arcs.


* **External Data:** Integrating weather patterns (rain, snow) and holiday calendars to improve outlier prediction accuracy.


* **Dynamic Forecasting:** Transitioning toward real-time adaptive predictions for live urban mobility management.
