# Hands on III – COVID-19 Severity Prediction using Machine Learning

This repository contains the analysis for **Hands on III (DMI course)**.  
The objective of this project is to reproduce and evaluate a machine learning pipeline to predict COVID-19 severity using proteomic and metabolomic data.

The analysis is based on the dataset from the publication:  
**Proteomic and Metabolomic Characterization of COVID-19 Patient Sera**  
Shen et al., Cell (2020)

---

# Objective

The main goal of this assignment is to:

- Build a predictive model to classify patients into **Severe vs non-Severe**
- Evaluate model performance using **cross-validation (C1 cohort)**
- Perform **external validation (C2 cohort)**
- Compare results with the original publication
- Interpret model predictions at both global and patient level

---

# Methodology

## Data preprocessing

- Integration of **proteomics and metabolomics data**
- Feature selection and harmonization across cohorts
- Handling of missing values:
  - Metabolites → imputed with minimum observed value
  - Other features → imputed with zero
- Separation into:
  - **C1 (training cohort)**
  - **C2 (external validation cohort)**

---

## Model

- Algorithm: **Random Forest classifier**
- Training performed on **baseline samples (C1)**
- Hyperparameter tuning via cross-validation
- Output:
  - Class prediction (Severe / nonSevere)
  - Probability of Severe

---

## Evaluation

### Internal validation (C1)

- Cross-validation
- Metrics:
  - Accuracy
  - Sensitivity / Specificity
  - ROC curve and AUC

---

### External validation (C2)

- Independent test set evaluation
- Confusion matrix
- ROC curve and AUC
- Patient-level probability analysis

---

## Patient-level interpretation

Beyond global performance metrics, predictions are analyzed at the individual level:

- Visualization of predicted probabilities
- Identification of:
  - Correct classifications
  - Misclassified patients
  - Borderline cases (close to decision threshold)

This provides insight into model confidence and potential clinical applicability.

---

# Report

The full analysis report is available here:  

➡ **[Hands_on_III.html](Hands_on_III.html)**

The report includes:

- Data preprocessing and feature engineering
- Model training and validation
- ROC analysis and performance metrics
- External validation on C2
- Patient-level prediction visualization
- Interpretation of results

The report is fully reproducible and contains all figures.

---

# Reproducibility

To reproduce the analysis:

1. Open:

    Hands_on_III.Rmd

2. Run all chunks in order

Required environment:

- R (≥ 4.x)
- Packages:
  - caret
  - randomForest
  - pROC
  - dplyr
  - ggplot2 (optional)

---

# Key Results

- The model is able to distinguish **Severe vs non-Severe patients**
- External validation (C2) provides a realistic estimate of performance
- Misclassified cases tend to have probabilities close to the decision threshold
- Patient-level visualization reveals model confidence patterns

---

# Discussion

This work reproduces a simplified version of the predictive approach described in the original study.  
While performance is consistent with expectations, several limitations should be considered:

- Potential influence of **cohort-specific effects**
- Lack of adjustment for **clinical covariates**
- Possible confounding due to **cellular composition**

Future improvements could include:

- Cell type deconvolution
- Multi-omics integration strategies
- More robust feature selection

---

# Authors

Regina Rodriguez Durant Reyes (regina.rodriguezdurant01@estudiant.upf.edu) and Domenica Arlet Teller Guardián (domenicaarlet.teller01@estudiant.upf.edu)