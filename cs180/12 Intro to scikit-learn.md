Daily Note: [[2023-03-23]] -- [*created*:: 2023-03-23] #cs180 

*Designed to be easy, fast, flexible, and is commonly used for the end-to-end life cycle*

# Some Basic Components:

## Data

Interacts with numpy, pandas, matplotlib

## Preprocessing

Lots of built-ins for preprocessing

## Train/Test Split

Built-ins to split data, k-fold cross validation

## Models

OOP API for models

- clustering 
- classification
- regression
- dimensionality reduction
- ++

## Evaluation

- metrics, tools, pipelines to evaluate performance

---

```python
knn = KNeighborsClassifier(n_neighbors=k)
knn.fit(X=, y=)
knn_predictions = knn.predict(X=)
knn_probabilities = knn.predict_proba(X=)
```
