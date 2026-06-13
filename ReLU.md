# ReLU (Rectified Linear Unit)

Formula:

f(x)=max(0,x)

### How it works

|Input|Output|
|---|---|
|-5|0|
|-2|0|
|0|0|
|3|3|
|7|7|

### Graph Intuition

```
       /  
      /  
     /  
----/

```


Negative values become 0, positive values remain unchanged.

---

## Practical Example

Imagine a bank loan prediction model.

Features:

- Income
- Credit Score
- Debt

A neuron calculates:

z=−3z=-3z=−3

After ReLU:

f(−3)=0f(-3)=0f(−3)=0

This means that neuron contributes nothing because the signal isn't useful.

Another neuron gets:

z=5z=5z=5

After ReLU:

f(5)=5f(5)=5f(5)=5

The information moves forward.

### Why ReLU is popular

✅ Fast computation

✅ Reduces vanishing gradient problem

✅ Works very well in deep learning