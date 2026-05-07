# Matrix Theory: Rank and Nullity

This study note provides a clear, practical guide to understanding the **Rank** and **Nullity** of a matrix.

---

## 1. The Minor of a Matrix
Before understanding rank, you must define the **minor**.

*   **Definition:** Take any matrix $A$ (square or rectangular). If you delete certain rows and columns to leave behind a square sub-matrix of size $p \times p$, the determinant of that sub-matrix is called a **minor of order $p$**.
*   **Logic:** A $3 \times 3$ matrix contains multiple $2 \times 2$ minors and one $3 \times 3$ minor (the determinant of the matrix itself).

---

## 2. Rank of a Matrix
Represented by $\rho(A)$. The rank is the "useful" size of a matrix. It represents the number of linearly independent rows or columns.

### Formal Properties
A number $r$ is the **rank** of matrix $A$ if it obeys these two conditions:
1.  **Existence:** There is at least one minor of order $r$ which is **not zero** (does not vanish).
2.  **Vanishing:** Every minor of order higher than $r$ is **equal to zero**.

### Key Rules

| Matrix Type | Rank Property |
| :--- | :--- |
| **Zero Matrix** | Always $0$ |
| **Unit Matrix** ( $I_n$ )| Always $n$ |
| **Non-Singular** ( det $A$ $\neq$ $0$ )| Rank equals the order $n$ |

---

## 3. Nullity of a Matrix
Represented by $N(A)$. Nullity represents the "redundant" or "wasted" dimensions in a system of equations.

*   **Definition:** For a square matrix of order $n$, the value $n - r$ is called the **nullity**.
*   **Formula:** 
$$N(A) = n - \rho(A)$$

---

## 4. Practical Example: Finding Rank 
While the "Minor Method" works for small matrices, the **Echelon Form** (using Row Transformations) is the professional engineering standard.

### The Problem
Find the rank and nullity of the matrix $A$:
```math
A = \begin{bmatrix} 3 & 2 & 5 \\ -1 & 0 & 6 \\ 7 & 8 & 3 \end{bmatrix}
```

### Step-by-Step Transformation
To find the rank, we reduce the matrix to a form where all elements below the diagonal are zero.

**Step 1: Get a '1' in the top left ($a_{11}$) for easier calculation.**
Swap $R_1$ and $R_2$, then multiply the new $R_1$ by $-1$:
```math
\begin{bmatrix} 3 & 2 & 5 \\ -1 & 0 & 6 \\ 7 & 8 & 3 \end{bmatrix}
\rightarrow
\begin{bmatrix} -1 & 0 & 6 \\ 3 & 2 & 5 \\ 7 & 8 & 3 \end{bmatrix}
\rightarrow
\begin{bmatrix} 1 & 0 & -6 \\ 3 & 2 & 5 \\ 7 & 8 & 3 \end{bmatrix}
```

**Step 2: Create zeros in the first column.**
Apply $R_2 \to R_2 - 3R_1$ and $R_3 \to R_3 - 7R_1$:
```math
\begin{bmatrix} 1 & 0 & -6 \\ 0 & 2 & 23 \\ 0 & 8 & 45 \end{bmatrix}
```

**Step 3: Create a zero in the third row, second column.**
Apply $R_3 \to R_3 - 4R_2$:
```math
\begin{bmatrix} 1 & 0 & -6 \\ 0 & 2 & 23 \\ 0 & 0 & -47 \end{bmatrix}
```

### Final Analysis
1.  **Count Non-Zero Rows:** There are **3** non-zero rows.
2.  **Rank:** $\rho(A) = 3$.
3.  **Nullity:** Since the order $n=3$, then $N(A) = 3 - 3 = 0$.

> **Summary:** Because the rank is equal to the order ($r=n$), this matrix is **non-singular**, meaning its determinant is not zero and it is fully invertible.
