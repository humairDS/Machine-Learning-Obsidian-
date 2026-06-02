It is one of the simplest Machine Learning algorithms.

KNN works by:

```
Finding the nearest data pointsand predicting based on them.
```

# Simple Real-Life Example

Imagine you move to a new city and want to know whether an area is good or bad.

You ask your nearest neighbors:

- If most say “good” → you think it’s good
- If most say “bad” → you think it’s bad

That is exactly how KNN works.

# Core Idea of KNN

When a new data point comes:

1. Calculate distance from all existing points
2. Find nearest K neighbors
3. Take majority vote (classification)
4. Or average (regression)


# What Does “K” Mean?

K = number of nearest neighbors.

Example:

```
K = 3
```

Means:

- Look at the 3 nearest points.

# Classification Example

Suppose:

```
Neighbor 1 → Cat
Neighbor 2 → Cat
Neighbor 3 → Dog
```

Majority = Cat

Final Prediction = Cat

# Regression Example

Suppose nearest values are:

```
10, 20, 30
```

Prediction:

```
(10 + 20 + 30) / 3 = 20
```


# How Distance is Calculated

Most common distance:

# Euclidean Distance


d=sqrt((x2​−x1​)2+(y2​−y1​)2)​


# Why KNN is Called Lazy Learning

KNN does not learn patterns during training.

It simply:

- Stores data
- Calculates during prediction time

So:

- Training = very fast
- Prediction = slower

---

# Advantages

✅ Very simple  
✅ Easy to understand  
✅ No training phase almost  
✅ Works well for small datasets  
✅ Handles nonlinear data

---

# Disadvantages

❌ Slow on large datasets  
❌ Sensitive to noise  
❌ Needs feature scaling  
❌ Memory expensive


# Choosing the Best K

## Small K

Example:

```
K = 1
```

- Very sensitive to noise
- Can overfit

---

## Large K

Example:

```
K = 50
```

- Smoother predictions
- May underfit

Usually odd K values are preferred:

- 3
- 5
- 7


## [[Python Example of KNN]]
