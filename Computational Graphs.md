# Computational Graph in Backpropagation

A **computational graph** is a visual representation of all calculations performed in a neural network.

Think of it as a **flowchart of mathematical operations**.

It helps us:

1. Perform the **forward pass** (calculate output).
2. Perform the **backward pass** (calculate gradients using the chain rule).

---

## Simple Example

Suppose:

x=2x = 2x=2 y=x2y = x^2y=x2 z=y+3z = y + 3z=y+3

The computational graph looks like:

```
x=2 │ ▼ y=x² │ ▼ z=y+3
```

Forward pass:

- x=2x = 2x=2
- y=22=4y = 2^2 = 4y=22=4
- z=4+3=7z = 4 + 3 = 7z=4+3=7

Output = **7**

---

## Backward Pass

Now let's find:

dzdx\frac{dz}{dx}dxdz​

Using the chain rule:

dzdx=dzdy×dydx\frac{dz}{dx} = \frac{dz}{dy} \times \frac{dy}{dx}dxdz​=dydz​×dxdy​

We know:

dzdy=1\frac{dz}{dy}=1dydz​=1

and

dydx=2x\frac{dy}{dx}=2xdxdy​=2x

At x=2x=2x=2:

dydx=4\frac{dy}{dx}=4dxdy​=4

Therefore:

dzdx=1×4=4\frac{dz}{dx}=1\times4=4dxdz​=1×4=4

This backward movement through the graph is exactly what **backpropagation** does.

---

## Computational Graph for a Neuron

A neuron computes:

z=wx+bz = wx+bz=wx+b

Then applies an activation function:

a=f(z)a = f(z)a=f(z)

Graph:

```
x ------         \          × ----> +b ----> z ----> Activation ----> a         /w ------
```

### Forward Pass

1. Multiply input and weight
2. Add bias
3. Apply activation
4. Produce output

### Backward Pass

1. Calculate loss
2. Move backward through activation
3. Move through addition
4. Move through multiplication
5. Update weight and bias

---

## Why Computational Graphs Matter

Without computational graphs:

❌ Backpropagation would be very difficult.

With computational graphs:

✅ We can automatically compute gradients.

This is why frameworks like:

- TensorFlow
- PyTorch

automatically perform backpropagation using computational graphs.

---

## Exam Definition

> A computational graph is a directed graph that represents mathematical operations and variables, enabling efficient forward computation and gradient calculation during backpropagation.