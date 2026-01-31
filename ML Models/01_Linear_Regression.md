# Linear Regression — Quick Interview Summary

## 1. What is Linear Regression?
Linear regression is a method to model the relationship between:
- **Independent variable(s) (X)** → input
- **Dependent variable (Y)** → output

Goal:  
Find a straight line that best predicts **Y** from **X**.

---

## 2. Simple Linear Regression Model

\[
y = \beta_0 + \beta_1 x + \error
\]

Where:
- \(y\) = predicted value
- \(x\) = input feature
- \(\beta_0\) = intercept (value of y when x = 0)
- \(\beta_1\) = slope (change in y for 1 unit change in x)
- \(\error\) = error term

---

## 3. Example

**Problem:** Predict exam score based on study hours.

| Hours Studied (x) | Score (y) |
|------------------|----------|
| 1 | 45 |
| 2 | 50 |
| 3 | 55 |
| 4 | 60 |

**Model:**
\[
y = 40 + 5x
\]

**Interpretation:**
- Each extra hour of study increases the score by **5 points**
- If a student studies 3 hours:
\[
y = 40 + 5(3) = 55
\]

---

## 4. How the Best Line is Found
Linear regression uses **Ordinary Least Squares (OLS)**.

OLS minimizes:
\[
\sum (y_i - \hat{y}_i)^2
\]

This means:
- Find the line with the **smallest total squared errors**

---

## 5. Residuals
\[
\text{Residual} = y - \hat{y}
\]

- Difference between actual and predicted value
- Good model → residuals are small and random

---

## 6. Key Assumptions (VERY IMPORTANT)

1. **Linearity**  
   Relationship between X and Y is linear

2. **Independence**  
   Observations are independent

3. **Homoscedasticity**  
   Constant variance of residuals

4. **Normality of Errors**  
   Residuals are normally distributed

5. **No Multicollinearity** (for multiple regression)  
   Predictors should not be highly correlated

---

## 7. Multiple Linear Regression

\[
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \dots + \error
\]

**Example:**
\[
\text{Score} = 30 + 4(\text{study hours}) + 2(\text{sleep hours})
\]

Interpretation:
- +1 hour study → +4 score points (keeping sleep constant)
- +1 hour sleep → +2 score points (keeping study constant)

---

## 8. Model Evaluation

### R-squared (\(R^2\))
- Measures how much variance in Y is explained by X
- Example: \(R^2 = 0.80\) → 80% explained

### Adjusted R-squared
- Penalizes unnecessary predictors
- Better for comparing models

---

## 9. Hypothesis Testing

**Null Hypothesis:**
\[
H_0: \beta = 0
\]

- Small p-value (< 0.05) → predictor is significant
- Large p-value → predictor is not useful

---

## 10. Common Interview Pitfalls

- Regression shows **correlation, not causation**
- Avoid extrapolating beyond data range
- Always check residual plots

---

## 11. One-Line Interview Explanation
> “Linear regression finds the straight line that best predicts the target variable by minimizing squared prediction errors.”

