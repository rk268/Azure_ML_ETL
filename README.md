# Car Price Prediction Using Azure Machine Learning Pipelines and REST API Deployment

<p align="center">
  <img src="https://drive.google.com/uc?id=1jV6UJnrLPJwlM_tfepe9KXfd0pkeVdop" alt="Azure ML Architecture" width="700">
</p>

## Project Overview

This project demonstrates an end-to-end solution for predicting vehicle prices based on various attributes like brand, horsepower, engine size, transmission type, and fuel type. Built entirely on **Azure Machine Learning Services**, it covers data ingestion, preprocessing, model training, evaluation, deployment, and real-time prediction through a REST API.

The dataset contained fields such as:
- Brand, Model, Transmission Type, Fuel Type, Color
- Horsepower, Engine Capacity, Mileage
- Selling Price (target variable)

---

## Workflow Architecture

- Azure ML Workspace for central orchestration
- Azure ML Datastore and Datasets for data management
- Data Ingestion and Cleaning Pipelines using Azure ML
- Feature Engineering (scaling with Min-Max and Z-Score normalization)
- Model Training with Regression Models (Random Forest, XGBoost)
- Evaluation Metrics: RMSE, MAE, R²
- Deployment using Azure ML Managed Online Endpoints
- Real-time Prediction via REST API (JSON input → Price Output)
- Monitoring and Alerting with Azure

---

## Process Breakdown

### 1. Data Ingestion
- Uploaded raw car datasets into Azure ML Datastore.
- Registered datasets for versioning and reproducibility.

### 2. Data Preprocessing
- Handled missing values and outliers.
- Encoded categorical features.
- Applied scaling techniques:
  - Min-Max Normalization
  - Z-Score Standardization

### 3. Model Training
- Splitted data into training and testing sets.
- Trained Random Forest and XGBoost Regression models.
- Cross-validated models and optimized hyperparameters.

### 4. Model Evaluation
- Evaluated model performance on the test set.
- Metrics used:
  - Root Mean Square Error (RMSE)
  - Mean Absolute Error (MAE)
  - Coefficient of Determination (R²)

### 5. Deployment
- Created a production pipeline combining preprocessing and inference.
- Deployed the model to a **Managed Online Endpoint**.
- Developed a scoring script to handle JSON inputs for real-time scoring.

### 6. Testing and Validation
- Sent JSON-formatted test inputs using Python scripts and Swagger UI.
- Successfully retrieved price predictions.

---

## Challenges Faced

- **Complex Feature Engineering:** Managing mixed types of data (categorical + continuous) and choosing the best normalization technique.
- **Pipeline Modularity:** Designing reusable and composable pipelines for training and production.
- **Overfitting on Sparse Categories:** Rare car brands caused overfitting, solved with smoothing techniques and filtering.
- **Schema Mismatch during Deployment:** Early failures due to input schema errors were resolved by strict schema validation.
- **Performance Optimization:** Fine-tuned model hyperparameters and parallelized training across compute clusters.

---

## Final Outcome

- End-to-end MLOps-ready project built entirely on Azure.
- Real-time vehicle price prediction through a REST API.
- Modular, reusable, and production-grade pipelines.
- Fully governed with versioning, monitoring, and scalability best practices.
- Ready for extension into AutoML or real-time streaming predictions in future enhancements.

---

## Technologies Used

- Azure Machine Learning
- Azure ML Pipelines
- Azure ML Compute Clusters
- Azure ML Managed Online Endpoints
- Python (Scikit-learn, XGBoost)
- Azure Storage Account
- Visual Studio Code (VS Code)

---
