```python 
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import LSTM, Dense

model = Sequential([
    LSTM(50, input_shape=(100, 1)),
    Dense(1)
])

model.summary()
```



### One-Line Definition

**LSTM (Long Short-Term Memory) is an advanced type of RNN that uses gates and a memory cell to learn and remember important information over long sequences of data.**

