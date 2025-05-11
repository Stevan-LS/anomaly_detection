# Anomaly Detection Project

## Overview
This project explores various anomaly detection techniques, implementing and comparing multiple approaches on different datasets. The work focuses on both unsupervised learning methods (Local Outlier Factor, Isolation Forest) and supervised classification techniques adapted for imbalanced datasets.

## Table of Contents
- [Installation](#installation)
- [Datasets](#datasets)
- [Methodology](#methodology)
- [Usage](#usage)
- [Results](#results)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/detection_anomalie.git
cd detection_anomalie

# Create and activate virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

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

## Usage

### Basic Example
```python
from anomaly_detection import AnomalyDetector

# Initialize detector
detector = AnomalyDetector(method='isolation_forest')

# Fit and predict
detector.fit(X_train)
predictions = detector.predict(X_test)

# Get anomaly scores
scores = detector.score_samples(X_test)
```

### Advanced Usage
```python
# Using SMOTE for imbalanced data
from anomaly_detection import BalancedAnomalyDetector

detector = BalancedAnomalyDetector(
    method='random_forest',
    sampling_strategy='smote'
)
```

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
- Python 3.8+
- pandas, numpy
- scikit-learn
- imbalanced-learn
- matplotlib
- seaborn (for enhanced visualizations)

## Author
Stevan Le Stanc