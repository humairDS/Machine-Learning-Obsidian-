| Age | Salary | Bought |
| --- | ------ | ------ |
| 22  | 25     | 0      |
| 25  | 30     | 0      |
| 47  | 80     | 1      |
| 52  | 110    | 1      |
```python 
from sklearn.neighbors import KNeighborsClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.preprocessing import StandardScaler

# Features
X = [
    [22, 25],
    [25, 30],
    [47, 80],
    [52, 110],
    [46, 90],
    [23, 20]
]

# Labels
y = [0, 0, 1, 1, 1, 0]

# Feature Scaling
scaler = StandardScaler()
X = scaler.fit_transform(X)

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Create model
model = KNeighborsClassifier(n_neighbors=3)

# Train
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)

# Accuracy
print("Accuracy:", accuracy_score(y_test, predictions))
```


## Understanding the Code

# Create KNN
```python
KNeighborsClassifier(n_neighbors=3)
```
Means:
- Use 3 nearest neighbors.

# Feature Scaling is Important
KNN depends on distance.
If features have different scales:
```python
Age = 20
Salary = 100000
```
Salary dominates distance.

So scaling is necessary.


# Regression Example

```python
from sklearn.neighbors import KNeighborsRegressor

X = [[1], [2], [3], [4]]
y = [10, 20, 30, 40]

model = KNeighborsRegressor(n_neighbors=2)

model.fit(X, y)

prediction = model.predict([[2.5]])

print(prediction)
```

# Important Hyperparameters

## n_neighbors

Number of neighbors.
```python 
KNeighborsClassifier(n_neighbors=5)
```

## metric

Distance calculation method.
```python 
KNeighborsClassifier(metric='euclidean')
```

Other options:

- Manhattan
- Minkowski