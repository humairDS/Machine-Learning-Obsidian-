
A **Random Forest** is an ensemble Machine Learning algorithm that combines **many Decision Trees** together.


***Simple Idea***:
Decision Tree = One person's opinion
Random Forest = Opinions from many experts


### Why "Random" Forest?
Two Randomness Techniques are used:
**1. Random Data Sampling (Bootstrap)
	Each tree gets random parts of the dataset.

**2. Random Feature Selection
	Each tree sees random features.

This makes trees different from each other.


# Real-Life Example

Imagine a hospital diagnosing a disease.

Instead of asking **one doctor**, the hospital asks **100 doctors**.

If most doctors say:

- Disease = Yes → Final answer = Yes
- Disease = No → Final answer = No

That is Random Forest.


## Classification Example

Tree 1 → Cat
Tree 2 → Dog
Tree 3 → Dog
Tree 4 → Dog

Final Prediction = Dog

## Regression Example 

Tree predictions:
100
110
120
130

Final Prediction:
(100 + 110 + 120 + 130) / 4 = 115


## [[Random Forest Python Example]]


**Dataset**

| Age | Salary | Bought |
| --- | ------ | ------ |
| 22  | 25     | 0      |
| 25  | 30     | 0      |
| 47  | 80     | 1      |
| 52  | 110    | 1      |

```python 
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

X = [  
[22, 25],  
[25, 30],  
[47, 80],  
[52, 110],  
[46, 90],  
[23, 20]  
]

y = [0, 0, 1, 1, 1, 0]

#split data
X_train, X_test, y_train, y_test = train_test_split(  
X, y, test_size=0.2, random_state=42
)

#create model
model = RandomForestClassifier(  
	n_estimators=100,  
	random_state=42
)

#Train Model 
model.fit(X_train, y_train)

#Precition
predictions = model.predict(X_test)

#accuracy 
print("Accuracy:", accuracy_score(y_test, predictions))
```

# Understanding the Code

## Create Random Forest

```python
RandomForestClassifier(n_estimators=100)
```

Means:
- Build 100 decision trees

---

## Train Model

```python
model.fit(X_train, y_train)
```

Trees learn from random data samples.

---

## Predict

```python 
model.predict(X_test)
```

All trees vote together.

---

# Regression Example

Predict house prices.

```python 
from sklearn.ensemble import RandomForestRegressor
X = [[1000], [1500], [2000], [2500]]
y = [10, 15, 20, 25]

model = RandomForestRegressor(
	n_estimators=100,
	random_state=42
)
model.fit(X, y)

prediction = model.predict([[1800]])

print(prediction)
```

---

# Important Hyperparameters

## n_estimators

Number of trees.

```
RandomForestClassifier(n_estimators=200)
```

More trees:

- Better performance
- More computation

---

## max_depth

Maximum depth of each tree.

```
RandomForestClassifier(max_depth=5)
```

Controls overfitting.

---

## max_features

How many features each tree can use.

```
RandomForestClassifier(max_features="sqrt")
```

Adds randomness.

---

# Feature Importance

Random Forest can tell which features are most important.

Example:

```
print(model.feature_importances_)
```

Output:

```
[0.30, 0.70]
```

Meaning:

- Salary influences prediction more than age.

---
