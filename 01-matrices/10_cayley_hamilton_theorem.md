# Engineering Mathematics: Matrix Theory
## Cayley-Hamilton Theorem — Part 1: Conceptual Foundation

The Cayley-Hamilton Theorem is a fundamental bridge between linear algebra and polynomial algebra. It allows us to treat a matrix as a variable within its own characteristic equation.

---

### 1. The Core Statement
**Theorem:** Every square matrix satisfies its own characteristic equation.

If we have a square matrix $A$ of order $n$, and its characteristic polynomial is defined by:
$P(\lambda) = |A - \lambda I| = a_0\lambda^n + a_1\lambda^{n-1} + a_2\lambda^{n-2} + \dots + a_n$

The theorem states that if you replace the scalar $\lambda$ with the matrix $A$ (and the constant term $a_n$ with $a_n I$), the result is the Null Matrix ($O$):
$$a_0 A^n + a_1 A^{n-1} + a_2 A^{n-2} + \dots + a_n I = O$$

---

### 2. Conceptual Breakdown
To understand why this is non-trivial, we must look at the components:

1.  **Characteristic Matrix $(A - \lambda I)$**:
    * This is formed by subtracting $\lambda$ from the diagonal elements of matrix $A$.
    * Example for a $2 \times 2$ matrix:
    
```math
\begin{bmatrix}
a_{11}-\lambda & a_{12}\\
a_{21} & a_{22}-\lambda
\end{bmatrix}
```

2.  **Characteristic Polynomial**:
    * When you find the determinant |A - $\lambda I$|, you get a polynomial in terms of $\lambda$.
    * The degree of this polynomial is equal to the order of the matrix ($n$).

3.  **The "Satisfies" Logic**:
    * Usually, we solve |A - $\lambda I| = 0$$ to find Eigenvalues (scalars).
    * Cayley-Hamilton tells us that the matrix $A$ itself "plugs into" that formula and results in zero.

---

### 3. Step-by-Step Algorithm (Verification)
To verify this theorem for a given matrix $A$:

1.  **Find the Characteristic Equation**: Calculate the determinant $|A - \lambda I| = 0$.
2.  **Expand the Determinant**: Write it in the form $a_0\lambda^n + a_1\lambda^{n-1} + \dots + a_n = 0$.
3.  **Substitute Matrix $A$**: Replace $\lambda$ with $A$. Note: $a_n$ becomes $a_n I$.
4.  **Compute Powers**: Calculate $A^2, A^3, \dots, A^n$ as required.
5.  **Simplify**: Sum the matrices to verify they result in the Null Matrix.

---

### 4. Illustrative Example ($2 \times 2$)
Let us verify the theorem for matrix 
```math
A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}
```

**Step 1: Characteristic Equation**
```math
|A - \lambda I| = \begin{vmatrix} 1-\lambda & 2 \\ 3 & 4-\lambda \end{vmatrix} = 0
```

$(1-\lambda)(4-\lambda) - (2)(3) = 0$

$4 - \lambda - 4\lambda + \lambda^2 - 6 = 0$

$\lambda^2 - 5\lambda - 2 = 0$

**Step 2: Cayley-Hamilton Substitution**
According to the theorem, $A$ must satisfy:
$A^2 - 5A - 2I = O$

**Step 3: Verification**
Calculate $A^2$:

```math
A^2 = \begin{bmatrix}
1 & 2\\
3 & 4
\end{bmatrix} \begin{bmatrix}
1 & 2\\
3 & 4
\end{bmatrix} \longrightarrow \begin{bmatrix}
7 & 10\\
15 & 22
\end{bmatrix}
```

Substitute into the equation:

```math
\begin{bmatrix}
7 & 10\\
15 & 22
\end{bmatrix} - 5\begin{bmatrix}
1 & 2\\
3 & 4
\end{bmatrix} - 2\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix}
```

```math
\longrightarrow \begin{bmatrix}
7-5-2 & 10-10-0\\
15-15-0 & 22-20-2
\end{bmatrix} \longrightarrow \begin{bmatrix}
0 & 0\\
0 & 0
\end{bmatrix}
```

**Result:** The theorem is verified.

---
---

## Cayley-Hamilton Theorem — Part 2: The Formal Proof

The proof of this theorem relies on the relationship between a matrix, its adjoint, and its determinant. We use the property: $D \cdot \text{adj}(D) = |D| \cdot I$.

---

### 1. The Setup
Let $A$ be a square matrix of order $n$. Its characteristic equation is:
$$|A - \lambda I| = a_0\lambda^n + a_1\lambda^{n-1} + \dots + a_n = 0$$

Now, consider the matrix $B = \text{adj}(A - \lambda I)$. Since the elements of $(A - \lambda I)$ are at most of first degree in $\lambda$, the cofactors (and thus the elements of the adjoint) will be polynomials in $\lambda$ of degree at most $(n-1)$.

Therefore, we can write the adjoint as a matrix polynomial:
$$\text{adj}(A - \lambda I) = B_0\lambda^{n-1} + B_1\lambda^{n-2} + \dots + B_{n-1}$$
Where $B_0, B_1, \dots$ are square matrices of order $n$.

---

### 2. The Derivation
Using the fundamental property $D \cdot \text{adj}(D) = |D| \cdot I$, and substituting $D = (A - \lambda I)$:

$$(A - \lambda I) \cdot \text{adj}(A - \lambda I) = |A - \lambda I| \cdot I$$

Substitute the polynomial forms into this equation:
$$(A - \lambda I)(B_0\lambda^{n-1} + B_1\lambda^{n-2} + \dots + B_{n-1}) = (a_0\lambda^n + a_1\lambda^{n-1} + \dots + a_n)I$$

**Equating coefficients of like powers of $\lambda$ on both sides:**
*   $\lambda^n: -IB_0 = a_0 I$
*   $\lambda^{n-1}: AB_0 - IB_1 = a_1 I$
*   $\lambda^{n-2}: AB_1 - IB_2 = a_2 I$
*   $\dots$
*   $\lambda^0: AB_{n-1} = a_n I$

---

### 3. Final Step: Pre-multiplication
To eliminate the $B$ matrices, we pre-multiply the equations by $A^n, A^{n-1}, A^{n-2}, \dots, I$ respectively:
*   $-A^n B_0 = a_0 A^n$
*   $A^n B_0 - A^{n-1} B_1 = a_1 A^{n-1}$
*   $A^{n-1} B_1 - A^{n-2} B_2 = a_2 A^{n-2}$
*   $\dots$
*   $AB_{n-1} = a_n I$

Adding all these equations, the terms on the left side cancel out (telescoping sum), leaving:
$$O = a_0 A^n + a_1 A^{n-1} + a_2 A^{n-2} + \dots + a_n I$$

**Proof Complete.**

---
---

## Cayley-Hamilton Theorem — Part 3: Engineering Applications

In Engineering M1, the theorem is a powerful tool for rapid matrix computations.

### 1. Finding the Inverse of a Matrix ($A^{-1}$)
If the constant term $a_n \neq 0$, the matrix is non-singular. We can find the inverse without the full adjoint method.

**The Algorithm:**
1.  Start with the CH Equation: $a_0 A^n + a_1 A^{n-1} + \dots + a_n I = O$.
2.  Multiply the entire equation by $A^{-1}$:
    $$a_0 A^{n-1} + a_1 A^{n-2} + \dots + a_{n-1} I + a_n A^{-1} = O$$
3.  Rearrange to solve for $A^{-1}$:
    $$A^{-1} = -\frac{1}{a_n} (a_0 A^{n-1} + a_1 A^{n-2} + \dots + a_{n-1} I)$$

---

### 2. Finding Higher Powers of Matrices
CH Theorem allows you to reduce high powers (like $A^{10}$) into a linear combination of $I, A, A^2, \dots, A^{n-1}$.

**The Logic:**
*   Example: If $A^2 - 5A - 2I = O$, then $A^2 = 5A + 2I$.
*   To find $A^3$, multiply by $A$: $A^3 = 5A^2 + 2A$.
*   Substitute $A^2$ back in: $A^3 = 5(5A + 2I) + 2A = 27A + 10I$.

---

### 3. Summary for Exams
| Task | Method |
| :--- | :--- |
| **Verify CH Theorem** | Find Char. Eq., plug in $A$, show it equals $O$. |
| **Find $A^{-1}$** | Multiply CH Eq. by $A^{-1}$ and isolate $A^{-1}$. |
| **Find $A^k$** | Express $A^k$ as a polynomial of lower powers using the CH Eq. |
