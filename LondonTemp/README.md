MLOps Projects Portfolio 🚀

Welcome to my MLOps portfolio! This repository documents my journey in applying MLOps best practices—experiment tracking, model pipelines, and reproducibility—to real-world machine learning problems.

🌤️ Featured Project: London Weather Prediction

📖 Project Overview

As climate change impacts daily life and business operations, accurate weather forecasting is becoming increasingly critical. This project focuses on predicting the Mean Temperature (mean_temp) in London using historical weather data.

The objective was to build a regression model that achieves a Root Mean Squared Error (RMSE) of ≤ 3.0°C, utilizing MLflow to track experiments, tune hyperparameters, and compare model architectures systematically.

📂 Dataset

The dataset (london_weather.csv) contains historical weather records including:

Target: mean_temp (°C)

Features: cloud_cover, sunshine, global_radiation, precipitation, pressure, snow_depth, etc.

Preprocessing:

Date Parsing: Converted dates and set as index for time-series operations.

Imputation: Implemented a hybrid approach using Rolling Means (window=15) for short gaps and Seasonal Averaging (day/month) for longer gaps.

🛠️ Tech Stack & Methodology

Experiment Tracking: MLflow (Autologging, Nested Runs, Custom Metrics)

Modeling: Scikit-Learn (Linear Regression, Random Forest, Decision Tree)

Optimization: RandomizedSearchCV & GridSearchCV

Pipelines: Sklearn Pipelines with robust scaling (MinMaxScaler, StandardScaler, Normalizer)

📊 Key Results

I ran multiple experiments, comparing raw models against hyperparameter-tuned versions and scaled pipelines.

Performance Highlight:

Target RMSE: ≤ 3.0

Best Model Achieved: RandomForestRegressor (Tuned/Cross-Validated)

Achieved RMSE: ~0.93 (Significantly outperforming the target)

🔄 MLflow Experiment Workflow

The project implements a nested run structure to keep experiments organized:

Parent Run: Represents the Model Class (e.g., "RandomForest").

Child Runs:

Raw: Baseline performance.

Tuned: Randomized Search CV with KFold.

Pipelines: Testing different scaling strategies.

🚀 How to Run This Project

1. Structure

MLOps-projects/
├── london_weather.csv      # Dataset
├── london_temp.ipynb       # Main Notebook
├── .gitignore
├── README.md
└── requirements.txt


2. Installation

Clone the repository and install the dependencies:

git clone [https://github.com/yourusername/MLOps-projects.git](https://github.com/yourusername/MLOps-projects.git)
cd MLOps-projects
pip install -r requirements.txt


3. Run Experiments

Open the notebook to execute the training loop:

jupyter notebook london_temp.ipynb


4. View Results in MLflow UI

To inspect the run logs, metrics, and artifacts:

mlflow ui


Then open http://localhost:5000 in your browser.

🔮 Future Improvements

Model Registry: Promote the best model to the 'Staging' environment using MLflow Model Registry.

Deployment: Serve the model via a REST API (using MLflow serving or FastAPI).

Automation: Implement a GitHub Actions workflow for CI/CD.

