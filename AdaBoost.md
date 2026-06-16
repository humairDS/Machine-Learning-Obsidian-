# What is AdaBoost?

**AdaBoost (Adaptive Boosting)** is a **machine learning ensemble technique** used to improve the accuracy of weak models by combining them into a strong model.

# Simple Idea

Instead of using one strong model, AdaBoost:

```
Builds many weak models → combines them → creates a strong model
```

Usually, the weak models are **Decision Stumps** (very small decision trees with only 1 split).


# Real-Life Example

Imagine students taking a test:

- Weak student 1: gets some answers wrong
- Weak student 2: corrects previous mistakes
- Weak student 3: focuses on hard questions

Finally:

```
Combined knowledge = strong performance
```

That’s AdaBoost.

# How AdaBoost Works

## Step 1: Start with equal weights

Every data point is treated equally.

```
All points → same importance
```

---

## Step 2: Train weak model

A simple model (like a stump) is trained.

---

## Step 3: Check errors

Misclassified points are identified.

---

## Step 4: Increase weight of wrong points

AdaBoost says:

```
“Focus more on the mistakes”
```

So wrong points get higher weight.

---

## Step 5: Train next model

Next model focuses more on difficult points.

---

## Step 6: Repeat

Many weak learners are created.



## Step 7: Combine results

Final prediction is a **weighted vote**:

```
Final = weighted sum of all models
```

---

# Key Idea

```
Hard-to-classify points get more attention in each iteration
```

That is why it is called **Adaptive Boosting**.


# Why AdaBoost is Powerful

- It improves weak models
- Reduces bias
- Focuses on mistakes
- Often gives high accuracy


# Simple Visual

```
Model 1 → learns easy patterns
Model 2 → fixes mistakes
Model 3 → improves further
Final → strong classifier
```

# AdaBoost Formula Idea

Final prediction:

```
Final = Σ (weight of model × prediction)
```

## [[Python Example Adaboost]]
