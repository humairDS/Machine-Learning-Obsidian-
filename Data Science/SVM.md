SVM stands for **Support Vector Machine**.
It is a Machine Learning algorithm mainly used for:
- Classification
- Regression (less common)


The main goal of SVM is:
Find the best boundary that separates classes.
That boundary is called a **Hyperplane**.

# Simple Real-Life Example

Imagine two groups:

- Apples 🍎
- Oranges 🍊

SVM tries to draw the **best line** between them.
Apples   |   Oranges
Apples   |   Oranges
Apples   |   Oranges

The line in the middle is the hyperplane.

# Main Idea of SVM

SVM does not just find _any_ separating line.

It finds the line with the:

# Maximum Margin

Margin = distance between classes and boundary.
Class A  ←→ Margin ←→ Hyperplane ←→ Margin ←→ Class B

Larger margin:
- Better generalization
- Better prediction on unseen data
# Support Vectors
The closest points to the boundary are called:

# Support Vectors

These points are very important because they define the hyperplane.
● ● ●     |     ▲ ▲ ▲
    ↑ support vectors
If support vectors move, the boundary changes.

# Hyperplane

A hyperplane is:

- A line in 2D
- A plane in 3D
- Higher-dimensional separator in ML

Example:

## 2D
x + y = 5


# Why SVM is Powerful

SVM works well for:

- High-dimensional data
- Complex classification problems
- Small-to-medium datasets

Especially useful in:

- Text classification
- Image recognition
- Spam detection

# Types of SVM

## 1. Linear SVM

Used when data is linearly separable.

```
● ● ● | ▲ ▲ ▲
```

Straight line works.

---

## 2. Non-Linear SVM

Used when data is not separable by straight line.

Uses something called:



## [[SVM Python Example]]
