# What is K-Means Clustering?

K-Means is an **Unsupervised Machine Learning algorithm** used for:

- Grouping similar data points
- Finding hidden patterns in data

It creates clusters/groups based on similarity.

# Simple Real-Life Example

Imagine a shopping mall wants to group customers based on:

- Spending habits
- Age
- Shopping frequency

K-Means can automatically create groups like:
Cluster 1 → Budget customers
Cluster 2 → Premium customers
Cluster 3 → Occasional shoppers


# Why is it Called “K-Means”?

## K

Number of clusters/groups.

## Means

Average center of each cluster.

That center is called:

# Centroid


Main Goal
```
Place similar points into the same cluster.
```


# How K-Means Works

## Step 1: Choose K

Example:

```
K = 3
```

Means:

- Create 3 clusters.

---

## Step 2: Randomly Place Centroids

Initial center points are chosen randomly.

---

## Step 3: Assign Points to Nearest Centroid

Each point joins the nearest cluster.

---

## Step 4: Recalculate Centroids

Compute new average position of each cluster.

Centroid formula:

μ=1n∑i=1nxi\mu = \frac{1}{n}\sum_{i=1}^{n} x_iμ=n1​∑i=1n​xi​

---

## Step 5: Repeat

Keep repeating:

- Assign points
- Update centroids

Until clusters stop changing.



## Example with Customers

| Customer | Spending |
| -------- | -------- |
| A        | High     |
| B        | High     |
| C        | Low      |
| D        | Low      |

K-Means groups:

- High spenders
- Low spenders


# Important Concept: Inertia

K-Means tries to minimize:

# Within Cluster Sum of Squares (WCSS)

Formula:

WCSS=∑i=1k​∑x∈Ci​​∣∣x−μi​∣∣2

Meaning:

- Points should stay close to centroid.

Lower WCSS = better clusters.



## [[Python Example]]



## K-Means vs KNN

| K-Means            | KNN             |
| ------------------ | --------------- |
| Unsupervised       | Supervised      |
| Finds clusters     | Predicts labels |
| No target variable | Needs labels    |
| Uses centroids     | Uses neighbors  |
