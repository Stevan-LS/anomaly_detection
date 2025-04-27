# Anomaly Detection Project

## Overview
This project explores various anomaly detection techniques, implementing and comparing multiple approaches on different datasets. The work focuses on both unsupervised learning methods (Local Outlier Factor, Isolation Forest) and supervised classification techniques adapted for imbalanced datasets.

## Datasets
The project analyzes three distinct datasets:
- **Mouse Dataset**: A simple 2D dataset for initial exploration and visualization
- **Credit Card Fraud Detection Dataset**: Real-world financial transaction data with fraudulent transactions as anomalies
- **KDDCup99 Dataset**: Network intrusion detection data with various attack types

## Methodology

### Unsupervised Anomaly Detection
- **Local Outlier Factor (LOF)**: Implemented to identify samples that have substantially different density from their neighbors
- **Isolation Forest**: Used for isolating observations by randomly selecting features and splitting values

### Classification with Imbalanced Data
Various strategies were implemented to handle class imbalance:
- **Oversampling**: SMOTE (Synthetic Minority Over-sampling Technique)
- **Undersampling**: Tomek Links
- **Specialized Classifiers**: Balanced Random Forest

### Models Evaluated
- Logistic Regression
- Random Forest
- Balanced Random Forest
- Combined approaches (RF+SMOTE, RF+Tomek Links, etc.)

## Key Features
- Data preprocessing pipeline including normalization and specialized encoding for categorical variables
- Custom evaluation framework using precision-recall curves and F1 scores
- Target encoding implementation for categorical features with high cardinality
- Strategic handling of imbalanced class distributions
- Threshold optimization for unsupervised methods

## Results
- For the KDDCup99 dataset, Random Forest combined with SMOTE achieved the best performance
- Visualizations demonstrate how different thresholds affect anomaly detection performance
- Comprehensive comparison between supervised and unsupervised approaches showing trade-offs in precision and recall

## Technologies Used
- Python
- pandas, numpy
- scikit-learn
- imbalanced-learn
- matplotlib

## Conclusion
The project demonstrates the relative strengths of different anomaly detection approaches and highlights the importance of carefully handling imbalanced data when working with real-world anomaly detection problems.