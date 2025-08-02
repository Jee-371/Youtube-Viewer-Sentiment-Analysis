# Youtube-Viewer-Sentiment-Analysis

## 🧠 Overview
This project showcases a complete MLOps pipeline built for performing YouTube viewer sentiment analysis, integrated with a Chrome plugin for real-time inference. From model training to deployment, the pipeline demonstrates key stages of the machine learning lifecycle using tools like Python, Docker, AWS, and DVC (Data Version Control).

The primary goal is to analyze the sentiment of user comments on YouTube videos and seamlessly deliver predictions via a lightweight Chrome browser extension. The end-to-end pipeline is fully modular, production-ready, and CI/CD compliant.

---

## ✅ Current Progress

1. **AWS Setup**
   - Created an account on AWS and configured an S3 bucket for storing experiment logs and models.
   - Created an EC2 Instance to host the MLflow Server
   - Linked MLflow to store all logs and metrics directly to S3.

2. **Notebook Development**
   - Created multiple Jupyter notebooks to explore:
     - Data preprocessing and EDA.
     - Created a baseline model
     - Bag-of-Words vs TF-IDF vectorization.
     - Handling imbalanced datasets.
     - Model comparison and performance tuning (XGBoost, LightGBM, etc.).

3. **Modular Pipeline (src)**
   - Created reusable scripts for each stage:
     - `data_ingestion.py`: Splits the raw data.
     - `data_preprocessing.py`: Cleans and vectorizes the data.
     - `model_building.py`: Trains a LightGBM model with TF-IDF.
     - `model_evaluation.py`: Evaluates the trained model and logs metrics.
     - `register_model.py`: Registers the best model based on evaluation metrics.

4. **Experiment Tracking with MLflow**
   - All scripts are integrated with MLflow to log:
     - Parameters
     - Metrics
     - Artifacts (models, vectorizers, etc.)
   - Tracking URI is configured to point to AWS S3.

5. **DVC Pipeline Execution**
   - Implemented a reproducible ML pipeline using `dvc.yaml`:
     - `data_ingestion` → `data_preprocessing` → `model_building` → `model_evaluation` → `model_registration`
   - Final trained model and associated artifacts were generated successfully via DVC.

---
