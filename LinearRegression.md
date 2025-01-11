# Linear Regression Methods: OLS vs Gradient Descent

A side-by-side comparison and derivation of the **Ordinary Least Squares (OLS)/Normal Equation** and **Gradient Descent** methods for fitting a Linear Regression model.

## Step-by-Step Comparison

| Step | OLS/Normal Equation | Gradient Descent |
|------|-------------------|------------------|
| **Objective** | Minimize the Mean Squared Error (MSE):<br><br>$J(\theta) = \frac{1}{2m} \| y - X\theta \|^2$<br><br>Aim: Find $\theta$ that minimizes MSE | Minimize the Mean Squared Error (MSE):<br><br>$J(\theta) = \frac{1}{2m} \| y - X\theta \|^2$<br><br>Aim: Find $\theta$ that minimizes MSE |
| **Gradient Calculation** | Compute gradient of $J(\theta)$:<br><br>$\frac{\partial J(\theta)}{\partial \theta} = \frac{1}{m} X^T (X\theta - y)$<br><br>*Note: Gradient is identical in both methods* | Compute gradient of $J(\theta)$:<br><br>$\frac{\partial J(\theta)}{\partial \theta} = \frac{1}{m} X^T (X\theta - y)$<br><br>*Note: Gradient is identical in both methods* |
| **Approach** | Solve analytically:<br><br>Set gradient to 0 to find minimum:<br>$\frac{\partial J(\theta)}{\partial \theta} = 0$ | Solve iteratively:<br><br>Update $\theta$ using gradient:<br>$\theta = \theta - \alpha \cdot \frac{\partial J(\theta)}{\partial \theta}$ |
| **Derivation** | 1. Substitute gradient: $X^T (X\theta - y) = 0$<br>2. Simplify: $X^T X \theta = X^T y$<br>3. Solve: $\theta = (X^T X)^{-1} X^T y$ | 1. Start with initial $\theta$ (e.g., zeros)<br>2. Update: $\theta^{(t+1)} = \theta^{(t)} - \alpha \cdot \frac{1}{m} X^T (X\theta^{(t)} - y)$<br>3. Repeat until convergence |
| **Final Formula** | $\theta = (X^T X)^{-1} X^T y$ | $\theta = \theta - \alpha \cdot \frac{1}{m} X^T (X\theta - y)$ |
| **Context** | - Direct matrix inversion for $\theta$<br>- Requires invertible $X^T X$ | - Gradual adjustment of $\theta$<br>- Requires learning rate tuning |
| **Computational Cost** | $O(n^3)$ due to matrix inversion | $O(m \cdot n \cdot \text{iterations})$ |

## Key Characteristics

### Advantages

**OLS/Normal Equation:**
- Direct and exact solution
- Simple implementation for small/medium datasets

**Gradient Descent:**
- Scales well to large datasets
- Works with non-invertible $X^T X$
- Avoids matrix inversion

### Disadvantages

**OLS/Normal Equation:**
- Computationally expensive for large datasets
- Requires invertible $X^T X$
- Sensitive to multicollinearity

**Gradient Descent:**
- Requires hyperparameter tuning
- Convergence not guaranteed
- Can be slow with poor hyperparameters

## When to Use Each Method

### OLS/Normal Equation
- Small to medium-sized datasets
- When matrix inversion is computationally feasible
- When exact solution is required

### Gradient Descent
- Large datasets
- High-dimensional data
- When scalability is important
- When approximate solution is acceptable

## Summary
- **OLS/Normal Equation**: Provides closed-form solution through system of linear equations
- **Gradient Descent**: Iteratively updates parameters using cost function gradient
