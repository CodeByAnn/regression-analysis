## Summary

This project focuses on fitting and evaluating regression models using synthetic datasets to understand the impact of data transformation and outliers. A logarithmic model is first applied to a simple dataset to assess goodness-of-fit using visualizations and statistical metrics. In the second part, multiple linear regression approaches are tested on multivariate data with and without outliers to compare performance across different modeling techniques.

---

### Dataset Overview

- **Dataset 1:** 50 observations with variables `x` and `y`, showing a nonlinear relationship
- **Dataset 2:** 800 rows, 3 input features (`x1`, `x2`, `x3`) and 1 target (`y`)
- Dataset 2 includes artificially inserted **outliers** in all features
- Models compared using standard regression evaluation metrics (RSS, R², MAE)

---

### Key Steps

### 1. **Logarithmic Regression**

- Transformed `x` into `log(x)` to linearize the relationship with `y`
- Fitted a first-degree polynomial model on the log-transformed data
- Visualized model predictions against original data using scatter and line plots
- Achieved **R² = 0.94** and **RSS = 31.84**, showing a strong model fit

### 2. **Multivariate Regression with Outliers**

- Used 800-row dataset with three features to predict a continuous target
- Visualized each feature’s relationship with the target to detect trends
- Split the data into training (80%) and testing (20%) sets
- Fitted two models: standard Linear Regression and Huber Regression
- Observed high MAE for linear regression (**104.8**) due to presence of outliers

### 3. **Cleaning and Model Comparison**

- Defined valid value ranges for each feature and removed outliers
- Reduced training dataset from 800 to 746 rows
- Re-trained linear regression on cleaned data
- Compared MAE across all three models:
    - **Linear with outliers:** 104.8
    - **Huber with outliers:** 83.9
    - **Linear without outliers:** 70.6

---

### Observations

- Logarithmic regression effectively captured the nonlinear relationship in Dataset 1
- Outliers had a significant negative impact on model accuracy
- Huber Regression improved performance by reducing sensitivity to outliers
- Removing outliers manually produced the best model performance
- Visualizations played a key role in identifying feature relationships and data issues

---

### Conclusion

This project highlights the importance of **data transformation**, **outlier handling** and **model selection** in regression tasks. Applying logarithmic transformation enabled linear modeling of a nonlinear trend, while robust techniques like Huber regression and data cleaning significantly improved predictive performance in multivariate settings. The step-by-step comparison of methods provides practical insights into building more reliable regression models.
