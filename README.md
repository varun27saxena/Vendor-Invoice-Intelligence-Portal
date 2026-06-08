# Vendor Invoice Intelligence Portal

## Overview

The Vendor Invoice Intelligence Portal is an end-to-end machine learning application designed to support procurement and finance teams by automating two critical business processes:

1. Freight Cost Prediction – Estimate freight charges before invoice arrival to improve budgeting and cost forecasting.
2. Invoice Risk Flagging – Identify invoices that may require manual review based on cost discrepancies and operational anomalies.

The solution combines data engineering, machine learning, model optimization, and interactive deployment through Streamlit to provide actionable business insights in real time.

---

## Business Problem

Organizations process thousands of vendor invoices and purchase orders every month. Manual analysis of freight costs and invoice validation introduces several challenges:

- Inaccurate freight cost forecasting
- Time-consuming invoice review processes
- Increased operational overhead
- Risk of approving abnormal or inconsistent invoices
- Difficulty identifying potential financial discrepancies

This project addresses these challenges using predictive analytics and machine learning.

---

## Project Objectives

### Freight Cost Prediction

Predict freight charges using purchase order and invoice information.

Business Benefits

- Improved budgeting accuracy
- Better vendor cost analysis
- Enhanced procurement planning
- Faster cost estimation before invoice receipt

### Invoice Risk Flagging

Predict whether an invoice should be flagged for manual review.

Business Benefits

- Reduced manual effort
- Faster invoice processing
- Improved financial controls
- Early detection of unusual transactions

---

## Technology Stack

### Programming Language

- Python

### Data Processing

- Pandas
- NumPy
- SQLite

### Machine Learning

- Scikit-Learn
- Random Forest
- Decision Tree
- Linear Regression
- Logistic Regression
- GridSearchCV

### Statistical Analysis

- SciPy

### Visualization

- Plotly
- Matplotlib
- Seaborn

### Deployment

- Streamlit

### Model Serialization

- Joblib

---

## Project Architecture

text Raw Data (SQLite Database)             |             v      Data Extraction             |             v    Feature Engineering             |             v      Model Training             |             v  Hyperparameter Tuning             |             v       Model Saving             |             v       Streamlit App             |             v       User Prediction 

---

## Dataset Processing

The original data is stored in a SQLite database and contains information related to:

- Purchase Orders
- Vendor Invoices
- Freight Costs
- Receiving Delays
- Payment Information
- Product Quantities
- Invoice Values

Data preprocessing includes:

- SQL-based aggregation
- Missing value handling
- Feature engineering
- Statistical analysis
- Train-test splitting
- Feature scaling

---

## Freight Cost Prediction Model

### Input Features

- Quantity
- Dollars

### Models Evaluated

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

### Evaluation Metrics

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

### Best Model

Linear Regression achieved the best performance on the evaluation dataset.

---

## Invoice Risk Flagging Model

### Input Features

- Invoice Quantity
- Invoice Dollars
- Freight Cost
- Total Item Quantity
- Total Item Dollars

### Models Evaluated

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

### Optimization

Hyperparameter tuning was performed using:

- GridSearchCV
- Cross Validation
- F1 Score Optimization

### Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1 Score
- Classification Report

---

## Application Features

### Freight Cost Prediction Module

Allows users to estimate freight costs by providing invoice details.

Inputs

- Quantity
- Invoice Dollars

Output

- Predicted Freight Cost

### Invoice Risk Assessment Module

Allows users to evaluate whether an invoice should be manually reviewed.

Inputs

- Invoice Quantity
- Invoice Dollars
- Freight Cost
- Total Item Quantity
- Total Item Dollars

Output

- Auto Approval Recommendation
- Manual Review Recommendation

---

## Project Structure

text Vendor-Invoice-Intelligence-Portal/ │ ├── app.py ├── requirements.txt │ ├── inference/ │   ├── predict_freight.py │   └── predict_invoice_flag.py │ ├── models/ │   ├── predict_freight_model.pkl │   ├── predict_flag_invoice.pkl │   └── scaler.pkl │ ├── Freight Cost Prediction/ │   ├── train.py │   ├── data_preprocessing.py │   └── model_evaluation.py │ ├── Invoice Flagging/ │   ├── train.py │   ├── data_preprocessing.py │   └── model_evaluation.py │ └── Notebooks/ 

---

## Installation

Clone the repository:

bash git clone https://github.com/your-username/Vendor-Invoice-Intelligence-Portal.git cd Vendor-Invoice-Intelligence-Portal 

Install dependencies:

bash pip install -r requirements.txt 

---

## Running the Application

Start the Streamlit application:

bash streamlit run app.py 

The application will be available at:

text http://localhost:8501 

---

## Future Improvements

- Advanced anomaly detection models
- Explainable AI integration
- Vendor performance analytics
- Real-time database integration
- Cloud-based deployment
- Automated retraining pipelines
- Model monitoring and drift detection

---

## Key Learning Outcomes

This project demonstrates practical implementation of:

- Data Extraction using SQL
- Feature Engineering
- Statistical Testing
- Regression Modeling
- Classification Modeling
- Hyperparameter Optimization
- Model Serialization
- Production Inference Pipelines
- Streamlit Deployment
- End-to-End Machine Learning Workflow

---

## Author

Varun Saxena
