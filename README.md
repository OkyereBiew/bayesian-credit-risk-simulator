# Bayesian Credit Risk Simulator

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/a7879a2d-8cbb-4876-942e-a80f909906fb" />

## Overview

The Bayesian Credit Risk Simulator is a probabilistic financial analytics project that applies Bayesian Logistic Regression to estimate borrower default risk while explicitly quantifying predictive uncertainty.

Traditional credit scoring models often provide deterministic predictions that fail to communicate uncertainty in borrower risk estimates. This project addresses this limitation by leveraging Bayesian inference and Markov Chain Monte Carlo (MCMC) sampling to generate posterior default probabilities and uncertainty-aware borrower risk profiles.

The framework demonstrates how Bayesian statistics can support more transparent, interpretable, and risk-sensitive decision-making in credit risk management.

---

## Research Question

**Can Bayesian inference improve credit risk assessment by providing uncertainty-aware estimates of borrower default probabilities and interpretable risk segmentation?**

---

## Project Objectives

* Analyze borrower credit risk characteristics
* Build a Bayesian Logistic Regression model
* Estimate posterior default probabilities
* Quantify uncertainty in borrower risk predictions
* Develop borrower risk categories
* Evaluate predictive performance using classification metrics
* Demonstrate practical applications of Bayesian statistics in finance

---

## Dataset

This project uses the German Credit Dataset from the UCI Machine Learning Repository.

### Dataset Characteristics

| Feature | Value |
| ------------------- | --------------------: |
| Observations | 1,000 |
| Predictor Variables | 20 |
| Target Variable | Credit Risk |
| Problem Type | Binary Classification |

### Target Variable

| Value | Interpretation |
| ----- | -------------- |
| 0 | Good Credit |
| 1 | Bad Credit |

### Dataset Source

https://archive.ics.uci.edu/ml/datasets/statlog+%28german+credit+data%29

---

## Methodology

### Notebook 01: Exploratory Data Analysis

- Class distribution analysis  
- Variable exploration  
- Descriptive statistics  
- Risk profile assessment  

---

### Credit Risk Distribution

<img width="513" height="470" alt="image" src="https://github.com/user-attachments/assets/e7d9a4a2-6d99-4fb8-b732-8a0026697537" />

---

### Notebook 02: Data Preprocessing

- Label encoding of categorical variables  
- Feature scaling using StandardScaler  
- Construction of modeling dataset  

---

### Notebook 03: Bayesian Logistic Regression

- PyMC probabilistic modeling  
- MCMC sampling (NUTS)  
- Posterior estimation of borrower risk  

---

### Posterior Probability Distribution

<img width="686" height="470" alt="image" src="https://github.com/user-attachments/assets/dc0743f6-4f09-41e3-8a42-6ae3114a428b" />

This plot shows the distribution of predicted default probabilities, capturing uncertainty across all borrowers.

---

## Notebook 04: Probabilistic Risk Analysis

- Posterior default probability estimation  
- Borrower risk segmentation  
- Risk category assignment  

---

### Borrower Risk Segmentation

<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/dc62a42f-126c-4155-a8a2-95a12939cf88" />

Borrowers are grouped into low, medium, and high-risk categories based on posterior default probabilities.

---

## Notebook 05: Model Evaluation

- Accuracy evaluation  
- Confusion matrix  
- Classification report  
- ROC curve analysis  

---

### Confusion Matrix (Model Performance)

<img width="513" height="470" alt="image" src="https://github.com/user-attachments/assets/e7d9a4a2-6d99-4fb8-b732-8a0026697537" />

This confusion matrix shows how well the model distinguishes between good and bad credit borrowers, highlighting correct and incorrect classifications.

---

###  ROC Curve

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/8d2c9ee2-f6b0-4ab1-bf08-b1746b1e6450" />

This ROC curve evaluates the model’s ability to distinguish between high-risk and low-risk borrowers across different thresholds.

---

## Key Findings

- The model effectively separates good and bad credit borrowers  
- Bayesian inference provides uncertainty-aware predictions  
- Posterior distributions improve interpretability  
- Risk segmentation supports financial decision-making  

---

## Financial Interpretation

This Bayesian model improves credit risk assessment by:

- Producing probability distributions instead of fixed outputs  
- Capturing uncertainty in predictions  
- Supporting risk-based lending decisions  
- Improving interpretability for financial institutions  

---

## Technologies Used

* Python
* PyMC
* ArviZ
* NumPy
* Pandas
* Scikit-Learn
* Matplotlib
* Seaborn
* Google Colab

---

## Repository Structure

```text
bayesian-credit-risk-simulator/
│
├── data/
│
├── images/
│   ├── confusion_matrix.png
│   ├── posterior_distribution.png
│   ├── risk_category_boxplot.png
│   └── roc_curve.png
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_bayesian_modeling.ipynb
│   ├── 04_risk_analysis.ipynb
│   └── 05_model_evaluation.ipynb
│
├── README.md
└── requirements.txt
````

---

## Statistical Techniques

* Bayesian Inference
* Logistic Regression
* MCMC Sampling (NUTS)
* Posterior Estimation
* Probabilistic Classification
* Uncertainty Quantification
* Financial Risk Modeling

---

## Portfolio Relevance

This project demonstrates:

* Bayesian statistical modeling
* Financial risk analytics
* Machine learning classification
* Probabilistic decision systems
* End-to-end data science workflow

---

## Future Enhancements

* Hierarchical Bayesian modeling
* Real-time credit scoring system
* Macroeconomic feature integration
* Explainable AI for lending decisions

---

## References

1. Bayesian Data Analysis
2. The Elements of Statistical Learning
3. PyMC Documentation: [https://www.pymc.io](https://www.pymc.io)
4. UCI German Credit Dataset: [https://archive.ics.uci.edu/ml/datasets/statlog+%28german+credit+data%29](https://archive.ics.uci.edu/ml/datasets/statlog+%28german+credit+data%29)

---

## Author

**Clement Kofi Okyere Biew**

Statistics | Data Science | Bayesian Statistics | Computational Statistics | Financial Risk Analytics | Quantitative Research

