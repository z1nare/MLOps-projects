# MLOps Projects Portfolio 🚀

Welcome to my **MLOps portfolio**, a collection of projects showcasing best practices in machine learning operations, including experiment tracking, reproducible pipelines, and systematic model evaluation.

This repository demonstrates how to take machine learning models from experimentation to reproducible, well-tracked workflows using modern MLOps tooling.

---

## 🌤️ Featured Project: London Weather Prediction

### 📖 Project Overview

As climate change increasingly impacts daily life and business operations, accurate weather forecasting has become more important than ever.

This project focuses on **predicting the daily mean temperature (`mean_temp`) in London** using historical weather data. The primary goal was to build and compare regression models while applying **MLOps best practices**, particularly experiment tracking and reproducibility with **MLflow**.

**Objective**
- Predict `mean_temp` (°C)
- Achieve **RMSE ≤ 3.0°C**
- Systematically compare models, pipelines, and hyperparameters

---

## 📂 Dataset

**File:** `london_weather.csv`

The dataset contains historical daily weather observations, including:

- **Target**
  - `mean_temp` (°C)

- **Features**
  - `cloud_cover`
  - `sunshine`
  - `global_radiation`
  - `precipitation`
  - `pressure`
  - `snow_depth`
  - `max_temp`, `min_temp`, and others

### 🧹 Preprocessing

- **Date Parsing**
  - Converted `YYYYMMDD` integers into proper `datetime` objects
  - Set `date` as the DataFrame index for time-series operations

- **Missing Value Imputation**
  - Hybrid strategy:
    - **Rolling Mean (window = 15 days)** for short gaps
    - **Seasonal averaging (day/month)** for longer missing periods

---

## 🛠️ Tech Stack & Methodology

- **Language:** Python  
- **Experiment Tracking:** MLflow  
  - Autologging  
  - Nested runs  
  - Custom metrics  
- **Modeling:** Scikit-Learn  
  - Linear Regression  
  - Decision Tree Regressor  
  - Random Forest Regressor  
- **Optimization:**  
  - `RandomizedSearchCV`  
  - `GridSearchCV`  
- **Pipelines:**  
  - Sklearn Pipelines  
  - Feature scaling using:
    - `StandardScaler`
    - `MinMaxScaler`
    - `Normalizer`

---

## 📊 Key Results

Multiple experiments were conducted comparing:
- Raw models
- Hyperparameter-tuned models
- Scaled pipeline variants

### 🏆 Performance Highlights

| Metric | Value |
|------|------|
| Target RMSE | ≤ 3.0 |
| Best Model | RandomForestRegressor (Tuned + CV) |
| Achieved RMSE | **~0.93** |

The final model significantly outperformed the target threshold.

![Model performance plot](LondonTemp/output.png)

---

## 🔄 MLflow Experiment Workflow

The project uses a **nested MLflow run structure** for clarity and reproducibility:

- **Parent Run**
  - Represents the model family (e.g., `RandomForest`)

- **Child Runs**
  - **Raw:** Baseline model performance
  - **Tuned:** Hyperparameter optimization with cross-validation
  - **Pipelines:** Evaluation of different scaling strategies

This structure enables clean comparison across modeling decisions.
![MLflow experiment tracking](LondonTemp/output2.png)

---

## 🚀 How to Run This Project

### 1️⃣ Repository Structure

```

MLOps-projects/
├── london_weather.csv      # Dataset
├── london_temp.ipynb       # Main notebook
├── requirements.txt
├── .gitignore
└── README.md

````

---

### 2️⃣ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/yourusername/MLOps-projects.git
cd MLOps-projects
pip install -r requirements.txt
````

---

### 3️⃣ Run Experiments

Launch the notebook and execute the training workflow:

```bash
jupyter notebook london_temp.ipynb
```

---

### 4️⃣ View Experiments in MLflow

Start the MLflow UI:

```bash
mlflow ui
```

Then open your browser at:

```
http://localhost:5000
```

Use the UI to inspect:

* Parameters
* Metrics
* Artifacts
* Model comparisons

---

## 🔮 Future Improvements

* **Model Registry**

  * Promote the best model to *Staging* using the MLflow Model Registry

* **Deployment**

  * Serve the model via REST API using MLflow Serving or FastAPI

* **Automation**

  * Add CI/CD with GitHub Actions for testing and experiment validation

---

## 📌 Key Takeaways

* Demonstrates end-to-end ML experimentation with MLOps principles
* Emphasizes reproducibility and structured experimentation
* Showcases practical use of MLflow in a real-world regression problem

---

Feel free to explore the code, experiment with models, or reach out with questions!

```

---

If you’d like, I can:
- Add **badges** (MLflow, Python, Scikit-Learn)
- Rewrite this for **GitHub + LinkedIn portfolio**
- Create a **second README** focused on recruiters/non-technical readers
- Review `requirements.txt` for best practices

Just tell me 👍
```
