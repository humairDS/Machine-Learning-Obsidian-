We’ll build something industry-style using real dataset concepts:

# 🏠 Project: House Price Prediction using ANN (Regression)

You’ll learn:

- real data handling
- multi-layer ANN
- ReLU activation
- proper training + evaluation

We’ll use:  
TensorFlow + Keras in Google Colab


# Step 1: Importing Libraries 
```python 
import tensorflow as tf
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
```

# Step 2: Create an Simple Dataset
```python 
# Features: [size, bedrooms]
X = np.array([
    [1000, 2],
    [1500, 3],
    [2000, 3],
    [2500, 4],
    [3000, 4],
    [3500, 5]
])

# Prices
y = np.array([200, 300, 400, 500, 600, 700])
```

# Step 3: Train Test Split
```python 
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

# Step 4: Feature Scaling 
```python 
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

#Note : ANN Works better when data is scaled


# Step 5: Build ANN Model 
```python 
model = tf.keras.Sequentical([
	tf.keras.layers.Dense(8,activation='relu',input_shape=[2]),
	tf.keras.layers.Dense(4,activation='relu'),
	tf.keras.layers.Dense(1)
])
```

explanation:
- Input: 2 features (size, bedrooms)
- Hidden layers: ReLU
- Output: price

# Step 6: Compile Model 
```python 
model.compile(
    optimizer='adam',
    loss='mean_squared_error'
)
```

# Step 7: Train Model 
```python 
model.fit(X_train, y_train, epochs=200, verbose=0)
```

# Step 8: Make Prediction 
```python 
sample = scaler.transform([[2000, 3]])
prediction = model.predict(sample)

print(prediction)
```




