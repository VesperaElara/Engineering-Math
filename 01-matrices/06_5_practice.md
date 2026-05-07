# Engineering Mathematics: Matrix Reduction to Normal Form

## 1. Theoretical Foundation

### 1.1 The Concept of Normal Form
The **Normal Form** (also known as the Canonical Form) of a matrix $A$ of rank $r$ is a specific block matrix structure obtained using elementary row and column transformations. It is typically represented as:

```math
\begin{bmatrix}
I_r & 0 \\
0 & 0 \\
\end{bmatrix}
```

Where $I_r$ is an identity matrix of order $r$, and the surrounding zeros represent null matrices of appropriate dimensions.

### 1.2 Objective of the Transformation
The goal is to isolate a leading identity block. Unlike the Echelon form (which only uses row operations), the Normal Form utilizes **both row and column operations** to systematically "clear" all elements except for the diagonal ones.

---

## 2. The Logic: Systematic Reduction Algorithm

To transform a matrix into its normal form, follow this hierarchical logic:

1.  **Pivot Selection:** Ensure the element at $a_{11}$ is 1. If it is not, swap rows or columns to bring a 1 to the $a_{11}$ position.
2.  **Row Clearing:** Use the pivot at $a_{11}$ to make all elements in the first column below it ($a_{21}, a_{31}, \dots$) equal to zero using row operations.
3.  **Column Clearing:** Use the pivot at $a_{11}$ to make all elements in the first row to its right ($a_{12}, a_{13}, \dots$) equal to zero using column operations.
4.  **Recurse:** Move to the next diagonal element $a_{22}$ and repeat the process for the remaining sub-matrix.

---

## 3. Step-by-Step Solution

**Problem:** Find the normal form and rank of the matrix:
```math
A = \begin{bmatrix}
2 & 3 & -1 & -1 \\
1 & -1 & -2 & -4 \\
3 & 1 & 3 & -2 \\
6 & 3 & 0 & -7 \\
\end{bmatrix}
```

### Step 1: Establish a Leading Pivot
We swap $R_1$ and $R_2$ to get $1$ at the $(1,1)$ position.

$$
\begin{bmatrix}
2 & 3 & -1 & -1 \\
1 & -1 & -2 & -4 \\
3 & 1 & 3 & -2 \\
6 & 3 & 0 & -7 \\
\end{bmatrix} (R_1 \leftrightarrow R_2) \longrightarrow \begin{bmatrix}
1 & -1 & -2 & -4 \\
2 & 3 & -1 & -1 \\
3 & 1 & 3 & -2 \\
6 & 3 & 0 & -7 \\
\end{bmatrix}
$$

### Step 2: Clear the First Column
Apply row operations: $R_2 \to R_2 - 2R_1$, $R_3 \to R_3 - 3R_1$, $R_4 \to R_4 - 6R_1$.

$$
\begin{bmatrix}
1 & -1 & -2 & -4 \\
2 & 3 & -1 & -1 \\
3 & 1 & 3 & -2 \\
6 & 3 & 0 & -7 \\
\end{bmatrix} (R_2-2R_1, R_3-3R_1, R_4-6R_1) \longrightarrow \begin{bmatrix}
1 & -1 & -2 & -4 \\
0 & 5 & 3 & 7 \\
0 & 4 & 9 & 10 \\
0 & 9 & 12 & 17 \\
\end{bmatrix}
$$

### Step 3: Clear the First Row
Apply column operations: $C_2 \to C_2 + C_1$, $C_3 \to C_3 + 2C_1$, $C_4 \to C_4 + 4C_1$.

$$
\begin{bmatrix}
1 & -1 & -2 & -4 \\
0 & 5 & 3 & 7 \\
0 & 4 & 9 & 10 \\
0 & 9 & 12 & 17 \\
\end{bmatrix} (C_2+C_1, C_3+2C_1, C_4+4C_1) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 5 & 3 & 7 \\
0 & 4 & 9 & 10 \\
0 & 9 & 12 & 17 \\
\end{bmatrix}
$$

### Step 4: Normalize the Second Pivot
Perform $R_2 \to R_2 - R_3$ to create a 1 at $a_{22}$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 5 & 3 & 7 \\
0 & 4 & 9 & 10 \\
0 & 9 & 12 & 17 \\
\end{bmatrix} (R_2-R_3) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & -6 & -3 \\
0 & 4 & 9 & 10 \\
0 & 9 & 12 & 17 \\
\end{bmatrix}
$$

### Step 5: Clear Column 2 and Row 2
Apply $R_3 \to R_3 - 4R_2$, $R_4 \to R_4 - 9R_2$ then $C_3 \to C_3 + 6C_2$, $C_4 \to C_4 + 3C_2$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & -6 & -3 \\
0 & 0 & 33 & 22 \\
0 & 0 & 66 & 44 \\
\end{bmatrix} (C_3+6C_2, C_4+3C_2) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 33 & 22 \\
0 & 0 & 66 & 44 \\
\end{bmatrix}
$$

### Step 6: Final Reduction
Divide $R_3$ by $33$, then clear $R_4$ and $C_4$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 33 & 22 \\
0 & 0 & 66 & 44 \\
\end{bmatrix} (R_3/33, R_4-2R_3) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 2/3 \\
0 & 0 & 0 & 0 \\
\end{bmatrix} \left(C_4 - \frac{2}{3}C_3\right) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 \\
\end{bmatrix}
$$

---

## 4. Final Result

The matrix has been reduced to the form:
```math
\begin{bmatrix}
I_3 & 0 \\
0 & 0 \\
\end{bmatrix}
```

**Rank of Matrix A:** The number of non-zero rows (or the order of the identity block) is **3**.
$$\rho(A) = 3$$
