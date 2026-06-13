```python 
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
    Dense(16, activation='relu', input_shape=(3,)),
    Dense(8, activation='relu'),
    Dense(4, activation='relu'),
    Dense(1)
])

model.compile(
    optimizer='adam',
    loss='mse',
    metrics=['mae']
)

model.summary()
```

Here:

- Input features = 3
- Hidden Layer 1 = 16 neurons
- Hidden Layer 2 = 8 neurons
- Hidden Layer 3 = 4 neurons
- Output Layer = 1 neuron

This is a **Deep Neural Network** because it has **3 hidden layers**.
