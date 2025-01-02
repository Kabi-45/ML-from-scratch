# Side-by-Side Comparison of OLS/Normal Equation and Gradient Descent for Linear Regression

| **Step**                  | **OLS/Normal Equation**                                                                                       | **Gradient Descent**                                                                                             |
|---------------------------|----------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Objective**             | Minimize the Mean Squared Error (MSE):                                                                       | Minimize the Mean Squared Error (MSE):                                                                          |
|                           | \[ J(\theta) = \frac{1}{2m} \| y - X\theta \|^2 \]                                                           | \[ J(\theta) = \frac{1}{2m} \| y - X\theta \|^2 \]                                                              |
|                           | Both aim to find \( \theta \) that minimizes the MSE.                                                       | Both aim to find \( \theta \) that minimizes the MSE.                                                           |
| **Gradient Calculation**  | Compute the gradient of \( J(\theta) \):                                                                     | Compute the gradient of \( J(\theta) \):                                                                        |
|                           | \[ \frac{\partial J(\theta)}{\partial \theta} = \frac{1}{m} X^T (X\theta - y) \]                             | \[ \frac{\partial J(\theta)}{\partial \theta} = \frac{1}{m} X^T (X\theta - y) \]                                |
|                           | The gradient is identical in both methods, as it is derived from the same cost function.                    | The gradient is identical in both methods, as it is derived from the same cost function.                       |
| **Approach**              | Solve analytically to find \( \theta \):                                                                     | Solve iteratively to find \( \theta \):                                                                         |
|                           | - The gradient is set to 0 to find the minimum of \( J(\theta) \):                                           | - Use the gradient to iteratively update \( \theta \):                                                          |
|                           | \[ \frac{\partial J(\theta)}{\partial \theta} = 0 \]                                                        | \[ \theta = \theta - \alpha \cdot \frac{\partial J(\theta)}{\partial \theta} \]                                 |
| **Derivation**            | Substitute gradient into the equation:                                                                      | Iteratively adjust \( \theta \):                                                                                |
|                           | \[ X^T (X\theta - y) = 0 \]                                                                                 | \[ \theta^{(t+1)} = \theta^{(t)} - \alpha \cdot \frac{1}{m} X^T (X\theta^{(t)} - y) \]                          |
|                           | Simplify:                                                                                                   |                                                                                                                  |
|                           | \[ X^T X \theta = X^T y \]                                                                                  | - Start with an initial guess for \( \theta \) (e.g., zeros).                                                   |
|                           | Solve for \( \theta \):                                                                                     | - Use the gradient to iteratively adjust \( \theta \).                                                          |
|                           | \[ \theta = (X^T X)^{-1} X^T y \]                                                                           | - Repeat until convergence or a stopping criterion is met.                                                      |
| **Final Formula**         | \[ \theta = (X^T X)^{-1} X^T y \]                                                                           | \[ \theta = \theta - \alpha \cdot \frac{1}{m} X^T (X\theta - y) \]                                              |
| **Context**               | - Uses matrix inversion to directly compute \( \theta \).                                                   | - Gradually adjusts \( \theta \) by moving in the direction opposite to the gradient.                           |
|                           | - Requires \( X^T X \) to be invertible.                                                                    | - Requires tuning of \( \alpha \) (learning rate) and can take many iterations.                                 |
| **Computational Cost**    | \[ O(n^3) \] (due to matrix inversion).                                                                     | \[ O(m \cdot n \cdot \text{iterations}) \] (depends on the number of iterations).                               |
| **Advantages**            | - Direct and exact solution.                                                                                | - Scales to large datasets; avoids matrix inversion.                                                            |
|                           | - Simple to implement for small to medium datasets.                                                        | - Works even if \( X^T X \) is not invertible.                                                                  |
| **Disadvantages**         | - Computationally expensive for large datasets.                                                            | - Requires hyperparameter tuning (learning rate).                                                               |
|                           | - \( X^T X \) must be invertible (multicollinearity can be an issue).                                       | - Convergence can be slow and is not guaranteed for poorly chosen hyperparameters.                              |

---

## Summary of Key Differences
- **OLS/Normal Equation** provides a closed-form solution for \( \theta \) by solving a system of linear equations.
- **Gradient Descent** iteratively updates \( \theta \) based on the gradient of the cost function.

## Use Case Considerations
- Use **OLS/Normal Equation** for small datasets where matrix inversion is computationally feasible.
- Use **Gradient Descent** for large datasets, high-dimensional data, or when scalability is important.
