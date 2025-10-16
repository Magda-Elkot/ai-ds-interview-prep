# K-Nearest Neighbors (KNN)

## Overview
KNN is a supervised learning algorithm used for classification and regression.  
It predicts based on the majority vote (classification) or average (regression) of the K nearest data points.

---

## How It Works
1. Choose a value for K.  
2. Calculate the distance between the new point and all training points.  
3. Pick the K closest points.  
4. Predict based on the majority label (or average for regression).

---

## Key Notes
- No training phase → "lazy learner."  
- Common distance metrics: Euclidean, Manhattan.  
- Small K → may overfit.  
- Large K → may underfit.  
- Sensitive to feature scaling → use normalization.

---

## Pros and Cons

| Pros | Cons |
|------|------|
| Simple and intuitive | Slow with large datasets |
| Non-parametric (no assumptions about data) | Affected by irrelevant features |
| Works for multi-class classification | Struggles in high-dimensional spaces |

---

## Quick Code Example
```python
from sklearn.neighbors import KNeighborsClassifier
model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)
model.score(X_test, y_test)
