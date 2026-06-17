Most common type.

Starts with:

- Every point as its own cluster.

Then:

- Closest clusters merge repeatedly.
```
1 point → small clusters → bigger clusters
```


Agglomerative Clustering Process

Suppose we have points:
```
A  B  C  D
```

Step 1
Each point becomes its own cluster.
```
[A] [B] [C] [D]
```

Step 2
Merge closest clusters.
```
[AB] [C] [D]
```

Step 3
Merge Again
```
[AB] [CD]
```

Step 4
Final Merge
```
[ABCD]
```


[[Python Example]]
```python
from sklearn.cluster import AgglomerativeClustering
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
model = AgglomerativeClustering(
    n_clusters=2
)

# Fit and predict
labels = model.fit_predict(X)

print(labels)
```



---

# Dendrogram Visualization
```python 
from scipy.cluster.hierarchy import dendrogram, linkage
import matplotlib.pyplot as plt

linked = linkage(X, method='ward')

dendrogram(linked)

plt.show()
```

