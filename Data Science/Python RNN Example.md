```python 
from tensorflow.keras.models import Sequential 
from tensorflow.keras.layers import SimpleRNN,Dense

model = Sequential([
	SimpleRNN(50,input_shape=(100,1)),
	Dense(1)
])
```

### Simple Definition

**A Recurrent Neural Network (RNN) is a deep learning model that processes sequential data by maintaining a memory of previous inputs, making it useful for text, speech, and time-series prediction tasks.**

