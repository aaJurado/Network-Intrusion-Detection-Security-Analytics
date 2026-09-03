# Network Intrusion Detection & Security Analytics

An end-to-end cybersecurity analytics and machine learning project using Python, Pandas, Matplotlib, Scikit-learn, and the UNSW-NB15 network intrusion dataset.

## Project Overview

This project analyzes network traffic to identify patterns associated with normal activity and malicious attacks.

The analysis explores attack categories, network protocols, services, and traffic behavior before building a machine learning model to classify network connections as either normal or malicious.

The project uses the official UNSW-NB15 training and testing datasets.

## Dataset

The UNSW-NB15 dataset was developed by the Australian Centre for Cyber Security at UNSW Canberra.

The project uses:

- 175,341 training records
- 82,332 testing records
- 45 original dataset columns
- Normal and malicious network traffic
- Multiple cyberattack categories

The dataset itself is not included in this repository because of its size.

## Technologies Used

- Python
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook
- VS Code
- GitHub

## Analysis Performed

The project includes:

- Data inspection and validation
- Missing-value and duplicate analysis
- Normal vs. malicious traffic analysis
- Attack category analysis
- Network protocol analysis
- Network service analysis
- Data preprocessing
- One-hot encoding of categorical variables
- Numerical feature scaling
- Logistic regression classification
- Model evaluation using unseen testing data
- Confusion matrix analysis
- Precision, recall, F1-score, and accuracy evaluation

## Key Findings

- Approximately 68% of the training dataset represents malicious traffic.
- Generic attacks were the most frequent attack category.
- Exploits were the second most frequent attack category.
- UDP and TCP accounted for the largest amounts of malicious traffic.
- DNS and HTTP were among the most common identifiable services associated with attack traffic.
- The intrusion detection model achieved approximately 81% accuracy.
- The model achieved approximately 97% recall for malicious traffic.
- The attack-class F1-score was approximately 85%.

## Machine Learning Model

A Logistic Regression classification model was developed using a Scikit-learn pipeline.

Categorical features such as protocol, service, and connection state were transformed using one-hot encoding, while numerical features were standardized before training.

The `label` variable was used as the prediction target:

- `0` = Normal traffic
- `1` = Attack traffic

The `attack_cat` variable was excluded from the model features to prevent target leakage.

## Model Performance

| Metric | Result |
|---|---:|
| Accuracy | 80.69% |
| Attack Precision | 75.08% |
| Attack Recall | 97.18% |
| Attack F1-Score | 84.71% |

### Confusion Matrix Results

- True Negatives: 22,375
- False Positives: 14,625
- False Negatives: 1,277
- True Positives: 44,055

The model prioritizes detecting malicious traffic, resulting in very high attack recall. The tradeoff is a higher number of false-positive security alerts.

## Security Interpretation

High recall is valuable in intrusion detection because failing to identify malicious activity can expose an organization to significant security risk.

However, excessive false positives can increase alert volume and analyst workload. Future improvements could focus on reducing false positives while preserving strong attack detection performance.

## Future Improvements

Potential improvements include:

- Testing additional machine learning algorithms
- Feature selection and engineering
- Hyperparameter tuning
- Detection threshold optimization
- Comparing Logistic Regression with Random Forest or gradient boosting models
- Multiclass classification of specific attack categories

## Repository Files

`network_intrusion_analysis.ipynb`  
Complete exploratory analysis, visualizations, machine learning workflow, and model evaluation.

## Author

Axel Jurado
