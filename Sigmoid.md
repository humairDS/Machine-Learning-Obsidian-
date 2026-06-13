# Sigmoid

Formula:

f(x)=1/1+e-x

### Output Range

```
0 to 1
```

### Example Values

|Input|Output|
|---|---|
|-5|0.007|
|-2|0.119|
|0|0.5|
|2|0.881|
|5|0.993|

---

## Practical Example

Suppose you're predicting:

> Will a customer buy a product?

Output:

0.95%

Interpretation:

```
95% chance customer buys
```

Output:

0.12%

Interpretation:

```
12% chance customer buys
```

That's why Sigmoid is often used in the **output layer of binary classification problems**.

Examples:

- Spam / Not Spam
- Pass / Fail
- Disease / No Disease

---

## Problem with Sigmoid

For very large positive or negative values:

```
Gradient ≈ 0
```

This causes the **vanishing gradient problem**.