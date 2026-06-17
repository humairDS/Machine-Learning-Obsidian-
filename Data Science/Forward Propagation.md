# Forward Propagation in ANN

**Forward Propagation** is the process where data moves from the **input layer → hidden layers → output layer** to produce a prediction.

In simple words:

> Forward propagation is how a neural network makes a prediction.

---

## 🏗️ Step-by-Step Process

Suppose we have:

- Input: (x)
    
- Weight: (w)
    
- Bias: (b)
    

The neuron computes:

z = wx + b

Then applies an activation function:

```
a = f(z)
```

Where:
- (z) = weighted sum
- (a)= output after activation
---

## Example

Let's say:

- Input (x = 2)
- Weight (w = 3)
- Bias(b = 1)

### Step 1: Calculate weighted sum

z=(2×3)+1=7

### Step 2: Apply activation

Using ReLU:

ReLU(z)=max(0,z)  

Since (z=7),

a=7  

### Step 3: Pass to next layer

This output becomes the input for the next neuron or the final output layer.

---

## Visual Flow

```text
Input
  │
  ▼
Weighted Sum (wx+b)
  │
  ▼
Activation Function
  │
  ▼
Output
```

For a full ANN:

```text
Input Layer
     │
     ▼
Hidden Layer(s)
     │
     ▼
Output Layer
```

All of this movement from left to right is **forward propagation**.

---

## Why is it Called "Forward"?

Because information moves:

```text
Input → Hidden Layer → Output
```

The opposite direction:

```text
Output → Hidden Layer → Input
```

is **Backpropagation**, where gradients flow backward to update weights.

---

## Real-Life Example

Imagine predicting whether a student will pass.

Inputs:

- Study Hours = 8
    
- Attendance = 90%
    
- Sleep = 7 hours
    

Forward propagation:

1. Inputs enter the network.
2. Hidden layers process patterns.
3. Output layer predicts:
    

```text
Pass Probability = 92%
```

This prediction is the result of forward propagation.

---

## Exam Definition

> Forward propagation is the process of passing input data through the layers of a neural network to compute the output prediction using weights, biases, and activation functions.

---

### ANN Training Cycle

```text
1. Forward Propagation
       ↓
2. Calculate Loss
       ↓
3. Backpropagation
       ↓
4. Gradient Descent
       ↓
5. Update Weights
       ↓
Repeat (Epochs)
```

This complete cycle is how an ANN learns from data.