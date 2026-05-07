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

---

## 3. Final Normal Form

After completing all row and column eliminations, we arrive at:
```math
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
\end{bmatrix}
```

Which is represented as:
$$
[ I_3 \mid 0 ]
$$

### 4. Conclusion
* **Normal Form:** $[I_3 \mid 0]$
* **Rank:** The number of non-zero rows is 3.
* **Result:** $\rho(A) = 3$
