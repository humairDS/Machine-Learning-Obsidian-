# What is Naive Bayes?

Naive Bayes is a **probability-based Machine Learning algorithm** mainly used for:
- Classification
- Text classification
- Spam detection
- Sentiment analysis


It is based on:
# Bayes’ Theorem

# Simple Real-Life Example

Imagine you receive an email.

The model checks words like:

- “Free”
- “Win”
- “Lottery”

If these words appear often in spam emails,  
the model predicts:

```
This email is probably spam.
```

That is Naive Bayes.


# Why is it Called “Naive”?

Because it assumes:

```
All features are independent.
```

Example:

When predicting whether someone buys a car:

- Salary
- Age
- Location

Naive Bayes assumes these features are independent.

In real life they are not fully independent,  
so the assumption is “naive.”

# Bayes Theorem

Core formula:
P(A/B) = P(B|A)P(A)/P(B)

# Easy Example

Suppose:

- 90% spam emails contain word “Free”
- 10% normal emails contain “Free”

If a new email contains “Free”,  
Naive Bayes increases spam probability.

# How Naive Bayes Works

## Step 1

Calculate probabilities from training data.

## Step 2

For new data:

- Compute probability for each class

## Step 3

Choose class with highest probability.


# Types of Naive Bayes

## 1. Gaussian Naive Bayes

Used for continuous numerical data.
Example:
- Height
- Weight
- Salary

## 2. Multinomial Naive Bayes

Used for text data and word counts.
Example:
- Spam detection
- NLP

## 3. Bernoulli Naive Bayes

Used for binary features.
Example:
- Yes/No
- 0/1

# Why Naive Bayes is Popular

Because it:

- Is extremely fast
- Works very well on text data
- Needs small training data
- Simple to implement


# Advantages

✅ Very fast  
✅ Simple algorithm  
✅ Works great for NLP  
✅ Performs well with small datasets  
✅ Handles multiclass classification

---

# Disadvantages

❌ Assumes independence  
❌ Not ideal for complex relationships  
❌ Probability estimates may be inaccurate


# Real-Life Applications

- Spam filtering
- Sentiment analysis
- News classification
- Recommendation systems
- Document categorization


## [[Naive Bayes Python Example]]
