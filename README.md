# 🌸 Iris Species Classification Using PySpark

## Overview of the Project
This project builds a **machine learning pipeline using Apache Spark (PySpark)** to classify Iris flower species (`setosa`, `versicolor`, and `virginica`). The project demonstrates how data preprocessing, machine learning execution, hyperparameter tuning and evaluation can be distributed and optimized. Three predictive classification models are **Logistic Regression**, **Decision Tree**, and **Random Forest**. This project aims to demonstrate how Spark can be used to process data efficiently and build classification models.

---

## Description of Dataset and Methodology

### 1. Dataset Characteristics
The dataset used is the classical **Iris Dataset**, which consist 5 columns:
* **Features**: `sepal_length`, `sepal_width`, `petal_length`, `petal_width` (all numeric measurements in cm).
* **Target Class**: `species` (categorical labels: `setosa`, `versicolor`, `virginica`).

### 2. Data Preprocessing 
The dataset is processed using **PySpark MLlib pipelines**:
#### Label Encoding
`StringIndexer` converts categorical labels (`species`) into numeric values (`label`)
#### Feature Engineering
`VectorAssembler` combines all feature columns into a single vector column called `features`
#### Train-Test Split
Dataset is split into: Training set and Testing set in ration 8:2
#### Model Training & Hyperparameter Optimization
For every model, hyperparameter spaces were evaluated across a **3-fold Cross Validator** framework to reduce overfitting ensure stable performance metrics.
* **Logistic Regression**: - Tuned parameters: Regularization (`regParam`) and Elastic Net mixing (`elasticNetParam`)
* **Decision Tree**:- Tuned parameter: Maximum depth (`maxDepth`)
* **Random Forest**: Ensemble model using multiple decision trees, tuned number of trees for optimal performance

---

## Summary of Results and Key Findings

### Evaluation Metrics Breakdown
The trained classifiers were comprehensively measured against testing subsets across four criteria: **Accuracy**, **Precision**, **Recall**, and **F1-Score**.

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | **96.55%** | **96.89%** | **96.55%** | **96.51%** |
| **Random Forest** | **96.55%** | **96.89%** | **96.55%** | **96.51%** |
| **Decision Tree** | 93.10% | 93.10% | 93.10% | 93.10% |

### Key Takeaways
1. **Top Performers**: Both **Logistic Regression** and **Random Forest** conducted the highest performance, with accuracy of **96.55%**.
2. **Optimal Model Selection**: Although performance metrics matched exactly between the two top models, **Logistic Regression** is considered as the most suitable model for this dataset. 
3. **Justification**: Compared to more complex models, Logistic Regression requires less processing power and trains quicker, making the model extremely efficient. It also provides better understanding since its coefficients clearly demonstrate how each petal and sepal measurement influences the final classification outcome.

---

## Instructions to Reproduce the Analysis

Follow these environment setups and steps to reproduce the pipeline on machine:

### 1. Prerequisites
Ensure the following core software are installed:
* **Python**: `3.9` or higher
* **Java Development Kit (JDK)**: Version 8 or 11 (Required for PySpark execution)
  
### 2. Data Setup
* Download the source dataset (iris.csv)

### 3. Running via Jupyter Notebook (Recommended)
* Download and open STQD6324_Assignment_1.ipynb.
* Clear all existing cell outputs (Kernel -> Restart & Clear Output).
* Run all cells sequentially (Cell -> Run All) to re-execute the Spark session initialization, feature engineering, hyperparameter tuning, and final model evaluation.

### 4. Expected Output
* Model training logs
* Cross-validation 
* Evaluation metrics: Accuracy, Precision, Recall, F1-score
