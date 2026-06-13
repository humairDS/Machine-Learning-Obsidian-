- [[Biological Neuron]]
- [[Artificial Neuron]]
- [[Perceptron]]
- [[Weights]]
- [[Bias]]
- [[Activation Functions]]


# Complete Flow of a Neuron 
```
Inputs
x1, x2, x3
      ↓
Multiply by Weights
      ↓
Weighted Sum
      ↓
Add Bias
      ↓
Activation Function
      ↓
Output
```


Mathematically:

```
Output=f((x1​w1​+x2​w2​+x3​w3​)+b)
```



Important Interview Questions
### Q1. Why do we need weights?

Weights determine the importance of each feature.

### Q2. Why do we need bias?

Bias allows the model to shift the decision boundary and learn more flexible patterns.

### Q3. What is a perceptron?

A single artificial neuron used for binary classification.

### Q4. Which activation function is most commonly used today?

**ReLU**.

### Q5. Why can't we use only linear functions?

Multiple linear layers still behave like one linear function, making it impossible to learn complex patterns.