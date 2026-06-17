```python 
import pandas as pd

df = pd.read_csv("adult.csv")

print(df.head())
```

```python 
print(df.info())
print(df.isnull().sum())
```

```python 
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df["gender"] = le.fit_transform(df["gender"])
```

```python 
X = df.drop("income", axis=1)
y = df["income"]
```

```python 
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

```python 
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()

model.fit(X_train, y_train)
```

```python 
predictions = model.predict(X_test)
```

```python 
from sklearn.metrics import accuracy_score

print(
    accuracy_score(
        y_test,
        predictions
    )
)
```
