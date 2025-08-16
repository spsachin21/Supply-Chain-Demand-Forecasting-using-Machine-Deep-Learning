# Supply-Chain-Demand-Forecasting-using-Machine-Deep-Learning
 Probabilistic time series system with Bayesian based ML &amp; DL models to  capture uncertainty (prediction interval)

Project Description: 
This project focuses on time series sales forecasting using the train.csv dataset, which contains ~913,000 records of daily item sales across multiple stores. The dataset includes four key columns:

date — transaction date

store — store identifier

item — item identifier

sales — number of units sold (target variable)
The project uses the train.csv dataset (≈ 913,000 rows), which records daily item-level sales across multiple stores from 2013–2017.
The dataset is structured, tabular, and time-series, making it well-suited for both tree-based models and sequential deep learning architectures.
********************************************************************************************************************************************************
Introduction

The exponential growth of e-commerce has made sales forecasting a critical component of demand planning and inventory management. Traditional models often provide point forecasts but fail to capture uncertainty in predictions. This project not only develops and benchmarks machine learning and deep learning models for sales forecasting but also explores Bayesian uncertainty quantification to improve decision-making under risk.
***************************************************************************************************************************************************************************************************************************
Objectives

Forecast daily sales at the (store, item) level.

Compare tree-based models (Random Forest, XGBoost) with deep learning models (LSTM, CNN+LSTM).

Introduce Bayesian techniques to quantify prediction uncertainty.

Evaluate trade-offs between accuracy, interpretability, and computational efficiency.
***********************************************************************************************************************************************************
Methodology

1 Data Preparation

Converted dates, extracted temporal features (month, weekday, season).
Generated lag features and rolling averages.
Train/test split followed a temporal holdout (train on past, test on future).

2 Model Families

Classical Models: Linear Regression (baseline).
Tree-based Models: Random Forest, XGBoost. Strong with tabular, structured features.

Deep Learning Models:
LSTM: Captures sequential dependencies.
CNN+LSTM: Learns local patterns (via CNN) + long-term memory (via LSTM).

Bayesian Extensions:
MC Dropout: Dropout at inference to approximate Bayesian posterior.
Bayesian LSTM: Probabilistic weights, yielding predictive distributions rather than point forecasts.

3 Evaluation Metrics

Accuracy: MAE, RMSE, R².
Reliability: Prediction Intervals, Calibration of uncertainty.
Decision Value: Cost-benefit analysis of under- vs. over-forecasting.

Model Development

Implemented baseline regression models: Linear Regression and Random Forest.

Designed and trained deep learning models: LSTM and CNN+LSTM architectures for sequence forecasting.

Considered advanced alternatives like XGBoost (commented in the notebook).

Evaluation

Models were compared on their ability to predict sales with high accuracy.

LSTM/CNN+LSTM were tested to capture temporal dependencies, while tree-based and linear models provided benchmarks.

*********************************************************************************************
Results & Findings

Tree-based models (XGBoost, RF) performed strongly on point accuracy, especially with lag features.

Deep learning models (LSTM, CNN+LSTM) provided value in capturing temporal dynamics, especially for high-variance items.

Bayesian LSTM / MC Dropout improved uncertainty quantification:
Produced prediction intervals (e.g., 95% credible intervals).
Allowed risk-aware planning — e.g., maintaining higher safety stock when uncertainty was high.

In many structured forecasting tasks, XGBoost outperformed LSTM in accuracy vs. training time, but Bayesian deep learning had the edge in uncertainty estimation, which is critical for inventory optimization.

*********************
The project shows that XGBoost and Random Forest excel in predictive accuracy for structured sales data, but Bayesian deep learning models bring an extra dimension by quantifying uncertainty. In retail and supply chain contexts, where over-forecasting increases cost and under-forecasting risks stockouts, this probabilistic view is invaluable.

Thus, while XGBoost may “beat” CNN+LSTM in raw accuracy, Bayesian-enhanced deep learning models provide actionable insights under uncertainty, making them complementary rather than strictly inferior.
