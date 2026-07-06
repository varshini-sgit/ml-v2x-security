# Machine Learning for V2X Network Security: Intrusion Detection and PKI Authentication Classification

## Overview
This project presents a dual-experiment machine learning study focused on two key security challenges in Vehicle-to-Everything (V2X) communication networks: intrusion detection and PKI authentication classification.

The project was completed as part of the MSc in Data Analytics at the National College of Ireland for the module Data Mining and Machine Learning. It combines domain knowledge from my background of connected vehicle systems with practical machine learning.

## Problem Statement
As connected vehicle ecosystems expand, V2X communication becomes more vulnerable to security threats at both the network and authentication levels. This project addresses:

- Detection of anomalous or malicious network traffic
- Classification of PKI-authenticated vs non-authenticated V2X communication
- Interpretability of model decisions for security-focused applications

## Objectives
- Build an intrusion detection model using the NSL-KDD dataset
- Build a PKI authentication classification model using the BME V2X real measurement dataset
- Compare multiple machine learning algorithms
- Apply explainability techniques to understand model behavior
- Evaluate results using robust validation and statistical testing

## Datasets
### 1. NSL-KDD Dataset
Used for binary intrusion detection classification.

- 22,544 records
- 41 features
- Target classes: Normal vs Anomaly/Attack

### 2. BME V2X Real Measurement Dataset
Used for PKI authentication anomaly classification.

- Real-world V2X communication logs
- Collected on the M0 motorway in Hungary
- Includes communication data across multiple vehicles
- Features derived from physical, GeoNetworking, BTP, and CAM layers

## Methodology
This project follows the **CRISP-DM** framework:

1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modelling
5. Evaluation
6. Deployment Readiness

### Data Preparation
- Label encoding for categorical variables
- Feature scaling using `StandardScaler`
- Missing value handling using median imputation
- Feature engineering on communication and signal attributes
- SMOTE applied only when class imbalance exceeded the defined threshold
- SQLite used for dataset persistence and reproducibility

## Models Used
### Experiment A: Intrusion Detection
- Decision Tree
- Multi-Layer Perceptron (MLP)

### Experiment B: PKI Authentication Classification
- Random Forest
- XGBoost

## Model Evaluation
The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- 5-fold Stratified Cross-Validation
- GridSearchCV for hyperparameter tuning
- McNemar’s Test
- Wilcoxon Signed-Rank Test

## Key Results
### Experiment A: Intrusion Detection
- Decision Tree achieved **98.3% accuracy**
- MLP achieved **97.9% accuracy**
- MLP achieved **ROC-AUC of 0.997**

### Experiment B: PKI Authentication Classification
- Random Forest achieved **97.7% accuracy**
- XGBoost achieved **97.7% accuracy**
- Both models achieved **ROC-AUC greater than 0.997**

## Explainability
SHAP was used to interpret model predictions in the PKI authentication experiment.

A key finding from the analysis was that **GeoNetworking payload length** emerged as the most important feature for distinguishing PKI-ON and PKI-OFF communication. The results also showed that relying on a single feature alone may be risky, which highlights the importance of multi-feature security analysis in V2X systems.

## Tech Stack
- Python
- Scikit-learn
- XGBoost
- SHAP
- Pandas
- NumPy
- SQLite
- Matplotlib
- Seaborn
- Jupyter Notebook

## Repository Structure
```bash
.
├── data/
├── notebooks/
├── src/
├── images/
├── report/
├── results/
└── README.md
```

## Suggested Files to Include
To make this repository stronger, include:

- Final project report PDF
- Jupyter notebooks or Python scripts
- `requirements.txt`
- Screenshots of:
  - title/abstract page
  - key results
  - SHAP plot
  - workflow or methodology diagram

## Learning Outcomes
Through this project, the following areas were strengthened:

- Machine learning for cybersecurity applications
- End-to-end classification workflow design
- Model explainability using SHAP
- Statistical validation of model performance
- Application of analytics in connected vehicle systems

## Future Improvements
Possible next steps for this work include:

- Multi-class intrusion detection across attack categories
- LSTM or Transformer-based sequence modelling
- Testing robustness against payload-padding attacks
- Distributed intrusion detection for roadside units
- Additional explainability analysis across multiple V2X scenarios

## Author
**Varshini Shashi Kumar**  
MSc Data Analytics, National College of Ireland
LinkedIn: [https://www.linkedin.com/in/varshini-s-02ba11210/]

## Project Note
This repository showcases an academic machine learning project developed in the context of V2X network security and connected vehicle communication. It reflects both technical implementation and domain-specific understanding of automotive cybersecurity challenges.
