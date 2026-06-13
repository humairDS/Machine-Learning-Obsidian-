- [[Deep Networks]]
- [[Vanishing Gradient]]
- [[Batch Normalization]]
- [[Dropout]] 

A **Deep Neural Network** is simply an **Artificial Neural Network with multiple hidden layers**.

### ANN vs DNN

**ANN (Shallow Network)**

```text
Input Layer
     ↓
Hidden Layer
     ↓
Output Layer
```

Only one hidden layer.

**DNN (Deep Network)**

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

Two or more hidden layers.

---

# Why "Deep"?

The word **Deep** refers to the depth of the network, meaning the number of hidden layers.

Example:

- 1 hidden layer → ANN
- 3 hidden layers → DNN
- 50 hidden layers → Very Deep Neural Network

---

# Real-Life Example

Imagine you want to identify a cat in an image.

### Layer 1 learns:

- Edges
- Lines
- Corners

### Layer 2 learns:

- Eyes
- Ears
- Tail

### Layer 3 learns:

- Complete cat face

### Output Layer:

- Cat ✅
- Not Cat ❌

Each deeper layer learns more complex patterns.

---

# Structure of a DNN

```text
Input Layer
(Height, Weight, Age)

       ↓

Hidden Layer 1
(Feature Extraction)

       ↓

Hidden Layer 2
(Complex Relationships)

       ↓

Hidden Layer 3
(Higher-Level Features)

       ↓

Output Layer
(Weight Gain / Weight Loss)
```

---

# Mathematical Working

For each neuron:

Then apply an activation function:

```text
a = Activation(z)
```

The output of one layer becomes the input of the next layer.

---

# Advantages of DNN

✅ Learns complex patterns

✅ High accuracy on large datasets

✅ Used in image recognition

✅ Used in speech recognition

✅ Used in NLP and ChatGPT-like systems

---

# Disadvantages of DNN

❌ Requires a lot of data

❌ Requires more training time

❌ Needs powerful hardware (GPU)

❌ Can overfit if not handled properly

---

# Applications of DNN

### Computer Vision

- Face Recognition
    
- Object Detection
    
- Medical Imaging
    

### Natural Language Processing (NLP)

- Chatbots
    
- Translation
    
- Sentiment Analysis
    

### Recommendation Systems

- Netflix recommendations
    
- YouTube recommendations
    

### Healthcare

- Disease prediction
    
- Medical diagnosis
    

---

# [[Practical Example of DNN]]

# Interview Question

**Q: What is the difference between ANN and DNN?**

**Answer:**  
A DNN is an ANN with multiple hidden layers. DNNs can learn more complex patterns and achieve better performance on large datasets, but they require more data and computational power.

