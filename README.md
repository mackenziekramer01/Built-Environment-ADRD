# The role of built and social environments in Alzheimer's disease dementia prevalence in the United States: A machine learning approach

## Background  
This repository contains the machine learning analysis used my publication examining how built and social environments predict county-level Alzheimer’s disease dementia prevalence across the United States.
* Journal of Alzheimer's Disease
* Year of Publication: 2025
* [Link to Paper](https://journals.sagepub.com/doi/epub/10.1177/13872877251372144)
* **Code for analysis can be found in:**
  * /AD-Dementia-Research(BEandSVI).ipynb

## Research Questions  
1. How well can built environment (BE) variables alone predict AD dementia prevalence?
2. How much does model performance improve when adding social vulnerability (SVI) variables?
3. Which variables are most influential nationally and regionally?
4. Do predictors differ across U.S. Census regions (Northeast, Midwest, South, West)?

## Data Overview
**Response Variable**
* Alzheimer’s Disease Dementia Prevalence
* Source: Dhana et al. (2020)

**Built Environment (BE) Variables**
* 5D framework (Density, Diversity, Design, Destination, and Distance to Transit)
* Sources: EPA Smart Location Database, USDA Food Environment Atlas, Homeland Infrastructure Foundation-Level Data (HIFLD)

**Social Vulnerability Index (SVI)**
* E.g., Poverty (%), Unemployment (%), Per capita income, No vehicle (%)
* Source: CDC/ATSDR

## Exploratory Analysis
* ANOVA tests identified significant regional differences in AD dementia prevalence
* Tukey’s HSD tests confirmed most regional pairs differed significantly
* Multicollinearity was assessed using:
  * Variance Inflation Factor (VIF < 5)
  * Pairwise correlation (|r| < 0.75)
* Final model retained 15 predictors.

## Model Selection
Two tree-based ensemble models were implemented:

**Random Forest**
* Implemented with scikit-learn
* Handles nonlinear relationships and feature interactions
* Ensemble averaging reduces overfitting

**eXtreme Gradient Boosting (XGBoost)**
* Implemented with xgboost
* Sequential boosting approach
* Regularization and early stopping
* Consistently outperformed RF regionally

## Model Configuration
**Train/Validation/Test Split:**
* 70% training
* 15% validation
* 15% test

**Hyperparameter tuning:**
* Grid search
* 5-fold cross-validation
* Evaluation metric: RMSE

**Performance Metrics**
* R²
* RMSE
* MAE
* AIC

## Key Results
**National Model**
* XGBoost: R² = 0.51
* RF: R² = 0.50

**Regional Models**
* Northeast: R² = 0.92
* South: R² = 0.73
* Midwest: R² = 0.72
* West: R² = 0.72

**Key Takeaways**
* Built environment variables were most predictive in the Northeast
* Social vulnerability variables were dominant in the South
* Midwest and West showed balanced influence of BE and SVI
* Grocery store density and walkability were strong BE predictors
* No-vehicle %, uninsured %, and single-parent households were strong SVI predictors

## Contact
Please contact Mackenzie Kramer on any questions regarding this paper or analysis.  
Data may be made available upon request.
