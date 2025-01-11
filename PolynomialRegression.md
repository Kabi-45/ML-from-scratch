---

### **Key Concept**
For \( p \) features and a polynomial degree \( n \):
- Polynomial features include:
  - **All powers of individual features** up to degree \( n \) (\( x_1, x_1^2, \dots, x_1^n \)).
  - **Cross-product terms** between features up to degree \( n \), e.g., \( x_1x_2, x_1^2x_2, x_1x_2^2, \dots \).

---

### **Example for 2 Features (\( x_1, x_2 \)) Raised to Degree 2**
If \( p = 2 \) (two features) and \( n = 2 \) (degree of polynomial), the resulting polynomial features will be:

1. \( x_1^0 x_2^0 = 1 \) (bias term).
2. \( x_1^1 x_2^0 = x_1 \) (linear term for \( x_1 \)).
3. \( x_1^0 x_2^1 = x_2 \) (linear term for \( x_2 \)).
4. \( x_1^2 x_2^0 = x_1^2 \) (quadratic term for \( x_1 \)).
5. \( x_1^0 x_2^2 = x_2^2 \) (quadratic term for \( x_2 \)).
6. \( x_1^1 x_2^1 = x_1x_2 \) (interaction term).

#### Final List of Features:
\[
[1, x_1, x_2, x_1^2, x_2^2, x_1x_2]
\]

---

### **Example for 2 Features Raised to Degree 3**
If \( p = 2 \) and \( n = 3 \), the resulting features will include all combinations of \( x_1 \) and \( x_2 \) with total powers (sum of exponents) up to 3:

1. \( 1 \) (bias term).
2. \( x_1 \), \( x_2 \) (linear terms).
3. \( x_1^2 \), \( x_2^2 \), \( x_1x_2 \) (degree 2 terms).
4. \( x_1^3 \), \( x_2^3 \), \( x_1^2x_2 \), \( x_1x_2^2 \) (degree 3 terms).

#### Final List of Features:
\[
[1, x_1, x_2, x_1^2, x_2^2, x_1x_2, x_1^3, x_2^3, x_1^2x_2, x_1x_2^2]
\]

---

### **General Pattern**
For \( p = 2 \) (features) and \( n \) (degree):
- It includes terms of the form \( x_1^a x_2^b \), where \( a + b \leq n \).
- The total number of terms is given by the formula:
\[
\text{Total Features} = \binom{n + p}{p} = \frac{(n + p)!}{n! \cdot p!}
\]

---

### **Explanation in Your Terms**
Using your style of explanation, for \( p = 2 \) features (\( x_1 \), \( x_2 \)):
1. **For degree 1**: You get:
   \[
   x_1, x_2
   \]
2. **For degree 2**: You get:
   \[
   x_1, x_2, x_1^2, x_2^2, x_1x_2
   \]
3. **For degree 3**: You get:
   \[
   x_1, x_2, x_1^2, x_2^2, x_1x_2, x_1^3, x_2^3, x_1^2x_2, x_1x_2^2
   \]

The terms grow combinatorially, including **all combinations of powers and interactions**.

---

### **Misconception Corrected**
- You mentioned:
   > "For 2 features raised to degree 2 there will be \( x_1 + x_1^2 + x_2 + x_2^2 \)."

   This is incomplete. It misses the **interaction term** \( x_1x_2 \), which is also included when degree \( n = 2 \).

- Correct list for degree 2:
   \[
   [1, x_1, x_2, x_1^2, x_2^2, x_1x_2]
   \]
