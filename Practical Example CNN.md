
# CNN Practical Example (MNIST Digit Classifier)

##  Step 1: Install & Import Libraries

```python
import tensorflow as tf
from tensorflow.keras import layers, models
import matplotlib.pyplot as plt
```

---

##  Step 2: Load Dataset

MNIST is built into Keras.

```python
mnist = tf.keras.datasets.mnist

(x_train, y_train), (x_test, y_test) = mnist.load_data()
```

---

## Step 3: Preprocess Data

CNN needs images in this format:  
**(height, width, channels)** → so we reshape.

```python
x_train = x_train.reshape(-1, 28, 28, 1)
x_test = x_test.reshape(-1, 28, 28, 1)

# Normalize (0–255 → 0–1)
x_train = x_train / 255.0
x_test = x_test / 255.0
```

---

##  Step 4: Build CNN Model

```python
model = models.Sequential([
    
    # Convolution Layer
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    
    # Pooling Layer
    layers.MaxPooling2D((2,2)),
    
    # Second Convolution Layer
    layers.Conv2D(64, (3,3), activation='relu'),
    layers.MaxPooling2D((2,2)),
    
    # Flatten
    layers.Flatten(),
    
    # Fully Connected Layer
    layers.Dense(64, activation='relu'),
    
    # Output Layer (10 classes)
    layers.Dense(10, activation='softmax')
])
```

---

##  Step 5: Compile Model

```python
model.compile(
    optimizer='adam',
    loss='sparse_categorical_crossentropy',
    metrics=['accuracy']
)
```

---

##  Step 6: Train Model

```python
model.fit(x_train, y_train, epochs=5, validation_data=(x_test, y_test))
```

---

##  Step 7: Evaluate Model

```python
test_loss, test_acc = model.evaluate(x_test, y_test)
print("Test Accuracy:", test_acc)
```

---

##  Step 8: Make Predictions

```python
import numpy as np

predictions = model.predict(x_test)

# Show first prediction
print("Predicted:", np.argmax(predictions[0]))
print("Actual:", y_test[0])
```

---

# What you just built

You created a full CNN pipeline:

- Input image (28×28 digit)
- Feature extraction (Conv layers)
- Compression (Pooling)
- Classification (Dense layers)
- Output (digit 0–9)


# 📊 Expected Result

After 5 epochs, you should get:
- Accuracy: **~98%+** 🎯
