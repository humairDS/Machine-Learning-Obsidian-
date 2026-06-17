```python 
from sklearn.ensemble import AdaBoostClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.tree import DecisionTreeClassifier

# Sample data
X = [
    [22, 25],
    [25, 30],
    [47, 80],
    [52, 110],
    [46, 90],
    [23, 20]
]

y = [0, 0, 1, 1, 1, 0]

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Weak learner (decision stump)
base_model = DecisionTreeClassifier(max_depth=1)

# AdaBoost model
model = AdaBoostClassifier(
    estimator=base_model,
    n_estimators=50,
    learning_rate=1.0
)

# Train
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)

# Accuracy
print("Accuracy:", accuracy_score(y_test, predictions))
```


# Understanding the Code

## Weak Model

```
DecisionTreeClassifier(max_depth=1)
```

This is a **decision stump**.

---

## AdaBoost Model

```
AdaBoostClassifier(n_estimators=50)
```

Means:

- Create 50 weak models
- Combine them

---

# Important Parameters

## n_estimators

Number of weak learners.

```
n_estimators=100
```

More models → better performance (but slower)

---

## learning_rate

Controls contribution of each model.

```
learning_rate=0.1
```

- High learning rate → faster learning, risk overfitting
- Low learning rate → slower but stable

