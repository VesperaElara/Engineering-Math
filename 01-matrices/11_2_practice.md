# Engineering Mathematics: Cayley-Hamilton Theorem ($3 \times 3$ Matrix)

This note provides a comprehensive guide to verifying the Cayley-Hamilton Theorem and finding the inverse of a $3 \times 3$ matrix.

---

## 1. Theoretical Foundation

### The Cayley-Hamilton Theorem
The theorem states that every square matrix satisfies its own characteristic equation. For a $3 \times 3$ matrix $A$, if the characteristic equation is $\det(A - \lambda I) = -\lambda^3 + S_1\lambda^2 - S_2\lambda + S_3 = 0$, then:
$$-A^3 + S_1A^2 - S_2A + S_3I = 0$$

### Conceptual Logic
1.  **Characteristic Equation**: Determine the coefficients $S_1$ (Trace), $S_2$ (Sum of minors of diagonal elements), and $S_3$ (Determinant).
2.  **Verification**: Substitute matrix $A$ into the polynomial and show it results in a zero matrix.
3.  **Inverse Computation**: Manipulate the equation to solve for $A^{-1}$ using $A^2, A,$ and $I$.

---

## 2. Step-by-Step Verification & Application

Given the matrix $A$:
```math
A = \begin{bmatrix}
1 & 0 & 2\\
0 & 2 & 1\\
2 & 0 & 3
\end{bmatrix}
```

### Step 1: Find the Characteristic Equation
We use the shortcut for $3 \times 3$ matrices: $\lambda^3 - S_1\lambda^2 + S_2\lambda - S_3 = 0$.

*   **$S_1$ (Trace):** $1 + 2 + 3 = 6$
*   **$S_2$ (Sum of diagonal minors):**
```math
\begin{vmatrix} 2 & 1 \\ 0 & 3 \end{vmatrix} + \begin{vmatrix} 1 & 2 \\ 2 & 3 \end{vmatrix} + \begin{vmatrix} 1 & 0 \\ 0 & 2 \end{vmatrix} = (6-0) + (3-4) + (2-0) = 6 - 1 + 2 = 7
```
*   **$S_3$ (Determinant $|A|$):**
    $1(6-0) - 0 + 2(0-4) = 6 - 8 = -1$

**Characteristic Equation:**
$$\lambda^3 - 6\lambda^2 + 7\lambda + 1 = 0$$

### Step 2: Verification of the Theorem
We must show that $A^3 - 6A^2 + 7A + I = 0$.

**Calculate $A^2$:**
```math
A^2 = \begin{bmatrix}
1 & 0 & 2\\
0 & 2 & 1\\
2 & 0 & 3
\end{bmatrix} \begin{bmatrix}
1 & 0 & 2\\
0 & 2 & 1\\
2 & 0 & 3
\end{bmatrix} \longrightarrow A^2 = \begin{bmatrix}
5 & 0 & 8\\
2 & 4 & 5\\
8 & 0 & 13
\end{bmatrix}
```

**Calculate $A^3$:**
```math
A^3 = A^2 \cdot A = \begin{bmatrix}
5 & 0 & 8\\
2 & 4 & 5\\
8 & 0 & 13
\end{bmatrix} \begin{bmatrix}
1 & 0 & 2\\
0 & 2 & 1\\
2 & 0 & 3
\end{bmatrix} \longrightarrow A^3 = \begin{bmatrix}
21 & 0 & 34\\
12 & 8 & 23\\
34 & 0 & 55
\end{bmatrix}
```

**Substitute into $A^3 - 6A^2 + 7A + I$:**
```math
\begin{bmatrix}
21 & 0 & 34\\
12 & 8 & 23\\
34 & 0 & 55
\end{bmatrix} - \begin{bmatrix}
30 & 0 & 48\\
12 & 24 & 30\\
48 & 0 & 78
\end{bmatrix} + \begin{bmatrix}
7 & 0 & 14\\
0 & 14 & 7\\
14 & 0 & 21
\end{bmatrix} + \begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1
\end{bmatrix} = \begin{bmatrix}
0 & 0 & 0\\
0 & 0 & 0\\
0 & 0 & 0
\end{bmatrix}
```

### Step 3: Find the Inverse Matrix ($A^{-1}$)
From $A^3 - 6A^2 + 7A + I = 0$, multiply by $A^{-1}$:

$$A^2 - 6A + 7I + A^{-1} = 0$$

$$A^{-1} = 6A - A^2 - 7I$$

**Calculation:**
```math
A^{-1} = \begin{bmatrix}
6 & 0 & 12\\
0 & 12 & 6\\
12 & 0 & 18
\end{bmatrix} - \begin{bmatrix}
5 & 0 & 8\\
2 & 4 & 5\\
8 & 0 & 13
\end{bmatrix} - \begin{bmatrix}
7 & 0 & 0\\
0 & 7 & 0\\
0 & 0 & 7
\end{bmatrix}
```

```math
A^{-1} = \begin{bmatrix}
6-5-7 & 0-0-0 & 12-8-0\\
0-2-0 & 12-4-7 & 6-5-0\\
12-8-0 & 0-0-0 & 18-13-7
\end{bmatrix} \longrightarrow A^{-1} = \begin{bmatrix}
-6 & 0 & 4\\
-2 & 1 & 1\\
4 & 0 & -2
\end{bmatrix}
```
