After calculating:

```
z=∑(xw)+b
```

we pass it through an activation function.

Activation functions decide:

> "Should this neuron activate or not?"

Without activation functions, neural networks become just a series of linear equations.

## A. Step Function

Used in the original perceptron.
```
If z >= 0 → 1
Else → 0
```

Example:
```
z = 2
Output = 1
```

```
z = -1
Output = 0
```

Problem:

- Not differentiable
- Cannot be used effectively in modern deep learning

# B. Sigmoid Function

Outputs values between 0 and 1.
Example:
```
Input = 0
Output = 0.5
```
Used for:

- Binary Classification
- Probability prediction

Range:
```
0 to 1
```

# C. Tanh Function
Outputs values between -1 and 1.
![[Pasted image 20260613173844.png]]

range: 
-1 to 1

Advantages:

- Zero-centered
- Better than sigmoid in many cases


# D. Relu(Most Important)
Rectified Linear Unit

f(x)=max(0,x)

example:
```
Input = -5 -> Output - 0
Input = 3 -> Output = 3
```
Why popular?

- Simple
- Fast
- Reduces vanishing gradient problem

Used in most modern deep learning models.


# E. Softmax
used in multi class classification 

example:
```
Cat    = 0.70
Dog    = 0.20
Bird   = 0.10
```


Total Probability
```
1.0
```

Used in:

- Digit Recognition
- Image Classification
- NLP Classification


