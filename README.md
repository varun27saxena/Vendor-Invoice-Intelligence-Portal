# Vendor Invoice Intelligence Portal

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.3+-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-Deployed-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://vendor-invoice-intelligence-app-kqibgwa7hkzy3qcvf2c5hh.streamlit.app/)


> An end-to-end ML application that automates freight cost prediction and invoice risk flagging for procurement and finance teams — reducing manual overhead while improving financial controls.

**[Live Demo →](https://vendor-invoice-intelligence-app-kqibgwa7hkzy3qcvf2c5hh.streamlit.app/)**

---

## Overview

Organizations process thousands of vendor invoices every month. Manual freight cost estimation and invoice validation are slow, error-prone, and operationally expensive. This project automates both workflows using classical machine learning, exposing results through an interactive Streamlit interface.

Two core prediction pipelines are implemented:

| Module | Task | Best Model | Primary Metric |
|---|---|---|---|
| Freight Cost Prediction | Regression | Linear Regression | RMSE / R² |
| Invoice Risk Flagging | Binary Classification | Tuned Random Forest | F1 Score |

---

## Features

- **Freight Cost Prediction** — Estimate freight charges from PO quantity and invoice value before invoice receipt, enabling proactive budgeting
- **Invoice Risk Flagging** — Classify invoices as auto-approved or flagged for manual review based on cost discrepancies and operational anomalies
- **Hyperparameter Optimization** — GridSearchCV with cross-validation used to maximize F1 score on the classification task
- **Production-Ready Inference** — Serialized models and scalers served through a clean Streamlit UI with real-time predictions
- **Modular Architecture** — Training, preprocessing, and inference code fully separated for maintainability

---

## Tech Stack

**Data & ML**
`pandas` · `numpy` · `scikit-learn` · `scipy` · `SQLite`

**Visualization**
`plotly` · `matplotlib` · `seaborn`

**Deployment**
`streamlit` · `joblib`

---

## Architecture

```
SQLite Database
      │
      ▼
Data Extraction & SQL Aggregation
      │
      ▼
Feature Engineering & Preprocessing
      │
      ▼
Model Training (Regression + Classification)
      │
      ▼
Hyperparameter Tuning (GridSearchCV)
      │
      ▼
Model Serialization (Joblib)
      │
      ▼
Streamlit Application → Real-Time Predictions
```

---

## Models

### Freight Cost Prediction

**Input features:** `quantity`, `invoice_dollars`

Three regression models were evaluated — Linear Regression, Decision Tree Regressor, and Random Forest Regressor — using MAE, RMSE, and R² as evaluation metrics. Linear Regression achieved the best generalization on the held-out test set.

### Invoice Risk Flagging

**Input features:** `invoice_quantity`, `invoice_dollars`, `freight_cost`, `total_item_quantity`, `total_item_dollars`

Logistic Regression, Decision Tree Classifier, and Random Forest Classifier were evaluated. The Random Forest model was selected and further optimized via GridSearchCV targeting F1 score. Evaluation metrics include accuracy, precision, recall, F1, and a full classification report.

---

## Project Structure

```
Vendor-Invoice-Intelligence-Portal/
│
├── app.py                        # Streamlit entry point
├── requirements.txt
│
├── inference/
│   ├── predict_freight.py        # Freight cost inference pipeline
│   └── predict_invoice_flag.py   # Risk flagging inference pipeline
│
├── models/
│   ├── predict_freight_model.pkl
│   ├── predict_flag_invoice.pkl
│   └── scaler.pkl
│
├── Freight Cost Prediction/
│   ├── train.py
│   ├── data_preprocessing.py
│   └── model_evaluation.py
│
├── Invoice Flagging/
│   ├── train.py
│   ├── data_preprocessing.py
│   └── model_evaluation.py
│
└── Notebooks/
```

---

## Getting Started

**Clone the repository**
```bash
git clone https://github.com/varun27saxena/Vendor-Invoice-Intelligence-Portal.git
cd Vendor-Invoice-Intelligence-Portal
```

**Install dependencies**
```bash
pip install -r requirements.txt
```

**Run the application**
```bash
streamlit run app.py
```

The app will be available at `http://localhost:8501`.

---

## Future Work

- [ ] Integrate explainability layer (SHAP values) for risk flag reasoning
- [ ] Anomaly detection module for unsupervised invoice screening
- [ ] Vendor performance analytics dashboard
- [ ] Real-time database integration and automated retraining pipelines
- [ ] Model monitoring with drift detection

---

## Author

**Varun Saxena**
