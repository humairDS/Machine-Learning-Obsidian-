# Architecture of ANN (Artificial Neural Network)

The **architecture of an ANN** refers to the **structure or layout of the neural network**, including:

- Number of layers
- Number of neurons in each layer
- How neurons are connected

In simple words:

> ANN Architecture = Blueprint of the Neural Network

---

## Basic ANN Architecture

```text
Input Layer
     │
     ▼
Hidden Layer(s)
     │
     ▼
Output Layer
```

### 1. Input Layer

- Receives data from the outside world.
- Number of neurons = Number of features.

Example:

- Age
- Salary
- Experience

→ 3 features = 3 input neurons

---

### 2. Hidden Layer

- Performs computations and learns patterns.
    
- Can have one or many hidden layers.
    

Example:

```text
Input Layer (3 neurons)
        │
        ▼
Hidden Layer (5 neurons)
        │
        ▼
Output Layer (1 neuron)
```

The more hidden layers, the more complex patterns the network can learn.

---

### 3. Output Layer

Produces the final prediction.

Examples:

- House Price → 1 neuron
- Spam/Not Spam → 1 neuron
- Cat/Dog/Bird → 3 neurons

---

## Example Architecture

Suppose you want to predict whether a student will pass.

Inputs:

- Study Hours
- Attendance
- Sleep Hours

Architecture:

```text
3 Input Neurons
       │
       ▼
5 Hidden Neurons
       │
       ▼
1 Output Neuron
```

This architecture is often written as:

```text
3 → 5 → 1
```

---

## Types of ANN Architectures

### 1. Single-Layer Perceptron

```text
Input → Output
```

- No hidden layer
- Can solve only simple problems

---

### 2. Multi-Layer Perceptron (MLP)

```text
Input → Hidden → Output
```

- Most common ANN architecture
- Uses backpropagation
- Can solve complex problems

---

### 3. Deep Neural Network (DNN)

```text
Input → Hidden → Hidden → Hidden → Output
```

- Multiple hidden layers
- Used in modern deep learning

---

## Key Components of Architecture

When describing an ANN architecture, mention:

1. Number of Input Neurons
2. Number of Hidden Layers
3. Number of Neurons per Hidden Layer
4. Activation Functions ([[ReLU]], [[Sigmoid]], [[Tanh]])
5. Number of Output Neurons

Example:

```text
Input Layer: 4 neurons
Hidden Layer 1: 8 neurons (ReLU)
Hidden Layer 2: 6 neurons (ReLU)
Output Layer: 1 neuron (Sigmoid)
```

Architecture:

```text
4 → 8 → 6 → 1
```

---

## Real-Life Analogy

Think of a company:

```text
Customers
    ↓
Employees
    ↓
Manager
```

- Customers = Input Layer
- Employees = Hidden Layers
- Manager = Output Layer

Information flows through the organization just like data flows through an ANN.

---

## Exam Definition

> ANN architecture is the arrangement of layers, neurons, and connections in a neural network that determines how input data is processed to produce an output.

---

