- [[Architecture]]
- [[Forward Propagation]]
- [[Loss Functions]]
- [[Backpropagation]] 


An **Artificial Neural Network (ANN)** is a machine learning model inspired by how the human brain works. It is mainly used in **deep learning** to solve complex problems like image recognition, speech detection, and predictions.

---

## 🧠 What is ANN?

ANN is a system made of connected units called **neurons** that process information and pass it forward.

Think of it like this:

> Input → Brain-like processing → Output


## 🏗️ Basic Structure of ANN

### 1. Input Layer

- Takes raw data
- Example: age, salary, images pixels

### 2. Hidden Layers

- Where the “learning” happens
- Multiple layers = Deep Neural Network
- Each neuron applies calculations and patterns

### 3. Output Layer

- Gives final result
- Example: Yes/No, Dog/Cat, Price prediction

---

## ⚙️ How ANN Works

Each neuron does this:

1. Takes inputs
2. Multiplies by weights
3. Adds bias
4. Applies activation function
5. Passes result forward

### Formula:

y=f(∑(wi​xi​)+b)

Where:

- **x** = inputs
- **w** = weights
- **b** = bias
- **f** = activation function

---

## 🔥 Activation Function (Important)

It decides whether a neuron should “fire” or not.

Common ones:

- [[ReLU]] (most used)
- [[Sigmoid]]
- [[Tanh]] 

---

## 🧪 Example (Real Life)

Imagine predicting if a student will pass:

Inputs:

- Study hours
- Attendance
- Sleep

ANN processes these and outputs:

- Pass / Fail prediction

---

## 📌 Why ANN is powerful?

- Learns patterns automatically
- Works with complex data (images, text)
- Improves with more data

---

## ⚠️ When ANN is used?

- Image recognition (face unlock)
- Chatbots
- Stock prediction
- Medical diagnosis