# What is PCA?

PCA stands for:

# Principal Component Analysis

It is a **Dimensionality Reduction** technique used to reduce the number of features while keeping as much important information as possible.

---

# Why Do We Need PCA?

Imagine a dataset with:

```text
Age
Salary
Height
Weight
Education
Experience
Income
...
100 Features
```

Too many features can cause:

- Slower training
- More memory usage
- Overfittin
- Difficult visualization

PCA reduces features while preserving most of the information.

---

# Simple Real-Life Example

Suppose you want to evaluate a student's performance using:

- Quiz Marks
- Assignment Marks
- Midterm Marks
- Final Exam Marks

These are highly related.

PCA can combine them into a smaller number of features that represent overall academic performance.

---

# Main Idea

PCA finds new features called:

# Principal Components

These components:

- Contain maximum information (variance)
- Are combinations of original features
- Are independent of each other

---

# Visual Understanding

Suppose data looks like:

```text
*
  *
    *
      *
        *
```

Instead of using:

- X coordinate
- Y coordinate

PCA finds the direction where data varies the most and projects data onto that line.

---

# What is Variance?

Variance means:

```text
How spread out the data is
```

More variance = more information.

PCA tries to keep directions with maximum variance.

---

# Principal Components

## First Principal Component (PC1)

Contains the most variance.

## Second Principal Component (PC2)

Contains the second most variance.

And so on...

Example:

```text
Original Features = 10

After PCA:
PC1
PC2

Only 2 features remain
```

---

# PCA Workflow

## Step 1

Standardize data.

```python
from sklearn.preprocessing import StandardScaler
```

---

## Step 2

Compute covariance matrix.

Measures relationships between features.

---

## Step 3

Find Eigenvalues and Eigenvectors.

These determine:

- Importance of directions
    
- New feature axes
    

---

## Step 4

Select top principal components.

---

## Step 5

Transform data.

Result:

```text
100 Features → 10 Features
```

---

# Why Feature Scaling is Important

Suppose:

```text
Age = 25
Salary = 100000
```

Salary dominates calculations.

Therefore PCA should usually be applied after scaling.

```python
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

---

# [[PCA Python Example]]

```

---

# PCA Visualization

PCA is often used to visualize high-dimensional data.

Example:

```text
100 Features
      ↓
PCA
      ↓
2 Features
      ↓
Scatter Plot
```

---

# Advantages

✅ Reduces dimensionality  
✅ Speeds up training  
✅ Reduces overfitting  
✅ Removes redundancy  
✅ Helps visualization

---

# Disadvantages

❌ Hard to interpret components  
❌ Information loss occurs  
❌ Sensitive to scaling  
❌ Assumes linear relationships

---

# PCA vs Feature Selection

|PCA|Feature Selection|
|---|---|
|Creates new features|Keeps original features|
|Combines information|Removes features|
|Harder to interpret|Easier to interpret|

---

# Real-World Applications

- Image compression
- Face recognition
- Data visualization
- Noise reduction
- Bioinformatics
- Financial analysis

---

# Interview Question

## Does PCA work with labels?

No.

PCA is an **unsupervised technique**.

It only looks at the feature values (X) and ignores the target variable (y).

---

# Quick Revision

PCA:

- Principal Component Analysis
- Dimensionality reduction technique
- Finds directions with maximum variance
- Creates Principal Components
- Reduces features while preserving information
- Usually applied after feature scaling

---

# One-Line Exam Definition

**PCA (Principal Component Analysis) is an unsupervised dimensionality reduction technique that transforms a large set of correlated features into a smaller set of uncorrelated principal components while retaining most of the data's variance.**