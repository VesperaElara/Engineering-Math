# Engineering Mathematics: Rank and Nullity via Echelon Form

This study note covers the fundamental process of finding the **Rank** and **Nullity** of a matrix using **Row Echelon Form**. This is a critical skill for understanding the dimensionality of linear systems and is a prerequisite for advanced Engineering Math.

## 1. Core Concepts

### What is Row Echelon Form?
A matrix is in Row Echelon Form (REF) if:
1. All non-zero rows are above any rows of all zeros.
2. The leading coefficient (the first non-zero number from the left, called a **pivot**) of a non-zero row is always to the right of the leading coefficient of the row above it.
3. All entries in a column below a leading coefficient are zeros.

### Rank and Nullity
* **Rank ($\rho$):** The number of non-zero rows in the Row Echelon Form of a matrix. It represents the number of linearly independent rows.
* **Nullity ($\nu$):** The number of free variables in the system.
* **Rank-Nullity Theorem:** For any matrix with $n$ columns:
    $$\text{Rank} + \text{Nullity} = n$$

---

## 2. Step-by-Step Algorithm
To transform a matrix into Echelon form, we use **Elementary Row Operations**:
1. Swap two rows ($R_i \leftrightarrow R_j$).
2. Multiply a row by a non-zero constant ($k R_i$).
3. Add or subtract a multiple of one row to another ($R_i \to R_i \pm k R_j$).

---

## 3. Detailed Solutions

### Problem (i)
$$
A = \begin{bmatrix}
1 & 3 & 4 & 3 \\
3 & 9 & 12 & 9 \\
1 & 3 & 4 & 1
\end{bmatrix}
$$

**Step 1:** Use $R_1$ to eliminate the first elements of $R_2$ and $R_3$.
Perform $R_2 \to R_2 - 3R_1$ and $R_3 \to R_3 - R_1$.

$$
\begin{bmatrix}
1 & 3 & 4 & 3 \\
3 & 9 & 12 & 9 \\
1 & 3 & 4 & 1
\end{bmatrix}
\left(R_2 \to R_2 - 3R_1\right) \longrightarrow
\begin{bmatrix}
1 & 3 & 4 & 3 \\
0 & 0 & 0 & 0 \\
1 & 3 & 4 & 1
\end{bmatrix}$$

$$
\begin{bmatrix}
1 & 3 & 4 & 3 \\
0 & 0 & 0 & 0 \\
1 & 3 & 4 & 1
\end{bmatrix}
\left(R_3 \to R_3 - R_1\right) \longrightarrow
\begin{bmatrix}
1 & 3 & 4 & 3 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & -2
\end{bmatrix}$$

**Step 2:** Swap $R_2$ and $R_3$ to bring the non-zero row up.

$$
\begin{bmatrix}
1 & 3 & 4 & 3 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & -2
\end{bmatrix}
\left(R_2 \leftrightarrow R_3\right) \longrightarrow
\begin{bmatrix}
1 & 3 & 4 & 3 \\
0 & 0 & 0 & -2 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

**Final Result for (i):**
* **Non-zero rows:** 2
* **Rank ($\rho$):** 2
* **Columns ($n$):** 4
* **Nullity ($\nu$):** $4 - 2 = 2$

---

### Problem (ii)
$$
B = \begin{bmatrix}
1 & 2 & 1 & 2 \\
1 & 3 & 2 & 2 \\
2 & 4 & 3 & 4 \\
3 & 7 & 4 & 6
\end{bmatrix}
$$

**Step 1:** Eliminate elements below the pivot in the first column.
Perform $R_2 \to R_2 - R_1$, $R_3 \to R_3 - 2R_1$, and $R_4 \to R_4 - 3R_1$.

$$
\begin{bmatrix}
1 & 2 & 1 & 2 \\
1 & 3 & 2 & 2 \\
2 & 4 & 3 & 4 \\
3 & 7 & 4 & 6
\end{bmatrix}
\left(R_2 \to R_2 - R_1\right) \longrightarrow
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
2 & 4 & 3 & 4 \\
3 & 7 & 4 & 6
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
2 & 4 & 3 & 4 \\
3 & 7 & 4 & 6
\end{bmatrix}
\left(R_3 \to R_3 - 2R_1\right) \longrightarrow
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
3 & 7 & 4 & 6
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
3 & 7 & 4 & 6
\end{bmatrix}
\left(R_4 \to R_4 - 3R_1\right) \longrightarrow
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 1 & 0
\end{bmatrix}
$$

**Step 2:** Eliminate elements below the second pivot.
Perform $R_4 \to R_4 - R_2$.

$$\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 1 & 0
\end{bmatrix}
\left(R_4 \to R_4 - R_2\right) \longrightarrow
\begin{bmatrix}
1 & 2 & 1 & 2 \\
0 & 1 & 1 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$

**Final Result for (ii):**
* **Non-zero rows:** 3
* **Rank ($\rho$):** 3
* **Columns ($n$):** 4
* **Nullity ($\nu$):** $4 - 3 = 1$
