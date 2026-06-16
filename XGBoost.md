Traditional models like decision trees and random forests are easy to interpret but may lack accuracy on complex data. XGBoost (eXtreme Gradient Boosting) is an optimized [gradient boosting algorithm](https://www.geeksforgeeks.org/machine-learning/ml-gradient-boosting/) that combines multiple weak models into a stronger, high-performance model.

- It uses decision trees as base learners, building them sequentially so each tree corrects errors from the previous one and it is known as [boosting](https://www.geeksforgeeks.org/machine-learning/boosting-in-machine-learning/).
- It features parallel processing for faster training on large datasets and allows parameter customization to optimize performance for specific problems.

![Evolution-of-Tree-Algorithm.webp](https://media.geeksforgeeks.org/wp-content/uploads/20250521100553962515/Evolution-of-Tree-Algorithm.webp)

## How XGBoost Works?

It builds [decision trees](https://www.geeksforgeeks.org/machine-learning/decision-tree/) sequentially with each tree attempting to correct the mistakes made by the previous one. The process can be broken down as follows:

1. **Start with a base learner**: The first model decision tree is trained on the data. In regression tasks this base model simply predicts the average of the target variable.
2. **Calculate the errors**: After training the first tree the errors between the predicted and actual values are calculated.
3. **Train the next tree**: The next tree is trained on the errors of the previous tree. This step attempts to correct the errors made by the first tree.
4. **Repeat the process**: This process continues with each new tree trying to correct the errors of the previous trees until a stopping criterion is met.
5. **Combine the predictions**: The final prediction is the sum of the predictions from all the trees.

## How XGBoost Improves Traditional Gradient Boosting

XGBoost extends traditional gradient boosting by including regularization elements in the objective function, XGBoost improves generalization and prevents overfitting.

### 1. Preventing Overfitting

XGBoost incorporates several techniques to reduce overfitting and improve model generalization:

- ****Learning rate (eta):**** Controls each tree’s contribution i.e a lower value makes the model more conservative.
- ****Regularization:**** Adds penalties to complexity to prevent overly complex trees.
- ****Pruning:**** Trees grow depth-wise and splits that do not improve the objective function are removed, keeping trees simpler and faster.
- ****Combination effect:**** Using learning rate, regularization and pruning together enhances robustness and reduces overfitting.

### 2. Tree Structure

XGBoost builds trees level-wise (breadth-first) rather than the conventional depth-first approach, adding nodes at each depth before moving to the next level.

- ****Best splits:**** Evaluates every possible split for each feature at each level and selects the one that minimizes the objective function like MSE for regression and cross-entropy for classification.
- ****Feature prioritization:**** Level-wise growth reduces overhead, as all features are considered simultaneously, avoiding repeated evaluations.
- ****Benefit:**** Handles complex feature interactions effectively by considering all features at the same depth.

### 3. Handling Missing Data

XGBoost manages missing values robustly during training and prediction using a sparsity-aware approach.

- ****Sparsity-Aware Split Finding:**** Treats missing values as a separate category when evaluating splits.
- ****Default direction:**** During tree building, missing values follow a default branch.
- ****Prediction:**** Instances with missing features follow the learned default branch.
- ****Benefit:**** Ensures robust predictions even with incomplete input data.

### 4. Cache-Aware Access

XGBoost optimizes memory usage to speed up computations by taking advantage of CPU cache.

- ****Memory hierarchy:**** Frequently accessed data is stored in the CPU cache.
- ****Spatial locality:**** Nearby data is accessed together to reduce memory access time.
- ****Benefit:**** Reduces reliance on slower main memory, improving training speed.

### 5. Approximate Greedy Algorithm

To efficiently handle large datasets, XGBoost uses an approximate method to find optimal splits.

- ****Weighted quantiles:**** Quickly estimate the best split without checking every possibility.
- ****Efficiency:**** Reduces computational overhead while maintaining accuracy.
- ****Benefit:**** Ideal for large datasets where full evaluation is costly.


## [[Python Example XGBoost]]
