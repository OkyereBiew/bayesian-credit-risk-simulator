# Bayesian Credit Risk Simulator

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/a7879a2d-8cbb-4876-942e-a80f909906fb" />

## Project Overview

This project develops a Bayesian credit risk modeling framework using the German Credit Dataset from the UCI Machine Learning Repository. It applies Bayesian Logistic Regression to estimate borrower default probabilities and explores how posterior probability estimates can support borrower risk classification.

Credit risk assessment is an important component of lending decisions. Financial institutions need methods for evaluating borrower characteristics, estimating the likelihood of default, and identifying applicants who may present higher repayment risks. This project explores a probabilistic modeling approach that combines borrower-level financial and demographic information with Bayesian inference.

Using Python, PyMC, and ArviZ, the project implements a Bayesian Logistic Regression model, estimates posterior borrower default probabilities, groups borrowers into risk categories, and evaluates classification performance using standard metrics.

Unlike an approach that reports only point estimates of model parameters, Bayesian inference produces posterior distributions that represent uncertainty about model parameters. The project introduces this perspective to credit risk analysis and demonstrates how posterior-based probability estimates can be used for risk assessment.

## Research Question

**How can Bayesian Logistic Regression be used to estimate borrower default probabilities and support uncertainty-aware credit risk assessment?**

## Project Objectives

The main objectives are to:

- Explore the distribution and characteristics of borrower information in the German Credit Dataset.
- Prepare categorical and numerical variables for Bayesian modeling.
- Develop a Bayesian Logistic Regression model using PyMC.
- Estimate posterior default probabilities for individual borrowers.
- Classify borrowers into low-, medium-, and high-risk categories using probability thresholds.
- Evaluate model classification performance using accuracy, precision, recall, F1-score, confusion matrix, and ROC-AUC.
- Explore the application of Bayesian inference to probabilistic credit risk assessment.

## Dataset Description

The analysis uses the **German Credit Dataset**, obtained from the UCI Machine Learning Repository.

The dataset contains 1,000 borrower records and 20 explanatory variables describing financial history, credit characteristics, loan information, and demographic attributes.

| Dataset characteristic | Description |
|---|---|
| Dataset | German Credit Dataset |
| Source | UCI Machine Learning Repository |
| Observations | 1,000 borrowers |
| Predictors | 20 variables |
| Target variable | Credit risk classification |
| Original target coding | 1 = Good Credit; 2 = Bad Credit |
| Modeling target coding | 0 = Good Credit; 1 = Bad Credit |

The target variable was recoded to represent bad credit as the positive class. The dataset contains 700 good-credit observations and 300 bad-credit observations, indicating an imbalance between the two classes.

The exploratory analysis also examines borrower age, credit amount, loan characteristics, and the distribution of credit risk categories. The credit amount variable exhibits a right-skewed distribution.

## Methodology

The project follows a five-notebook workflow, progressing from exploratory data analysis and preprocessing to Bayesian modeling, risk analysis, and model evaluation.

### 1. Exploratory Data Analysis

The first notebook examines the structure and characteristics of the German Credit Dataset.

Key activities include:

- Loading and inspecting the dataset.
- Examining variable types and dataset dimensions.
- Reviewing the distribution of good- and bad-credit borrowers.
- Summarizing numerical variables using descriptive statistics.
- Visualizing credit amount and borrower age distributions.
- Comparing credit amount distributions across credit risk categories.
- Checking for missing values.

The dataset contains 1,000 observations and 21 columns, including 20 predictors and the original target variable. No missing values were identified in the inspected dataset.

**Credit Risk Distribution**

<img width="513" height="470" alt="image" src="https://github.com/user-attachments/assets/e7d9a4a2-6d99-4fb8-b732-8a0026697537" />

### 2. Data Preprocessing

The second notebook prepares the dataset for Bayesian Logistic Regression.

The preprocessing workflow includes:

- Separating predictor variables from the target variable.
- Recoding the target variable so that good credit is represented by 0 and bad credit by 1.
- Identifying categorical predictor variables.
- Applying Label Encoding to categorical variables.
- Standardizing the predictor matrix using StandardScaler.
- Preparing the feature matrix and target vector for model estimation.

The resulting feature matrix contains 1,000 observations and 20 predictors, while the target vector contains 1,000 binary observations.

### 3. Bayesian Logistic Regression

The third notebook develops the Bayesian Logistic Regression model using PyMC.

The model specifies prior distributions for the regression coefficients and intercept:

- Regression coefficients are assigned Normal prior distributions with a mean of 0 and standard deviation of 1.
- The intercept is assigned a Normal prior distribution with a mean of 0 and standard deviation of 1.
- The linear predictor is transformed using the logistic sigmoid function to obtain borrower-level default probabilities.
- The observed binary credit outcomes are modeled using a Bernoulli likelihood.

Posterior sampling is performed using Markov Chain Monte Carlo (MCMC), with the following sampling configuration:

| Sampling parameter | Setting |
|---|---:|
| Posterior draws | 1,000 |
| Tuning iterations | 1,000 |
| Target acceptance rate | 0.90 |
| Random seed | 42 |

ArviZ is used to summarize and visualize the posterior sampling results, including posterior summaries and trace plots.

The notebook provides the foundation for estimating borrower default probabilities through a Bayesian modeling framework.

[![Open In Colab](https://camo.githubusercontent.com/bc9ece8f645afd1edbf69b3006353a59d93a267f24f566f7acf1460df39061bb/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667)](https://colab.research.google.com/github/OkyereBiew/bayesian-credit-risk-simulator/blob/main/notebooks/03_bayesian_modeling.ipynb)

### 4. Probabilistic Credit Risk Analysis

The fourth notebook uses posterior model estimates to derive borrower-level default probabilities.

For each borrower, the posterior mean probability is calculated by averaging the sampled values of the model's probability parameter across chains and posterior draws.

These estimated probabilities are then used to assign borrowers to three risk categories:

| Estimated default probability | Risk category |
|---|---|
| Below 0.30 | Low Risk |
| 0.30 to below 0.60 | Medium Risk |
| 0.60 and above | High Risk |

The notebook explores the resulting risk classifications through:

- Borrower counts across risk categories.
- The distribution of estimated posterior mean default probabilities.
- Comparisons of estimated probabilities across risk categories.

This stage demonstrates how Bayesian model estimates can be translated into probability-based borrower risk groups.

**Posterior Probability Distribution**

<img width="686" height="470" alt="image" src="https://github.com/user-attachments/assets/dc0743f6-4f09-41e3-8a42-6ae3114a428b" />

**Borrower Risk Segmentation**

<img width="691" height="470" alt="image" src="https://github.com/user-attachments/assets/dc62a42f-126c-4155-a8a2-95a12939cf88" />

### 5. Model Evaluation

The fifth notebook evaluates the classification performance of the Bayesian Logistic Regression model.

Using a probability threshold of 0.50, estimated borrower default probabilities are converted into binary predictions.

The evaluation includes:

- Accuracy.
- Precision.
- Recall.
- F1-score.
- Confusion matrix.
- Receiver Operating Characteristic (ROC) curve.
- Area Under the ROC Curve (ROC-AUC).

The notebook also visualizes predicted probability distributions to examine how estimated probabilities relate to the two observed credit classes.

**Confusion Matrix**

<img width="513" height="470" alt="image" src="https://github.com/user-attachments/assets/e7d9a4a2-6d99-4fb8-b732-8a0026697537" />

**ROC Curve**

<img width="613" height="470" alt="image" src="https://github.com/user-attachments/assets/8d2c9ee2-f6b0-4ab1-bf08-b1746b1e6450" />

**Evaluation Note:** The supplied evaluation workflow estimates and evaluates the model using the same 1,000 observations. Consequently, the reported classification metrics represent in-sample performance and should not be interpreted as evidence of predictive performance on previously unseen borrowers.

## Key Analytical Components

The project brings together several statistical and computational techniques:

- **Exploratory Data Analysis:** Descriptive statistics and visual analysis of borrower characteristics.
- **Data Preprocessing:** Categorical encoding and feature standardization.
- **Bayesian Logistic Regression:** Probabilistic binary classification using prior distributions and a Bernoulli likelihood.
- **MCMC Sampling:** Posterior estimation using PyMC.
- **Posterior Analysis:** Examination of posterior summaries and sampling visualizations using ArviZ.
- **Probability-Based Risk Segmentation:** Classification of borrowers using estimated default probabilities.
- **Classification Evaluation:** Assessment using confusion matrix, accuracy, precision, recall, F1-score, and ROC-AUC.

## Limitations and Future Improvements

The current implementation provides a foundation for Bayesian credit risk modeling, but several improvements would strengthen its predictive and analytical reliability.

Potential extensions include:

1. **Out-of-Sample Validation:** Introduce training and testing datasets or cross-validation to evaluate performance on unseen borrowers.
2. **Improved Categorical Encoding:** Explore one-hot encoding or alternative representations for nominal categorical variables to avoid imposing artificial numerical ordering.
3. **Posterior Predictive Uncertainty:** Extend the analysis to report borrower-specific posterior intervals and more fully examine uncertainty in individual default probability estimates.
4. **Model Comparison:** Compare Bayesian Logistic Regression with conventional Logistic Regression and other classification approaches using consistent validation procedures.
5. **Hierarchical Bayesian Modeling:** Investigate hierarchical structures that can represent variation across borrower groups or credit segments.
6. **Additional Predictors:** Incorporate relevant macroeconomic and financial indicators to examine how broader economic conditions influence credit risk.
7. **Decision-Oriented Risk Analysis:** Explore how probability thresholds can be selected in relation to lending policies, default costs, and risk tolerance.

## Technologies and Tools

| Category | Tools |
|---|---|
| Programming Language | Python |
| Bayesian Modeling | PyMC |
| Bayesian Analysis | ArviZ |
| Data Manipulation | Pandas, NumPy |
| Machine Learning and Preprocessing | Scikit-learn |
| Data Visualization | Matplotlib, Seaborn |
| Development Environment | Google Colab |


## Conclusion

This project demonstrates the application of Bayesian Logistic Regression to credit risk assessment using borrower-level financial and demographic information. By combining Bayesian inference, MCMC-based posterior estimation, probability-based risk segmentation, and classification evaluation, it provides a practical framework for exploring probabilistic approaches to borrower default assessment.

The project also highlights the importance of distinguishing estimated default probabilities from the uncertainty associated with those estimates, as well as the need for appropriate validation before applying predictive models to real-world lending decisions.
