# AP Exam Score Analysis

This project explores the relationship between AP Calculus AB exam scores and academic indicators using multiple linear regression, ordinal logistic regression, and cross-validation techniques.

## Objective

- Predict AP Calculus AB exam scores based on course grade, PSAT, gender, GPA, and rank
- Investigate whether classroom performance aligns with AP exam outcomes
- Evaluate model performance and validity

## Data Overview

- Sample size: 71 students (graduating classes 2019–2022)
- Predictors: Final course grade, PSAT Math score, gender, relative GPA, relative rank
- Target: AP score (2–5; ordinal)

> **Note:** Dataset is private due to identifiable student information and cannot be shared.

## Modeling Techniques

### Multiple Linear Regression (MLR)
- Optimal model (Adj. R² = 0.5754) included:
  - Course Grade (β = 0.090, *p* < 0.001)
  - PSAT (β = 0.004, *p* = 0.023)
  - Gender (β = 0.483, *p* = 0.006)
  - Relative GPA (β = 4.764, *p* = 0.008)
- Diagnostics:
  - Shapiro-Wilk test: *p* = 0.325 (normality supported)
  - Breusch-Pagan test: *p* = 0.169 (homoscedasticity supported)

### Ordinal Logistic Regression (OLR)
- Optimal model included same predictors as MLR
- All coefficients significant (*p* < 0.002)
- Brant test: Proportional odds assumption upheld (*p* = 1.000)

### Cross-Validation
- 10-fold CV tested 5 link functions
- **Best performing model:** Probit link, accuracy ≈ 71%

## Key Skills Demonstrated

- R (tidyverse, MASS, polr, caret)
- Regression modeling (MLR, OLR)
- Model selection (best subset, AIC)
- Multicollinearity checks (VIF)
- Influence diagnostics (Cook’s D, DFFITS, COVRATIO)
- Cross-validation with ordinal models

## Files

- `code/` – RMarkdown analysis script
- `report/` – Final project write-up (PDF)
- `data/` – *Not included due to privacy concerns*

## Future Considerations

- Explore additional predictors (e.g., effort, math GPA, activities)
- Test models on data split by GPA scale (4.3 vs. 6.0 max)
- Incorporate multiple imputation for missing PSATs

