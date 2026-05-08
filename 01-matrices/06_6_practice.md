# Engineering Mathematics: Matrix Reduction to Normal Form

## 1. Problem Statement
Find the normal form and the rank of the matrix:
```math
A = \begin{bmatrix}
8 & 1 & 3 & 6 \\
0 & 3 & 2 & 2 \\
-8 & -1 & -3 & 4 \\
\end{bmatrix}
```

---

## 2. Transformation Process

### Step 1: Establish a Leading Pivot
To make the arithmetic easier, we swap $C_1$ and $C_2$ to bring the element `1` to the $(1,1)$ position.

$$
\begin{bmatrix}
8 & 1 & 3 & 6 \\
0 & 3 & 2 & 2 \\
-8 & -1 & -3 & 4 \\
\end{bmatrix} (C_1 \leftrightarrow C_2) \longrightarrow \begin{bmatrix}
1 & 8 & 3 & 6 \\
3 & 0 & 2 & 2 \\
-1 & -8 & -3 & 4 \\
\end{bmatrix}
$$

### Step 2: Clear the First Column
We use the pivot at $a_{11}$ to eliminate the elements below it.
Apply: $R_2 \to R_2 - 3R_1$ and $R_3 \to R_3 + R_1$.

$$
\begin{bmatrix}
1 & 8 & 3 & 6 \\
3 & 0 & 2 & 2 \\
-1 & -8 & -3 & 4 \\
\end{bmatrix} (R_2 - 3R_1, R_3 + R_1) \longrightarrow \begin{bmatrix}
1 & 8 & 3 & 6 \\
0 & -24 & -7 & -16 \\
0 & 0 & 0 & 10 \\
\end{bmatrix}
$$

### Step 3: Clear the First Row
Now we use column operations to clear the elements to the right of the pivot.
Apply: $C_2 \to C_2 - 8C_1$, $C_3 \to C_3 - 3C_1$, $C_4 \to C_4 - 6C_1$.

$$
\begin{bmatrix}
1 & 8 & 3 & 6 \\
0 & -24 & -7 & -16 \\
0 & 0 & 0 & 10 \\
\end{bmatrix} (C_2, C_3, C_4 \text{ ops}) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & -24 & -7 & -16 \\
0 & 0 & 0 & 10 \\
\end{bmatrix}
$$

### Step 4: Normalize the Second and Third Pivots
We need to isolate the remaining non-zero elements. We swap $C_2$ and $C_4$ to bring the value `10` into a more manageable position, then normalize the rows.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & -24 & -7 & -16 \\
0 & 0 & 0 & 10 \\
\end{bmatrix} (C_2 \leftrightarrow C_4) \longrightarrow \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & -16 & -7 & -24 \\
0 & 10 & 0 & 0 \\
\end{bmatrix}
$$

By continuing elementary operations ($R_2 \to R_2 + 2R_3$, then clearing the remaining constants), the matrix reduces to its canonical identity structure.

### Step 5: Initial State and Pivot 1
The first pivot $a_{11}$ is already $1$, and its column is cleared.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & -16 & -7 & -24 \\
0 & 10 & 0 & 0
\end{bmatrix}
\left(R_2 \leftrightarrow R_3\right) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 10 & 0 & 0 \\
0 & -16 & -7 & -24
\end{bmatrix}
$$

### Step 6: Establishing Pivot 2
We normalize the second row to get a leading $1$ at $a_{22}$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 10 & 0 & 0 \\
0 & -16 & -7 & -24
\end{bmatrix}
\left(R_2 \to \frac{1}{10}R_2\right) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & -16 & -7 & -24
\end{bmatrix}
$$

### Step 7: Vertical Clearing (Row Operations)
Use the new pivot at $a_{22}$ to clear the value below it in $R_3$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & -16 & -7 & -24
\end{bmatrix}
\left(R_3 \to R_3 + 16R_2\right) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & -7 & -24
\end{bmatrix}
$$

### Step 8: Establishing Pivot 3
We normalize the third row to get a leading $1$ at $a_{33}$.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & -7 & -24
\end{bmatrix}
\left(R_3 \to -\frac{1}{7}R_3\right) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & \frac{24}{7}
\end{bmatrix}
$$

### Step 9: Horizontal Clearing (Column Operations)
Finally, we use column operations to eliminate any remaining values to the right of our pivots to reach the identity structure.

$$
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & \frac{24}{7}
\end{bmatrix}
\left(C_4 \to C_4 - \frac{24}{7}C_3\right) \longrightarrow
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
$$

---

## 10. Final Result
The matrix is now in the form $[I_3 \mid 0]$.
*   **Rank of the Matrix ($r$)**: 3
*   **Canonical Form**: 
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
```

Which is represented as:
```math
\begin{bmatrix}
I_3 & 0 \\
\end{bmatrix}
```

### 4. Conclusion
* **Normal Form:** $[I_3 \mid 0]$
* **Rank:** The number of non-zero rows is 3.
* **Result:** $\rho(A) = 3$
