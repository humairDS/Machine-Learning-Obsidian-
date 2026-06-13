The **Deep Network** in **DNN (Deep Neural Network)** refers to having **multiple hidden layers between the input and output layers**.

Think of it this way:

```text
Input Layer
     ↓
Hidden Layer 1
     ↓
Hidden Layer 2
     ↓
Hidden Layer 3
     ↓
Output Layer
```

This network is called **deep** because information passes through several layers before reaching the output.

### Why do we need deep networks?

Each hidden layer learns features at a different level:

For image recognition:

- Hidden Layer 1 → Learns edges and lines
- Hidden Layer 2 → Learns shapes and patterns
- Hidden Layer 3 → Learns objects like eyes, ears, faces
- Output Layer → Predicts "Cat" or "Dog"

The deeper the network, the more complex patterns it can learn.

### Example

Suppose you're predicting house prices using:

- Area
- Bedrooms
- Location Score

A shallow ANN might have:

```text
Input → Hidden Layer → Output
```

A DNN might have:

```text
Input → Hidden Layer 1 → Hidden Layer 2 → Hidden Layer 3 → Output
```

The deeper network can learn more complicated relationships between the inputs and the final house price.

### Key Point

A network becomes "deep" when it has **more than one hidden layer**.

```text
1 Hidden Layer  → ANN (Shallow Network)
2+ Hidden Layers → DNN (Deep Network)
```

So, **"Deep Network" simply means a neural network with multiple hidden layers that can learn increasingly complex features from data.**
