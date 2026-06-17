**RNN** stands for **Recurrent Neural Network**.

It is a type of **Deep Learning** neural network designed to work with **sequential data**, where the order of the data matters.

Examples of sequential data:

- Text and sentences
- Speech and audio
- Time-series data (stock prices, weather)
- Video frames

## Why Do We Need RNNs?

A normal neural network processes each input independently.

For example, in the sentence:

> "I grew up in Pakistan, so I speak ____."

To predict the missing word, the model needs information from the earlier words in the sentence.

RNNs solve this problem by having a **memory** of previous inputs.



## How RNN Works

Unlike a traditional neural network, an RNN passes information from one step to the next.

```
Input1 → Hidden State → Output1 
          ↓
Input2 → Hidden State → Output2
          ↓
Input3 → Hidden State → Output3
```


The hidden state acts like memory.

At each time step:

```
Current Output =
Current Input + Previous Hidden State
```

This allows the network to remember earlier information.


Example: Predicting Words
Sentence:

```
I love learning Data Science
```

The RNN processes one word at a time:

```
"I"       → Memory
"love"    → Uses memory from "I"
"learning"→ Uses memory from previous words
"Data"    → Uses earlier context
"Science" → Uses all previous context
```


Because it remembers previous words, it understands the sentence better.

---

## RNN Architecture

```
Input Sequence
      ↓
RNN Cell
      ↓
Hidden State (Memory)
      ↓
Output
```

When unfolded through time:

```
x1 → [RNN] → h1
            ↓
x2 → [RNN] → h2 
            ↓
x3 → [RNN] → h3
            ↓
x4 → [RNN] → h4
```

Where:

- **x** = input
- **h** = hidden state (memory)


### 1. Natural Language Processing (NLP)
- Language translation
- Chatbots
- Text generation
### 2. Speech Recognition
- Voice assistants
- Speech-to-text systems
### 3. Time-Series Forecasting
- Stock price prediction
- Weather forecasting
### 4. Text Prediction
- Keyboard next-word suggestions

## Problem with Basic RNNs

RNNs struggle with remembering information from very long sequences.

Example:

```
The movie that I watched last week with my friends was really good.
```

When predicting the last words, the network may forget information from the beginning of the sentence.

This is called the **vanishing gradient problem**.


## Improved Versions of RNN

To solve memory issues, researchers developed:

### 1. [[LSTM]]

**Long Short-Term Memory**

- Can remember information for a long time
- Most widely used RNN variant

### 2. [[GRU]]

**Gated Recurrent Unit**

- Simpler than LSTM
- Faster to train
- Similar performance


## [[Python RNN Example]]
