| Age | Salary | Bought |
| --- | ------ | ------ |
| 22  | 25     | 0      |
| 25  | 30     | 0      |
| 47  | 80     | 1      |
| 52  | 110    | 1      |


```python 
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

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

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Create model
model = SVC(kernel='linear')

# Train model
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)

# Accuracy
print("Accuracy:", accuracy_score(y_test, predictions))
```

## Understanding the Code

## Create SVM

```python
SVC(kernel='linear')
```

This creates:

- Support Vector Classifier
- Using linear kernel

---

# Different Kernels

## Linear Kernel

```python
SVC(kernel='linear')
```

Straight-line separation.

---

## RBF Kernel

```python
SVC(kernel='rbf')
```

Most commonly used.

Handles nonlinear data.

---

## Polynomial Kernel

```python
SVC(kernel='poly')
```

Curved boundaries.

---

# Important Hyperparameters

## C Parameter

Controls balance between:

- Correct classification
- Margin size

```python
SVC(C=1)
```

### Small C

- Wider margin
- More tolerance for mistakes

### Large C

- Tries to classify everything correctly
- May overfit

---

# Gamma Parameter (RBF)

Controls influence of points.

```python
SVC(gamma='scale')
```

High gamma:

- Complex boundaries
- Risk of overfitting

Low gamma:

- Simpler boundaries

---

# Feature Scaling is Important

SVM is sensitive to feature scales.

Always use scaling.

Example:

```python
from sklearn.preprocessing import StandardScalerscaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

---

# Real-World Uses

- Face detection
- Handwriting recognition
- Spam filtering
- Bioinformatics
- Image classification