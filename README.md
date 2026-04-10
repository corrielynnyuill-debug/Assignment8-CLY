# Assignment8-CLY
Assignment 8 Supervised Learning Classification


Fish Market Regression Analysis
Predicting Fish Weight Using Linear Regression and Random Forest Models

Overview
This project applies supervised machine learning techniques to a regression problem using the Fish Market dataset. The goal is to predict fish weight based on physical measurements and species information. The workflow includes data preprocessing, exploratory data analysis (EDA), model training, evaluation, interpretation, and a discussion of deployment and monitoring strategies.

Dataset
The dataset used in this project is the Fish Market dataset, publicly available on GitHub. It contains 159 samples with the following features:

Species

Weight (target variable)

Length1, Length2, Length3

Height

Width

A raw CSV version is loaded directly into the notebook.

Project Workflow
1. Data Preprocessing
Loaded dataset from GitHub.

Verified dataset integrity (no missing values or duplicates).

Encoded the categorical Species feature using one‑hot encoding.

Split the data into training and testing sets (80/20).

Built preprocessing pipelines using ColumnTransformer.

2. Exploratory Data Analysis (EDA)
EDA included both statistical summaries and visualizations:

Histograms of all numerical features

Species distribution plot

Correlation heatmap

Summary statistics and dataset structure

Key insights:

Weight is right‑skewed.

Length measurements are highly correlated.

Species distribution is uneven, with Bream and Perch dominating.

3. Models Implemented
Two regression models were trained and evaluated:

Linear Regression

Random Forest Regressor

Both models were wrapped in pipelines that included preprocessing and training steps.

4. Model Evaluation
Models were evaluated using:

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

R² Score

Model	MAE	RMSE	R²
Linear Regression	65.30	83.71	0.951
Random Forest	43.01	62.41	0.973


The Random Forest model outperformed Linear Regression across all metrics.

5. Model Interpretation
Visualizations included:

Actual vs. predicted scatterplots

Residual plots

Feature importance (Random Forest)

Findings:

Random Forest predictions align more closely with actual values.

Linear Regression residuals show non‑linear patterns.

Length3, Height, and Width are the most influential features.

Deployment Strategy
A realistic deployment approach includes:

Exporting the trained model using pickle or joblib.

Serving predictions via a REST API (FastAPI or Flask).

Validating incoming data to ensure measurement ranges match training data.

Logging predictions and inputs for monitoring and retraining.

Monitoring Considerations
To maintain model performance over time:

Track prediction errors to detect drift.

Monitor feature distributions for shifts in species mix or measurement patterns.

Retrain periodically as new data becomes available.

Implement alerts for out‑of‑range inputs or anomalous predictions.

Repository Structure
Code
├── notebook.ipynb        # Google Colab notebook with full workflow
├── README.md             # Project documentation
└── data/                 # (Optional) Local copy of dataset
How to Run
Open the notebook in Google Colab.

Install required Python libraries (if needed).

Run all cells in order.

Review visualizations and model outputs.
