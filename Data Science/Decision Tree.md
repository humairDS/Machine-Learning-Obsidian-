A **Decision Tree** is a Machine Learning algorithm that makes decisions like a flowchart.

Example:
                Is Age < 30?
                 /        \
               Yes         No
              /             \
      Salary > 50k?      Buy = No
         /     \
       Yes      No
    Buy=Yes   Buy=No
## Real Life Example
Imagine a bank deciding wheter to approve a loan.

The bank checks:
1. Income 
2. Credit Score
3. Existing Debt


Example:

Income > 100k?
   ├── Yes → Loan Approved
   └── No
         ├── Credit Score > 700?
         │       ├── Yes → Approved
         │       └── No → Rejected


## Types of Decision Trees

1. Classification Tree(For Categorical output)
2. Regression Tree(for Continous Numbers)

## Important Terms

1. Root Node (The First Question)
2. Branch (Possible answer paths)
3. Leaf Node (Final Output)
4. Splitting (process of dividing data based on conditions)



## How Decision Tree Chooses Questions

For classification it uses:
- Gini Impurity
- Entropy

For regression it uses:
- Mean Squared Error


## [[Decision Tree Python Example]]
