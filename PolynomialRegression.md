# Polynomial Features in Machine Learning

## Key Concept
For p features and a polynomial degree n:
- Polynomial features include:
  - All powers of individual features up to degree n (x₁, x₁², ..., x₁ⁿ)
  - Cross-product terms between features up to degree n (x₁x₂, x₁²x₂, x₁x₂², ...)

## Two Features with Degree 2
When p = 2 (two features) and n = 2 (degree of polynomial), the resulting polynomial features are:

1. x₁⁰x₂⁰ = 1 (bias term)
2. x₁¹x₂⁰ = x₁ (linear term for x₁)
3. x₁⁰x₂¹ = x₂ (linear term for x₂)
4. x₁²x₂⁰ = x₁² (quadratic term for x₁)
5. x₁⁰x₂² = x₂² (quadratic term for x₂)
6. x₁¹x₂¹ = x₁x₂ (interaction term)

Final feature list: [1, x₁, x₂, x₁², x₂², x₁x₂]

## Two Features with Degree 3
When p = 2 and n = 3, features include all combinations with total powers up to 3:

1. 1 (bias term)
2. x₁, x₂ (linear terms)
3. x₁², x₂², x₁x₂ (degree 2 terms)
4. x₁³, x₂³, x₁²x₂, x₁x₂² (degree 3 terms)

Final feature list: [1, x₁, x₂, x₁², x₂², x₁x₂, x₁³, x₂³, x₁²x₂, x₁x₂²]

## General Pattern
For p = 2 features and degree n:
- Includes terms x₁ᵃx₂ᵇ, where a + b ≤ n
- Total number of terms: (n + p)!/(n! × p!)

## Breakdown by Degree
For p = 2 features (x₁, x₂):

### Degree 1
```
x₁, x₂
```

### Degree 2
```
x₁, x₂, x₁², x₂², x₁x₂
```

### Degree 3
```
x₁, x₂, x₁², x₂², x₁x₂, x₁³, x₂³, x₁²x₂, x₁x₂²
```

## Common Misconception
The expression "x₁ + x₁² + x₂ + x₂²" for 2 features with degree 2 is incomplete. It misses the interaction term x₁x₂.

Correct complete list for degree 2:
```
[1, x₁, x₂, x₁², x₂², x₁x₂]
```

Note: The terms grow combinatorially, including all possible combinations of powers and interactions up to the specified degree.
