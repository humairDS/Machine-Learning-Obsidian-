# Loss Function in ANN

A **Loss Function** measures **how wrong the neural network's prediction is** compared to the actual answer.

In simple words:
> Loss Function = "Mistake Calculator" of the neural network.

---

## Why Do We Need It?

After forward propagation, the ANN makes a prediction.

Example:

- Actual value = 100
- Predicted value = 80

The network needs a way to know:
> "How bad is this prediction?"
That's the job of the loss function.

---

## How It Fits in ANN

```text
Input
  ↓
Forward Propagation
  ↓
Prediction
  ↓
Loss Function
  ↓
Error
  ↓
Backpropagation
  ↓
Update Weights
```

---

## Example

Suppose:

- Actual House Price = 500,000
    
- Predicted House Price = 450,000
    

Error:

[  
500000 - 450000 = 50000  
]

The loss function converts this error into a numerical value that the model tries to minimize.

---

# Common Loss Functions

## 1. Mean Squared Error (MSE)

Used for **Regression Problems**.

Examples:

- House price prediction
    
- Salary prediction
    
- Temperature forecasting
    

Formula:

MSE = \frac{1}{n}\sum (y-\hat{y})^2

Where:

- (y) = actual value
    
- (\hat{y}) = predicted value
    

### Why square the error?

- Makes all errors positive
    
- Penalizes large mistakes more heavily
    

---

## 2. Binary Cross-Entropy

Used for **Binary Classification**.

Examples:

- Spam / Not Spam
    
- Pass / Fail
    
- Disease / No Disease
    

Formula:

[  
L = -\left(y\log(\hat y)+(1-y)\log(1-\hat y)\right)  
]

---

## 3. Categorical Cross-Entropy

Used for **Multi-Class Classification**.

Examples:

- Cat, Dog, Bird
    
- Digit Recognition (0–9)
    

---

# Real-Life Analogy

Imagine a teacher checking an exam:

- Actual marks = 90
    
- Predicted marks = 85
    

Loss Function says:

```text
Error = 5 marks
```

If the prediction were 40 instead of 85:

```text
Error = 50 marks
```

The second prediction has a much higher loss.

---

# Goal of Training

The ANN continuously tries to:

```text
High Loss  →  Lower Loss  →  Minimum Loss
```

This happens through:

- Backpropagation
    
- Gradient Descent
    

---

# Relationship with Previous Topics

```text
Forward Propagation
       ↓
Prediction
       ↓
Loss Function
       ↓
Backpropagation
       ↓
Gradient Calculation
       ↓
Gradient Descent
       ↓
Weight Update
```

---

## Exam Definition

> A loss function is a mathematical function that measures the difference between the actual output and the predicted output of a neural network. The objective of training is to minimize this loss.

### Quick Rule for Interviews/Exams

- **Regression** → MSE, MAE
    
- **Binary Classification** → Binary Cross-Entropy
    
- **Multi-Class Classification** → Categorical Cross-Entropy
    

The next topic should be **Gradient Descent**, because once we know the loss, we need a method to reduce it by updating the weights.