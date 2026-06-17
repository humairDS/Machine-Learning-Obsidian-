What is LSTM

**LSTM** stands for **Long Short-Term Memory**.

It is a special type of **Recurrent Neural Network (RNN)** designed to remember information for a long time and overcome the main weakness of basic RNNs.


## Why Was LSTM Created?

Consider this sentence:

> "I grew up in Karachi. I speak fluent ____."

To predict the missing word (**Urdu**), the model needs to remember information from much earlier in the sentence.

A basic RNN often forgets important information when sequences become long. This is known as the **vanishing gradient problem**.

LSTM was developed to solve this problem.


## Main Idea of LSTM

Think of an LSTM as a **smart memory system**.

It decides:

1. What information to remember
2. What information to forget
3. What information to output

Unlike a simple RNN, it doesn't store everything blindly.

Structure of an LSTM Cell
```
Previous Memory
      ↓
 Forget Gate
      ↓
 Input Gate
      ↓
 Update Memory
      ↓
 Output Gate
      ↓
 Current Output
```

## Example

Sentence:

```
The weather today is very hot, so I will drink cold _____
```

When predicting the last word, the LSTM remembers:

- weather
- hot
- drink
- cold

and can correctly predict:

```
water
```

because it keeps important context in memory.

### Natural Language Processing (NLP)

- Language translation
- Text generation
- Chatbots

### Speech Recognition

- Voice assistants
- Speech-to-text

### Time-Series Forecasting

- Stock prices
- Sales prediction
- Weather forecasting

### Sentiment Analysis

- Positive/negative review classification


## [[LSTM Python Example]] 
