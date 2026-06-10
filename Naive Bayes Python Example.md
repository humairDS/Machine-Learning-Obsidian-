Classification:
```python 
from sklearn.naive_bayes import GaussianNB
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Features
X = [
    [1, 20],
    [2, 21],
    [8, 90],
    [9, 85],
    [7, 88],
    [1, 18]
]

# Labels
# 0 = Not Spam
# 1 = Spam
y = [0, 0, 1, 1, 1, 0]

# Split data
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Create model
model = GaussianNB()

# Train
model.fit(X_train, y_train)

# Predict
predictions = model.predict(X_test)

# Accuracy
print("Accuracy:", accuracy_score(y_test, predictions))
```



Text Classification Example

```python
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

texts = [
    "Win money now",
    "Free lottery ticket",
    "Meeting tomorrow",
    "Project discussion"
]

labels = [1, 1, 0, 0]

vectorizer = CountVectorizer()
X = vectorizer.fit_transform(texts)

model = MultinomialNB()
model.fit(X, labels)

test = vectorizer.transform(["Free money"])

print(model.predict(test))
```
