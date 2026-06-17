```python
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler
from sklearn.datasets import load_iris

# Load data
data = load_iris()
X = data.data

# Scale data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Apply PCA
pca = PCA(n_components=2)

X_pca = pca.fit_transform(X_scaled)

print(X_pca.shape)
```

Output:

```text
(150, 2)
```

Meaning:

```text
150 samples
4 features → 2 principal components
```

---

# Understanding the Code

## Create PCA

```python
PCA(n_components=2)
```

Means:

```text
Keep only 2 principal components
```

---

## Fit Transform

```python
pca.fit_transform(X_scaled)
```

Finds components and transforms data.

---

# Explained Variance Ratio

Very important in PCA.

```python
print(pca.explained_variance_ratio_)
```

Example:

```text
[0.72, 0.23]
```

Meaning:

- PC1 explains 72% information
    
- PC2 explains 23% information
    

Total:

```text
95% information retained