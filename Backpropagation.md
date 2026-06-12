# 🔁 Backpropagation (Simple + Clear)

**Backpropagation** is the algorithm used to **reduce error in a neural network by updating weights backward from output to input.**

In simple words:

> “ANN learns from its mistakes and adjusts itself.”

---

# 🧠 Why do we need it?

When ANN gives a wrong prediction:

- We calculate **error (loss)**
- Then we adjust weights so next time it becomes better

Without backpropagation → ANN would NOT learn.

---

# ⚙️ How Backpropagation Works (Step-by-Step)

## 1. Forward Pass ➜ (Prediction)

Input goes through network:

Input → Hidden Layers → Output

Example:

- Actual: 1 (Dog)
- Predicted: 0.7

---

## 2. Loss Calculation 📉

We calculate error using a loss function:

Example:

- Error = Actual - Predicted
- Loss tells “how wrong model is”

---

## 3. Backward Pass 🔙 (Main idea)

Now we go **backward through the network**:

Output → Hidden → Input

We calculate:

- Which weights caused the error
- How much each weight contributed

This uses **calculus (chain rule)**.

---

## 4. Weight Update ⚙️

We update weights using:

w=w−η⋅∂Loss∂ww = w - \eta \cdot \frac{\partial Loss}{\partial w}w=w−η⋅∂w∂Loss​

Where:

- **w** = weight
- **η (eta)** = learning rate
- **derivative** = how much weight affects error

---

# 🔥 Intuition (Very Important)

Think of it like:

> You got low marks in exam  
> You check mistakes  
> You fix weak topics  
> Next exam = better marks

ANN does exactly this mathematically.

---

# 🧩 Simple Analogy

### Forward pass:

Teacher asks question → you answer

### Loss:

Teacher says “wrong”

### Backpropagation:

You check:

- Where you went wrong
- Which part caused mistake

### Update:

You improve your understanding

---

# ⚡ Key Idea

✔ Forward = prediction  
✔ Loss = mistake  
✔ Backprop = find blame  
✔ Update = fix weights

---

# 📌 One Line Definition

> Backpropagation is a method that calculates gradients of loss and updates neural network weights in reverse direction to minimize error.


1. [[Chain Rule]]
2. [[Gradient Flow]]
3. [[Computational Graphs]] 