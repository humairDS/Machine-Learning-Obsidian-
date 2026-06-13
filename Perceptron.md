A **Perceptron** is the simplest neural network consisting of a single artificial neuron.

It was introduced by Frank Rosenblatt in 1958.

### Example: Pass or Fail

Inputs:

- Study Hours = 8
- Attendance = 90%

Output:

```
1 = Pass
0 = Fail
```

The perceptron learns which factors are more important and adjusts weights accordingly.

### Working

```
Inputs 
  ↓
Weighted Sum
   ↓
Activation Function
   ↓
Output
```


### Limitation

A single perceptron can solve only **linearly separable problems**.

Example:

✅ AND Gate

❌ XOR Gate

This limitation led to Multi-Layer Neural Networks.