```python 
from sklearn.cluster import KMeans
import numpy as np

# Data
X = np.array([
    [1, 2],
    [1, 4],
    [1, 0],
    [10, 2],
    [10, 4],
    [10, 0]
])

# Create model
model = KMeans(
    n_clusters=2,
    random_state=42
)

# Train model
model.fit(X)

# Cluster labels
print(model.labels_)

# Centroids
print(model.cluster_centers_)
```

# Understanding the Code

Create the Model
```python 
KMeans(n_clusters=2)
```
Means:
- Create 2 clusters.


Fit Model
```python 
model.fit(X)
```
Finds cluster patterns.

Labels
```python 
model.labels_
```
Example
```
[0 0 0 1 1 1]
```

Cluster Centers

```python 
model.cluster_centers_
```



---

# Feature Scaling is Important

```python 
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```


