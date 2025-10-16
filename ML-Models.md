# ML Models Recap

Quick summaries of core machine learning algorithms — for fast revision before interviews.

---

## K-Nearest Neighbors (KNN)

### Overview
KNN is a supervised learning algorithm used for classification and regression.  
It predicts based on the majority vote (classification) or average (regression) of the K nearest data points.

### How It Works
1. Choose a value for K.  
2. Calculate the distance between the new point and all training points.  
3. Pick the K closest points.  
4. Predict based on the majority label (or average for regression).

### Key Notes
- No training phase → "lazy learner."  
- Common distance metrics: Euclidean, Manhattan.  
- Small K → may overfit.  
- Large K → may underfit.  
- Sensitive to feature scaling → use normalization.

### Pros and Cons

| Pros | Cons |
|------|------|
| Simple and intuitive | Slow with large datasets |
| Non-parametric (no assumptions about data) | Affected by irrelevant features |
| Works for multi-class classification | Struggles in high-dimensional spaces |

### Quick Code Example
```python
from sklearn.neighbors import KNeighborsClassifier
model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)
model.score(X_test, y_test)
```


## Linear Regression

### Overview
Linear Regression is a supervised learning algorithm used for predicting continuous values.  
It finds the best-fit line that minimizes the difference between actual and predicted values.

### How It Works
1. Assume the relationship between features (X) and target (y) is linear:  
   y = β₀ + β₁x₁ + β₂x₂ + ... + βₙxₙ  
2. Find the coefficients (β) that minimize the Mean Squared Error (MSE).  
3. Use the equation to predict new values.

### Key Notes
- Goal: minimize **MSE = (1/n) Σ(yᵢ - ŷᵢ)²**  
- Assumes a **linear relationship** between input and output.  
- Sensitive to **outliers**.  
- Works best when features are **independent** and **normally distributed**.  
- Can be extended to **Multiple Linear Regression** (more than one feature).

### Pros and Cons

| Pros | Cons |
|------|------|
| Simple and interpretable | Assumes linearity |
| Fast to train and predict | Sensitive to outliers |
| Works well on small datasets | Poor with multicollinearity |
| Provides feature importance | May underfit complex data |

### Quick Code Example
```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

model = LinearRegression()
model.fit(X_train, y_train)

preds = model.predict(X_test)
mse = mean_squared_error(y_test, preds)
print("MSE:", mse)
```