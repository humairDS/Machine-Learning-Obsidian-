|Age|Salary|Bought|
|---|---|---|
|22|25|0|
|25|30|0|
|47|80|1|
|52|110|1|
```python 
from sklearn.tree import DecisionTreeClassifier
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
model = DecisionTreeClassifier()

# Train model
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)

# Accuracy
print("Accuracy:", accuracy_score(y_test, predictions))
```



# Understand the Code


***Create Model***
```python 
model = DecisionTreeClassifier()
```

***Train Model***
```python 
model.fit(X_train,y_train)
```

***Prediction***
```python
model.predict(X_test)
```

***Visualize Decision Tree***
```python 
from sklearn.tree import plot_tree
import matplotlib.pyplot as plt 

plt.figure(figsize=(10,6))
plot_tree(model,filled=True)
plt.show()
```

***Regression Example***

Prediction House Price
```python 
from sklearn.tree import DecisionTreeRegressor

X = [[1000], [1500], [2000], [2500]]
y = [10, 15, 20, 25]

model = DecisionTreeRegressor()
model.fit(X, y)

prediction = model.predict([[1800]])

print(prediction)
```


### Important Hyperparameters

***max_depth***
```python
DecisionTreeClassifier(max_depth=3)
```
Prevents Overfitting
***

**min_samples_split**
```python
DecisionTreeClassifier(min_samples_split=5)
```
Minimum samples needed to split
***

***criterion***

```python 
DecisionTreeClassifier(criterion="gini")
```
or
```python 
DecisionTreeClassifier(criterion="entropy")
```

