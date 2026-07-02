
# Bayesian Credit Risk Simulator

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/a7879a2d-8cbb-4876-942e-a80f909906fb" />


## Overview

The Bayesian Credit Risk Simulator is a probabilistic financial analytics project that applies Bayesian Logistic Regression to estimate borrower default risk while explicitly quantifying predictive uncertainty.

Traditional credit scoring models often provide deterministic predictions that fail to communicate uncertainty in borrower risk estimates. This project addresses that limitation by leveraging Bayesian inference and Markov Chain Monte Carlo (MCMC) sampling to generate posterior default probabilities and uncertainty-aware borrower risk profiles.

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

| Feature             |                 Value |
| ------------------- | --------------------: |
| Observations        |                 1,000 |
| Predictor Variables |                    20 |
| Target Variable     |           Credit Risk |
| Problem Type        | Binary Classification |

### Target Variable

| Value | Interpretation |
| ----- | -------------- |
| 0     | Good Credit    |
| 1     | Bad Credit     |

### Dataset Source

[UCI German Credit Dataset](https://archive.ics.uci.edu/ml/datasets/statlog+%28german+credit+data%29?utm_source=chatgpt.com)

---

## Methodology

### Notebook 01: Exploratory Data Analysis

Initial exploration focused on understanding borrower characteristics and credit risk distributions.

Key activities included:

* Class distribution analysis
* Variable exploration
* Descriptive statistics
* Risk profile assessment
* Financial interpretation of borrower characteristics

---

### Notebook 02: Data Preprocessing

Data preprocessing prepared the dataset for Bayesian modeling.

Tasks included:

* Handling categorical variables
* One-hot encoding
* Feature scaling
* Target variable transformation
* Construction of the modeling matrix

---

### Notebook 03: Bayesian Logistic Regression

The core model estimates borrower default probabilities using Bayesian inference.

The probability of default is modeled as:

Where:

* (Y = 1) indicates borrower default
* (X) represents borrower characteristics
* (\beta) represents model coefficients
* (\alpha) is the intercept

Posterior parameter estimation was performed using:

* Bayesian inference
* Markov Chain Monte Carlo (MCMC)
* PyMC probabilistic modeling

---

### Notebook 04: Probabilistic Risk Analysis

Posterior predictions were transformed into actionable borrower risk scores.

Outputs include:

* Posterior default probabilities
* Risk category assignment
* Borrower segmentation
* Probability-based risk interpretation

---

### Notebook 05: Model Evaluation

Model performance was evaluated using:

* Accuracy
* Confusion Matrix
* Classification Report
* ROC Curve
* ROC-AUC Analysis

The evaluation framework focuses on both predictive performance and uncertainty-aware decision support.

---

## Key Findings

### Credit Classification Performance

<img width="513" height="470" alt="image" src="https://github.com/user-attachments/assets/e7d9a4a2-6d99-4fb8-b732-8a0026697537" />

The confusion matrix demonstrates the model’s ability to distinguish between good-credit and bad-credit borrowers.

The Bayesian framework provides not only classification outcomes but also confidence estimates associated with those predictions.

---

### Posterior Probability Analysis

<img width="686" height="470" alt="image" src="https://github.com/user-attachments/assets/dc0743f6-4f09-41e3-8a42-6ae3114a428b" />


Posterior distributions reveal the uncertainty associated with estimated default probabilities.

Unlike traditional logistic regression, Bayesian inference produces full probability distributions rather than single-point estimates, allowing analysts to assess prediction confidence and model uncertainty.

---

### Borrower Risk Segmentation

<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/dc62a42f-126c-4155-a8a2-95a12939cf88" />


Borrowers were categorized into risk groups using posterior default probabilities.

This segmentation framework supports:

* Credit approval decisions
* Lending policy development
* Portfolio monitoring
* Risk-adjusted pricing

---

### Discriminatory Power

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/8d2c9ee2-f6b0-4ab1-bf08-b1746b1e6450" />


The ROC analysis evaluates the model’s ability to distinguish between low-risk and high-risk borrowers across varying classification thresholds.

Strong separation between classes indicates that Bayesian risk estimates contain meaningful predictive information.

---

## Financial Interpretation

The results demonstrate that Bayesian inference provides several advantages in credit risk analytics:

### Uncertainty Quantification

Instead of producing a single probability estimate, the model generates a posterior distribution describing the range of plausible borrower risk levels.

### Improved Interpretability

Posterior distributions allow analysts to understand the certainty associated with each prediction.

### Risk-Aware Lending Decisions

Financial institutions can incorporate prediction uncertainty directly into credit approval and risk management frameworks.

### Enhanced Portfolio Monitoring

Probability-based borrower segmentation supports dynamic portfolio risk assessment.

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
│   └── raw/
│
├── images/
│
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
├── requirements.txt
└── LICENSE
```

---

## Statistical Techniques Demonstrated

* Bayesian Statistics
* Bayesian Logistic Regression
* Markov Chain Monte Carlo (MCMC)
* Posterior Inference
* Probabilistic Classification
* Uncertainty Quantification
* Credit Risk Modeling
* Financial Risk Analytics
* Predictive Modeling
* Risk Segmentation

---

## Portfolio Relevance

This project demonstrates practical applications of:

* Bayesian and Computational Statistics
* Financial Risk Analytics
* Statistical Learning
* Predictive Modeling
* Quantitative Risk Management
* Probabilistic Decision Systems

The project showcases how Bayesian methods can improve transparency and interpretability in real-world financial analytics applications.

---

## Future Enhancements

* Hierarchical Bayesian Models
* Bayesian Neural Networks
* Dynamic Credit Risk Models
* Macroeconomic Variable Integration
* Explainable AI for Credit Decisions
* Real-Time Risk Monitoring Dashboards
* Stress Testing Simulations

---

## References

1. Bayesian Data Analysis
2. The Elements of Statistical Learning
3. [PyMC Documentation](https://www.pymc.io?utm_source=chatgpt.com)
4. [UCI Machine Learning Repository – German Credit Dataset](https://archive.ics.uci.edu/ml/datasets/statlog+%28german+credit+data%29?utm_source=chatgpt.com)

---

## Author

**Clement Kofi Okyere Biew**

Statistics | Data Science | Bayesian Statistics | Computational Statistics | Financial Risk Analytics | Quantitative Research

